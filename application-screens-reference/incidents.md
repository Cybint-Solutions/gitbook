# Incidents

## Phishing Incidents Dashboard

The incidents dashboard centralizes the reporting and tracking of reported phishing incidents. It collects data on reported incidents, allowing security teams to analyze patterns, assess threat severity, and respond effectively.

## Dashboard Filters

The dashboard provides a streamlined interface for quickly identifying potential threats and taking appropriate actions. Use filters to group your incidents by date, client, campaign, and severity.

<figure><img src="../.gitbook/assets/image (722).png" alt=""><figcaption></figcaption></figure>

## Dashboard Actions

You can download or delete incidents straight from the dashboard, as well as forward them to your own reporting contacts.

## Centralized Analysis

The Centralized Analysis feature enables both manual and automatic analysis of reported emails. This allows the security team to efficiently assess and categorize threats, enhancing the overall email security posture.

{% tabs %}
{% tab title="Threat Summary" %}
The summary page displays a weighted average of the Mail Server, Domain, and Body Analysis scores, as well as general information about the reported email. You can also view or download the reported message as either a `.eml` or `.msg` file from this page.

<figure><img src="../.gitbook/assets/image (723).png" alt=""><figcaption></figcaption></figure>

The overall risk score is calculated using data from the following sources:

* Google Safebrowsing ([https://safebrowsing.googleapis.com/v4/threatMatches:find](https://safebrowsing.googleapis.com/v4/threatMatches:find))
* Phishtank ([http://data.phishtank.com/data/online-valid.csv](http://data.phishtank.com/data/online-valid.csv))
* DNS BL queries to `bl.spamcop.net`and `zen.spamhaus.org`
* CI Army ([http://cinsscore.com/](http://cinsscore.com/))
* Cybercrime tracker ([http://cybercrime-tracker.net/](http://cybercrime-tracker.net/))

{% hint style="info" %}
Reported emails from a LUCY campaign are automatically categorized as simulations, all others can be assigned a status to help keep your incidents organized.
{% endhint %}
{% endtab %}

{% tab title="Mail Server Analysis" %}
When an incident is reported, the Mail Server Analysis feature examines the mail servers involved in the email's transmission to see if any of them appear on a blacklist.

<figure><img src="../.gitbook/assets/image (717).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can use online tools like [https://mxtoolbox.com/blacklists.aspx](https://mxtoolbox.com/blacklists.aspx) or [https://www.virustotal.com/gui/home/url](https://www.virustotal.com/gui/home/url) to check if any of your mail servers have been blacklisted.
{% endhint %}
{% endtab %}

{% tab title="Domain Analysis" %}
When an incident is reported, all domains and IP addresses from the email header and body are extracted. LUCY then checks each IP and domain against public databases, such as Google's Safe Browsing and PhishTank, to identify any reported threats.

<figure><img src="../.gitbook/assets/image (710).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Body Analysis" %}
When an incident is reported, LUCY checks the body of the message against your [incident score factors](settings/submitted-email-settings/custom-rules-and-score-factors.md) and assigns a score accordingly. On this page you can view all the score factors and rules that contributed to the overall score.

<figure><img src="../.gitbook/assets/image (715).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

***

## AI-Powered Phishing Detection

{% hint style="success" %}
AI-powered phishing detection is available starting in Lucy version 5.5
{% endhint %}

Each reported email now includes a **Phishing Score** and additional insights to help with threat assessment:

* **Phishing Score**: A percentage score indicating the AI’s confidence that the email is phishing.
* **Insight Tooltips**: Hover over the score to view detailed probability breakdowns for:
  * Phishing URL
  * Phishing URL (Alternate)
  * Legitimate URL

<figure><img src="../.gitbook/assets/image (979).png" alt=""><figcaption></figcaption></figure>

These insights are generated automatically when the system processes a new report or when a user clicks **"Rescan"** on an existing report.

#### How it works

This feature uses a machine learning model to classify email content during parsing. It automatically activates under the following conditions:

* Your account has a **Commercial License**.
* The reported email is **not marked as a simulation** at the time of analysis.

**Important Behavior Notes:**

| Scenario                                  | AI Runs | Results Displayed |
| ----------------------------------------- | ------- | ----------------- |
| Commercial License                        | ✅ Yes   | ✅ Yes             |
| Free / Non-commercial License             | ❌ No    | ❌ No              |
| Report marked as simulation (before scan) | ❌ No    | ❌ No              |
| Report marked as simulation (after scan)  | ✅ Yes   | ❌ No              |

The AI analysis uses a specialized natural language processing model to evaluate the email content:

**Model Used**: `cybersectony/phishing-email-detection-distilbert_v2.4.1`\
This model predicts multiple probability values, including:

* Likelihood that the **email is phishing**
* Probability that a **URL is phishing**
* Probability that a **URL is legitimate**
* Analysis of **alternate URLs**

#### Running the model manually

You can run the model directly from the command line to analyze a local email file:

```bash
bashCopyEditpython3 scripts/phishing-detector/phishing-email-detection.py /path/to/email.txt
```

#### Sample Output:

```xml
xmlCopyEdit<PHISHING_PROBABILITY>4</PHISHING_PROBABILITY>
<PHISHING_URL>1</PHISHING_URL>
<PHISHING_URL_ALT>3</PHISHING_URL_ALT>
<LEGITIMATE_URL>2</LEGITIMATE_URL>
```

> Note: These are percentage probabilities represented as integers.\
> For example, `<PHISHING_PROBABILITY>4</PHISHING_PROBABILITY>` means 4% phishing confidence (i.e., 96% confidence the email is legitimate).

***

## Detecting Simulations

LUCY differentiates between real and simulation emails. Reports on simulation emails are included in campaign statistics, but depending on your plugin settings they do not have to be included in the incidents dashboard.

LUCY identifies simulation emails via headers that it includes with every simulation email it sends.\
For example:

```
X-LucyVictimURL ...
X-LucyAltVictimURL ...
X-LucyScenarioID 123
```

***

## Using Custom Plugins

The incident dashboard can be integrated into your organization's toolkit very easily. To use your own reporting plugin and still receive reports to the incident dashboard, follow these steps:

1. Configure your reporting domain’s MX records to point to LUCY.
2. Set an email address for receiving incident reports in the [plugin settings](https://app.gitbook.com/o/gJ3JHRuHpkD1JGxoFnyo/s/VYPsDfg76rUuy4DWfSsJ/~/changes/568/platform-reference/navigation-bar/settings/submitted-email-settings/plugin-settings).
3. Enable "Send Reports Over SMTP" and "Use SMTP for receiving incident reports on LUCY."

LUCY will listen on the reporter email's inbox and create incidents out of each email sent to that address.

{% hint style="warning" %}
Using "Send reports over SMTP" and "Use SMTP for receiving incident reports" will cause LUCY to intercept all its own emails to the reporter domain. In other words, recipients on the same domain as the reporter email will no longer receive any emails from LUCY.
{% endhint %}
