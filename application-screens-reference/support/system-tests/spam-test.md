# Spam Test

### Introduction

In order to ensure email delivery you should make sure to [configure your domains](../../settings/common-system-settings/domains/) appropriately. To check your settings for a campaign you can use the Spam Test tool to generate a report of any potential issues.

{% hint style="info" %}
Navigate to **Support -> System Tests -> Spam Test**
{% endhint %}

***

### What is the spam test tool doing?

The spam test verifies three things about your campaign's settings:

1. DNS records (SPF, PTR, etc.) of the sender domain.
2. Domain reputation - Lucy checks a number of blacklists to see if your domain/IP address appear.
3. Content - Lucy checks the email and landing page content for keywords that can result in a high spam score.

{% hint style="warning" %}
The domain reputation check can take up to 30 minutes if you have enabled the full blacklist  scan in the [advanced settings](../../settings/advanced-system-settings/advanced-settings.md).
{% endhint %}

***

### Spam Test Results

To initiate the check simply select a campaign and click **Start**.\
Once the spam check finishes, a report is generated for you:

<figure><img src="../../../.gitbook/assets/image (854).png" alt=""><figcaption></figcaption></figure>

***

### Why was my email rejected or marked as spam?

Spam filters identify spam using a long list of criteria, but generally they consider things such as:

* **Relationship with Subscriber**: Emails are more likely to be marked as spam if recipients don't recognize or trust the sender.
* **Reputation of IP Address and Sender Domain**: A poor reputation, often due to previous spam reports, can lead to emails being flagged.
* **Quality of Email Subject Line, Teaser, and Content**: Misleading or low-quality subject lines and content can trigger spam filters.
* **Quality and Safety of Links in Email**: Links to suspicious or unsafe websites increase the likelihood of emails being marked as spam.
* **Presence or Absence of Images**: Tiny tracking images or a lack of images can be red flags for spam filters.
* **Ratio of Images to Text and Links to Text**: An imbalanced ratio can look suspicious to spam filters.
* **Inclusion of Text Version of Email**: Emails without a plain text version may be flagged as spam.

***

### How to pass common spam filter tests

The goal of a phishing campaign is to test people, not to hack email filters. Since most of the time email filters are black boxes (we don't know what exactly is inside them), trying to bypass them with trial and error is time-consuming. Instead, we recommend whitelisting LUCY's domain or IP in your spam/email defense solution.

{% hint style="info" %}
Whitelisting is the most reliable method for ensuring email delivery. See [here](../../../guides/whitelisting-a-lucy-server/) for instructions.
{% endhint %}

If whitelisting isn't possible or for some reason isn't sufficient, here are some tips to improve your spam score or bypass filters:

**Use a domain you own to send:** The number one reason for email rejection is missing DNS entries, and the only way you can correct those entries is if you own and control the domain in question.

{% hint style="danger" %}
Reminder that you should _**never**_ send phishing content from your Lucy admin domain.

[Register](../../settings/common-system-settings/domains/) one or more other domains for that purpose instead.
{% endhint %}

**Set DNS records:** Use MX, SPF, PTR, and other records to authenticate your sending domain. Lucy also includes support for DKIM.

**Use an external mail server:** An external mail server with an established reputation can help to quickly avoid spam filters. Exercise caution using domains to send attack scenarios - all such domains are subject to reporting from your recipients and the domain's reputation may suffer as a result of too many reports.

**Set HELO/EHLO SMTP Host Name:** Create a valid server name for Lucy and ensure that the reverse DNS entry matches this name.

**Use descriptive text instead of URLs:** Embed your links in descriptive text instead of naked URLs.

**Use simple sender addresses:** Use clear, trustworthy "From" addresses like "contact@", "newsletter@", or "support@" instead of obscure or random names.

**Limit the number of URLs:** Spam filters are suspicious of emails with too many links, so try to only include a few. One link is usually enough for most emails.

**Use a unique subject line:** Include something unique to the recipient in the subject line. Lucy provides a number of variables that work well for this purpose.

**Avoid tracking images:** Tracking images increase spam score. If you notice emails being filtered by your spam tools try removing any tracking images.

**Decrease sending volume:** Sending large numbers of emails without throttling can trigger a spam response from the recipient mail server. Use the scheduler to slow down delivery.
