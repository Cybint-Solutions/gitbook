# Base Settings



<figure><img src="../../../../.gitbook/assets/image (51).png" alt="" width="563"><figcaption></figcaption></figure>

<details>

<summary>Campaign Name</summary>

Assign a name to your campaign; this will be visible on the dashboard.

</details>

<details>

<summary>Client</summary>

Lucy's architecture uses a client framework to manage information, where each client acts as a container for elements like campaigns, templates, and user access. This setup allows for data segregation and enhanced security, ensuring data integrity and confidentiality.&#x20;

The client can be tailored to fit various scenarios; a single client suffices for an individual organization, while managing multiple organizations necessitates distinct clients for each, allowing for customized control and security per organization.

</details>

<details>

<summary>Setup Mode</summary>

The Setup Mode determines how your campaign is configured: either as new or from pre-defined templates.

**Expert Setup (Manual Configuration)**: This is the default setting for creating a blank campaign using Expert mode.

**Start with Default Campaign Template**: This option allows administrators to begin with a pre-configured campaign template that has been saved in the campaign template directory.

**Mail & Web Test**: This scenario template is necessary for the Mail & Web Filter test, enabling you to identify what types of files can be accessed within the company network through mail or web channels.

</details>

<details>

<summary>Industry</summary>

You can set a benchmark for a campaign when initiating it. Benchmarks allow you to compare results across different campaigns and sectors, particularly useful if you use LUCY for conducting phishing campaigns for multiple clients. The benchmarking uses an internal database; no data is ever submitted to our servers.&#x20;

If you are using LUCY for the first time, you will be asked once if you wish to participate in submitting anonymous data. By default, no anonymous data is submitted, and your choice is stored in the advanced settings.

By default, the industry field is empty. The more tests you conduct, the easier it will become to compare results if you set a benchmark for each test. Benchmark results are not shared across different LUCY installations, and no campaign data is transmitted to external servers.

**Editing Benchmark Values**

Your benchmark values can be edited under "Users -> Benchmark Sectors".

**How to Add Custom Sectors**

You can add new benchmark sectors by clicking on the "new" button at the top right of the sector list.

<img src="../../../../.gitbook/assets/image (52).png" alt="" data-size="original">

</details>

<details>

<summary>Notes</summary>

Add any internal comments or reminders about the campaign.

</details>

<details>

<summary>Awareness Re-Scheduling</summary>

Enable if you wish to allow recipients to reschedule their awareness training.

Once this option is enabled, a popup will appear in the user's browser, allowing them to reschedule the training for a specific date. The email will then be resent on the selected date.

![](<../../../../.gitbook/assets/image (53).png>)



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

**Track Bounced Emails** This function intercepts all emails sent to the campaign's sender email address and its domain. To facilitate this, the sender email domain's MX records should be configured to point to the current Lucy server. This setup ensures that emails directed to this domain are captured by Lucy for monitoring purposes.

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
