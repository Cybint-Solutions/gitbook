# Base Settings

## General Info

<figure><img src="../../../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

### Campaign Name and Client

Give the campaign a descriptive name and assign a [client](../../../settings/clients/).\
These will be visible in the campaign dashboard and reports.

### Type

{% hint style="success" %}
This setting will change which steps must be **finalized** before the campaign can run.
{% endhint %}

**Awareness Education** - a campaign with only training materials.\
**Attack Simulation** - a campaign with only an attack simulation.\
**Attack Simulation & Awareness Education** - a campaign with linked attack and awareness.

### Stop Options

Configure an automatic stop date for the campaign. This setting is optional.

## Campaign Parameters

<figure><img src="../../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

### Industry (Benchmark Sector)

This field is used to benchmark the campaign against average values in the selected industry. For more on benchmarking read [here](../../../settings/benchmark-sectors.md).

### Notes

A section for admin notes on the campaign. This does not appear on the campaign report.

## Save & Finalize

Select **Save Progress** at the bottom of the screen to apply your changes. When you're ready to start the campaign, select **Finalize Step** to let Lucy know these settings are correc&#x74;**.**

{% hint style="success" %}
**Finalize Step** does not prevent you from changing settings!\
This step is just to let Lucy know that the campaign can be unlocked and started.
{% endhint %}

<details>

<summary>Awareness Re-Scheduling</summary>

Enable if you wish to allow recipients to reschedule their awareness training.

Once this option is enabled, a popup will appear in the user's browser, allowing them to reschedule the training for a specific date. The email will then be resent on the selected date.

![](<../../../../.gitbook/assets/image (53) (1).png>)



</details>

<details>

<summary>Ignore Repeated Answers in Awareness</summary>

If you include awareness training, you can specify that only the first response to an exam or quiz is recorded, and any repeated attempts will be ignored.

</details>

<details>

<summary>End-User Profiles Enabled</summary>

Users may not always have time to complete an awareness course right away. They have the option to reschedule the training, or alternatively, you can establish a dedicated portal for your end users. This portal enables them to log in and access their custom training links at any time, eliminating the need to resend an awareness email.

**Security considerations for access include:**

1. **Plain Text Password:** Sent only once as an attachment with the recipient's first awareness training email.
2. **Password Reset Link:** Can be included in the awareness email, allowing the user to configure a password upon initial login.
3. **Login with SSO:** Users can log in using their organization's Identity Provider (IDP). Ensure to [set up SSO](../../../settings/common-system-settings/sso-configuration.md) prior to launching the campaign to facilitate this feature.

</details>

<details>

<summary>Tracking</summary>

Enable this feature to refine your campaign statistics by monitoring email responses:

**Track Bounced Emails** Determine which recipients did not actually receive the email, such as those with 'out of office' or bounced email responses.

**Interval Email Testing** Enhance the reliability of your campaign by scheduling periodic email tests. This involves sending emails to a predefined address at set intervals to verify ongoing mail delivery success. This helps track and ensure the health of your campaign's email system.

</details>

<details>

<summary>Campaign Stop</summary>

**Stop the Campaign Automatically:** If this setting is enabled, the campaign will automatically stop on the specified date. After this date, no further emails will be sent, and campaigns with landing pages will no longer be accessible. This function allows you to set a definitive end date for the campaign's active phase.

**Send a Report When You Stop the Campaign:** When enabled, this feature automatically sends you a report upon the campaign’s conclusion. Ensure that you have configured the appropriate [report template](../../../templates/report-templates.md) in advance to receive a comprehensive summary of the campaign’s performance and outcomes. This automated report helps in evaluating the effectiveness of the campaign without manual intervention.

</details>

<details>

<summary>Pinned / Delete Protection</summary>

**Pinned Campaigns:** "Pinned campaigns" function similarly to browser favorites, allowing you to group various campaigns within a specific view for easy access. Once you activate the "pinned" checkbox for a campaign, it will appear in the designated frame on the dashboard. This feature helps you quickly navigate to and manage your most important or frequently accessed campaigns.

**Delete Protection:** Delete protection provides a safety net against data loss, ensuring that your campaign information is preserved by disabling the delete function for this campaign in the user interface.

</details>

<details>

<summary>Anonymous Mode</summary>

Use this mode to conceal all victim data from statistics and reports, ensuring privacy and anonymity in the data handling process. Please be aware that once this operation is performed, it cannot be undone. This permanent setting is crucial for campaigns where confidentiality is a priority.

</details>

<details>

<summary>Suppress Duplicate Recipients</summary>

Lucy reviews incoming emails from the new group, specifically those already listed as recipients in the campaign. This option disables the addition of new recipients for individuals whose emails are already included in the campaign.

</details>

<details>

<summary>Antivirus/Firewall Protection Interval</summary>

In some cases, remote firewalls, spam filters, or virus filters may automatically scan all the URLs within a link. This can lead to false positives, causing LUCY to register all link clicks as successful. To prevent this issue caused by third-party applications, you can activate the antivirus/firewall protection feature. This will prompt LUCY to disregard all GET requests for the initial 30/60/90/120 seconds, thus minimizing the impact of automatic link scanning.

</details>

<details>

<summary>Enable SSO for Awareness Websites</summary>

This feature enables you to generate a static link for the awareness website. It proves beneficial when you don't require individual email messages for each user, opting instead to distribute a single link through alternative channels. This unique link accessed via the organization's Identity Provider, remains specific to the context of a particular awareness scenario and campaign, ensuring targeted dissemination.

</details>
