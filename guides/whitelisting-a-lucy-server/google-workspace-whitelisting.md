# Google Workspace Whitelisting

Several options in Google Workspace can be adjusted to improve the phishing simulation experience with Lucy. Follow the steps below to whitelist emails and ensure they are not flagged as spam.

***

### **Whitelisting Emails from Lucy**

**Log into Google Admin Console:**

* Go to [admin.google.com](https://admin.google.com).
* Navigate to "Apps".
* Navigate to Google Workspace
* Click on "Gmail".

<figure><img src="../../.gitbook/assets/image (679).png" alt=""><figcaption></figcaption></figure>

* Scroll to the bottom and select "Spam, phishing, and malware".

<figure><img src="../../.gitbook/assets/image (680).png" alt=""><figcaption></figcaption></figure>

* Add Lucy's IPv4 address to the "Email Allowlist".
* Click "Save".

<figure><img src="../../.gitbook/assets/image (747).png" alt=""><figcaption></figcaption></figure>

***

### **Bypassing Spam by Email Header**

To ensure emails from Lucy are not flagged as spam, configure Google Workspace to bypass spam detection based on specific email headers.

{% hint style="warning" %}
If you whitelist using this method, [test emails](../../application-screens-reference/support/system-tests/test-email.md) will still not arrive because it will not contain these campaign headers.
{% endhint %}

**Compliance Settings:**

* Go back to -> Google Workspace -> Gmail - Scroll to the bottom and select "Compliance".

<figure><img src="../../.gitbook/assets/image (750).png" alt=""><figcaption></figcaption></figure>

Scroll down to "Content Compliance"

* Click "Configure".

<figure><img src="../../.gitbook/assets/image (751).png" alt=""><figcaption></figcaption></figure>

**Add Compliance Rule:**

* Add a description (e.g., "Lucy Email Phishing").
* Check "Inbound" and "Internal - receiving".
* Select "If ANY of the following match the message".

<figure><img src="../../.gitbook/assets/image (752).png" alt="" width="563"><figcaption></figcaption></figure>

* Click "Add" → Advanced content match → Headers + Body → Contains text.
* In "Content", input your Lucy X-Mailer Header (default is "X-Lucy-VictimUrl") and click "Save".

<figure><img src="../../.gitbook/assets/image (753).png" alt="" width="563"><figcaption></figcaption></figure>

* Scroll down to the "Spam" section and activate "Bypass spam filter for this message".
* Click "Save".

<figure><img src="../../.gitbook/assets/image (754).png" alt="" width="563"><figcaption></figcaption></figure>

***

### **Addressing Suspicious Link Issues**

Sometimes, a warning pop-up window appears when trying to open a link from a Lucy email. To mitigate this:

**Enable SSL in Lucy Campaign:**

* Ensure SSL is enabled in your Lucy campaign.

{% hint style="info" %}
Refer to our platform reference article on [campaign SSL settings.](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#ssl-settings)
{% endhint %}

**Consider a Paid Certificate:**

* If the Let's Encrypt certificate is not sufficient, consider obtaining a paid certificate. Contact any SSL vendor you prefer and [upload your SSL certificate](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#generate-or-upload) to the campaign.

***

### **Disable Warning Prompts:**

If issues persist, you can disable the warning prompt for links to untrusted domains in Google Workspace. Follow these steps:

* Log into [admin.google.com](https://admin.google.com).
* Navigate to "Apps".
* Select "Google Workspace".
* Go to "Gmail".
* Select "Safety".
* Go to "Links and external images".
* Deactivate "Show warning prompt for any click on links to untrusted domains".
* Click "Save".
