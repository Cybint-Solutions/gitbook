# Troubleshooting FAQs

## Email Delivery Issues

#### **Why are my phishing emails not being delivered?**

Common causes include:

* SPF/DKIM records not configured correctly
* Sending domain or IP on a blacklist
* Recipient mail gateway blocking simulated phishing emails
* Missing allowlist entries for the Lucy server

Recommended checks:

1. [Verify SPF and DKIM for the sending domain](application-reference/settings/common-system-settings/domains/#dns-records-explained)
2. [Confirm the attack domain is not blacklisted](guides/manage-blacklisted-domains/)
3. [Ensure the recipient email gateway allowlists the Lucy server](guides/quick-guides/create-your-first-campaign/whitelisting.md)
4. [Check the Lucy mail queue and server logs](application-reference/support/system-logs.md#how-to-view-mail-and-web-server-logs)

***

#### **Why are phishing emails landing in spam?**

Possible causes:

* Missing SPF/DKIM/DMARC configuration
* Low domain reputation
* Suspicious phishing template content
* Security filters detecting simulation behavior

Mitigation:

* [Configure proper DNS authentication records](application-reference/settings/common-system-settings/domains/#dns-records-explained)
* Use warmed-up domains
* Avoid common phishing keywords in early test campaigns
* [Allowlist the sending domain internally](guides/quick-guides/create-your-first-campaign/whitelisting.md)

***

#### **Why are users not receiving campaign emails?**

Check the following:

* [The campaign schedule is valid](application-reference/campaigns/campaign-settings/configuration/schedule/) (if in use)
* The recipient group contains valid email addresses
* [SMTP configuration is correct](application-reference/settings/common-system-settings/smtp-servers.md) (if in use)
* Email rate limits or throttling are not blocking delivery

***

## Campaign Issues

#### Why won’t my campaign start?

Before a campaign can start, Lucy runs a series of [**automatic campaign checks**](application-reference/campaigns/campaign-settings/starting-a-campaign.md#campaign-checks) to confirm that the campaign configuration and infrastructure are working correctly. If any required check fails, the campaign will not launch.

If a check fails, Lucy will display a **red error indicator** in the campaign checks panel. Warnings may appear in **yellow** if a potential issue is detected but does not completely block the campaign.

#### How to resolve it

1. Open the campaign and review the **Campaign Checks** section
2. Identify any failed checks (shown in red)
3. Click the check to view details about the problem
4. Correct the configuration issue and start the campaign again

{% hint style="info" %}
Running a **small internal test campaign** before launching a full campaign can help identify configuration problems early.
{% endhint %}

***

#### **Why are campaign results empty?**

This usually occurs when:

* Emails were never delivered
* Tracking links were blocked by security gateways
* Tracking domain not configured correctly
* User activity was filtered by browser security settings

***

#### **Why are clicks or credential captures not being recorded?**

Possible causes:

* Tracking domain misconfiguration
* [DNS for the phishing domain incorrect](application-reference/settings/common-system-settings/domains/#dns-records-explained)
* Proxy or email security solution rewriting links
* Browser blocking tracking scripts

***

#### Why do I see incorrect information in my campaign statistics?

Possible causes:

* Firewall, antivirus, or email security tools intercepting packets
* Recipients sharing links

Mitigation:

* [Whitelist your Lucy server and email senders](guides/quick-guides/create-your-first-campaign/whitelisting.md)
* [Use system filters to ignore false-positive clicks](application-reference/settings/common-system-settings/filter-settings.md)
* [Enable the End User Portal to provide individual access to training content](application-reference/users/end-users/end-user-portal-overview.md)

***

## Domain & DNS Problems

#### **Why do I need a separate phishing domain?**

Using a separate domain prevents the primary Lucy server domain from being blacklisted during phishing simulations.

***

#### **Why is my attack domain not working?**

Common causes:

* [DNS A record not pointing to the Lucy server](application-reference/settings/common-system-settings/domains/#dns-records-explained)
* [SSL certificate missing or invalid](application-reference/settings/common-system-settings/ssl-settings/)

Verification steps:

1. Confirm DNS resolves to the Lucy server
2. [Verify SSL certificate installation](application-reference/settings/common-system-settings/ssl-settings/)

***

#### **Why did my phishing domain get blacklisted?**

Possible reasons:

* High-volume campaigns sending emails too quickly
* Suspicious phishing templates triggering automated scanners
* Users reporting the campaign content

Mitigation:

* [Use the campaign scheduler to spread campaign emails over a longer period](application-reference/campaigns/campaign-settings/configuration/schedule/)
* [Whitelist your lucy server](guides/quick-guides/create-your-first-campaign/whitelisting.md)
* [Use the reporting plugin to send suspicious email reports directly to Lucy](guides/reporting-plugin/)

#### Why does my browser report an expired SSL certificate after renewal?

Common causes:

* Cached files in the browser
* An intermidate service is still hosting the old SSL certificate

Check:

* Clear your browser cache or open the page in a private browsing session.
* Ensure the current SSL files are loaded in any intermediate servers such as proxies and load balancers.

***

## Reporting Plugin Issues

#### **Why don't I see the report button in my mail client?**

Possible causes:

* Your clients have not yet synced with the domain controller
* Incorrect configuration of the Entra ID application

Check:

* Wait up to 90 minutes to allow clients to sync with the domain controller
* [Validate your application config in Entra ID](guides/reporting-plugin/deploying-office-365.md)

#### **Why are phishing reports not appearing in the incidents dashboard?**

Possible causes:

* Reporting plugin not installed correctly
* Email forwarding rules missing
* Mailbox integration misconfigured

***

#### **Why do reported phishing emails not appear in Lucy?**

Check:

* [The reporting mailbox is configured](application-reference/settings/submitted-email-settings/plugin-settings.md)
* Communication between Lucy and clients is allowed
  * If using HTTPs for reports, check whitelisting over port 443
  * If using SMTP for reports, check whitelisting over port 25

***

## Installation & System Issues

#### **Lucy installation failed. What should I check?**

Verify:

* [Supported Linux version](guides/installing-lucy/system-requirements.md)
* [Firewall rules allowing required ports](guides/installing-lucy/network-communication.md)
* [Sufficient system resources (RAM, disk space)](guides/installing-lucy/system-requirements.md)

***

#### **Lucy is running slowly. What could cause this?**

Common performance issues:

* Insufficient server RAM
* Large campaign datasets
* Database performance issues
* Background workers not running

{% hint style="info" %}
VPS customers should contact Support for help investigating such issues.
{% endhint %}

***

#### **How do I check Lucy system logs?**

[VPS customers can find their logs in the workstation under **Support > System Logs > Service Logs**.](application-reference/support/system-logs.md)

On-premise customers can find their logs in various locations in the container:

* Apache logs: `/var/log/apache2`&#x20;
* Mail logs: `/var/log/mail.log`
* Application logs: `/opt/phishing/runtime`&#x20;

#### How can I clear up storage space?

If you need to make room for new templates, updates, or custom files, you can quickly and safely remove unused templates via the [system monitoring](application-reference/support/status/system-monitoring.md) page:

<figure><img src=".gitbook/assets/image (1056).png" alt=""><figcaption></figcaption></figure>

Select **Clear** to delete all templates that are not currently in use by any campaign.

{% hint style="info" %}
Awareness templates are usually larger than other files because they contain larger assets like videos and images. If you need to clear up space, awareness templates are usually the best place to start.
{% endhint %}

***

## Administrative Configuration

#### **Why can’t I change the system timezone?**

The timezone cannot be modified while scheduled campaigns are active. Stop scheduled tasks before making the change.

***

#### **Why are some settings locked or unavailable?**

This can happen when:

* Campaigns are actively running
* [Administrator permissions are limited](application-reference/users/administrative-users.md#administrative-permission-list)
* Certain modules are not licensed or enabled
