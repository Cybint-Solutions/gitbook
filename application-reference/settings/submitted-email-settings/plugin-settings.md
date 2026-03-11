# Plugin Settings

{% hint style="info" %}
Navigate to **Settings > Submitted Email Settings > Plugin Settings**
{% endhint %}

## Introduction

LUCY includes a "Phish Alert" plugin for various mail clients and browsers, enabling users to safely report suspicious emails with one click. The reported emails are analyzed by LUCY’s Threat Analyzer, enhancing the organization’s security by involving employees in proactive threat reporting.

The plugin has two main purposes:

1. **Forwarding Suspicious Emails**:
   * Users can forward emails to a predefined address (e.g., security team).
   * A [custom message](incident-autoresponder.md) appears to the user post-reporting.
2. **Reporting to LUCY**:
   * Suspicious emails can be sent back to LUCY for [analysis](custom-rules-and-score-factors.md).
   * LUCY-generated emails are processed in campaign statistics.

***

## Technical Details

* The plugin is an unsigned MSI file programmed as a C++/COM object and bundled with Microsoft Visual C++ 2015 Redistributable. Loading time is around 10ms.
* The Office 365 version always uses the system's built-in web browser to send data to LUCY.
* Both the XML (Office 365) and MSI (Outlook) versions can utilize system proxy settings (if present) without additional setup.

### Supported email clients

* &#x20;Office 365 (Desktop, Web, Mobile)
* Google Workspace (Gmail)

***

## Plugin Settings

#### Default Language

Set the plugin's default language.

#### Email

Add a list of emails to receive incident reports. Multiple emails can be separated by a semicolon (`;`).

#### Send reports over HTTP

If enabled, the plugin will send incident reports to LUCY over HTTP. If your Lucy domain has an SSL certificate, the report will be sent over HTTPs instead.

If this setting is not enabled, no incidents will appear in the [Incidents Dashboard](../../incidents.md).

**Phishing Incident Report Settings**

Choose one:

* **Always receive simulation reports** – All simulation reports sent to Lucy will be saved and included in the statistics.
* **Send report (update stats, don’t save)** – The plugin sends the report to Lucy, Lucy updates the report statistics, and then discards the report without saving it.
* **Do not send report** – The plugin will not send the report to Lucy at all, and statistics will not be updated. Only supported by the Outlook O365 plugin.

#### Enable MSI Plugin Authentication

You can optionally enable user authentication in your reporting workflow.

{% hint style="warning" %}
This option is not needed for most cases. Leave this setting disabled unless you know you need it.
{% endhint %}

#### Send reports over SMTP

If enabled, the plugin will send incident reports via SMTP to the list of emails defined in the Email setting above. If this setting is not enabled, no incident email reports will be sent.

#### Use SMPT for receiving incident reports

If enabled, incident reports will be sent to Lucy using SMTP.

{% hint style="warning" %}
To avoid duplicate incident reports, please select only one of the following methods:\
**Send Reports over HTTP** or **Use SMTP for receiving incident reports**.
{% endhint %}

{% hint style="danger" %}
When using **Send reports over SMTP** and **Use SMTP for receiving incident reports** together, LUCY will intercept all emails to the domains used for receiving the reports.

In other words, recipients on the same domains as the reporter emails will not receive any emails from LUCY.
{% endhint %}

**Phishing Incident Report Settings**

Choose one:

* **Always receive simulation reports** – All simulation reports sent to Lucy will be saved and included in the statistics.
* **Send report (update stats, don’t save)** – The plugin sends the report to Lucy, Lucy updates the report statistics, and then discards the report without saving it.
* **Do not send report** – The plugin will not send the report to Lucy at all, and statistics will not be updated. Only supported by the Outlook O365 plugin.

#### Send phishing simulations over HTTP

If enabled, the plugin will forward simulation emails over HTTP(s). Use this option if you want to ignore simulation emails in your incidents dashboard, but still want the report to be included in campaign stats.

#### Use X-Headers in forwarded emails

If enabled, the plugin will add a header to the forwarded email:

```
X-CI-Report: True
```

It will also add this HTML to the body of the message:

```
<p>X-CI-Report: True</p>
```

#### Inline Message Forwarding

If enabled, the plugin will clear the body of the email before forwarding.

#### Deeper Analysis Request

If enabled, users will see a popup asking whether they want to request deeper analysis of the reported phishing email (supported only in O365 and MSI plugins).

#### Deeper Analysis Comment

If enabled, the plugin will add a comment field to the report UI.\
Only supported in the MSI plugin.

#### Send reported mail attachment in EML format

By default, emails are forwarded in `.msg` format. Enable this setting to forward them as `.eml` instead.

#### Disable Autorepsonder for Reports

If enabled, LUCY will not send any [automatic response](incident-autoresponder.md) to reporters.

#### Actions for reported emails

When an email is reported, the plugin will do one of the following:

* Delete the reported email.
* Move reported email to a folder.
  * You can specificy a folder with this setting, but the folder must already exist.
* Move reported email to the Junk Folder.

#### Notify of expired incidents

Enable this setting to receive notification if there are reports older than 30 days.

#### Anonymous simulation reporting

When enabled, all phishing simulation reports will be marked as anonymous. The reporter's email and message content will not be saved or displayed.

{% hint style="success" %}
Anonymous simulation reporting is only available in Lucy version 5.6 and up.
{% endhint %}

#### Anonymous phishing reporting

When enabled, all real phishing reports (i.e., not simulations) will be marked as anonymous. The reporter's email and message content will not be saved or displayed.

{% hint style="success" %}
Anonymous phishing reporting is only available in Lucy version 5.6 and up.
{% endhint %}

## UI Settings

Configure these settings in the **Language** tab.

<table><thead><tr><th width="179">Setting</th><th width="364.77777099609375">Description</th><th>Outlook/O365/Gmail</th></tr></thead><tbody><tr><td>Language</td><td>Choose the language preset to configure it specifically for the needed language.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>Ribbon Label</td><td>The name of the area in the ribbon where the button appears.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Success Message Body</td><td>The body of the message displayed after successfully reporting an email.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Success Message Title</td><td>The title of the message displayed after successfully reporting an email.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Success Message Button</td><td>The text displayed on the button after successfully reporting an email.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Success Mmessage Body</td><td>The body of the message displayed after successfully reporting an email.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Report Button Text</td><td>The text displayed on the report button.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Report Button Sub-Text</td><td>The sub-text displayed on the report button.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Report Title</td><td>The title of the message displayed after clicking the report button.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Error Title</td><td>The title of the message displayed when any error occurs.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Send Error Message</td><td>The message displayed when an issue with sending the report occurs.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>User Request Message</td><td>The message displayed after marking a suspected phishing email and clicking the report button.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Deeper Analysis Request Message</td><td>The message displayed after clicking the report button for deeper analysis.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Deeper Analysis Request Title</td><td>The title of the message displayed after clicking the report button for deeper analysis.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>Subject</td><td>The subject of the forwarded email message when sending a report over SMTP.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td>For "Yes" Action</td><td>Set the action for "Yes" in the Deeper Analysis Request.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr><tr><td>For "No" Action</td><td>Set the action for "No" in the Deeper Analysis Request.</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span>/<span data-gb-custom-inline data-tag="emoji" data-code="274c">❌</span></td></tr></tbody></table>
