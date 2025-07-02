# User Settings

### Introduction

The "User Settings" tab allows you to add an [Administrative User](../../../users/administrative-users.md) with the role of "**User**" to a campaign and set the desired permissions. This is ideal for including stakeholders in the campaign, ensuring they are bound by their respective [client](../../../settings/clients/) for data isolation and are given only the necessary permissions to view or make minor changes to the campaign configuration.

### Configuration

{% hint style="info" %}
Navigate to **Campaign -> Advanced Settings -> User Settings**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (503).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Please note, Administrative users with permission assigned "**Access All Campaigns**" will automatically be added to campaigns for their respective client.
{% endhint %}

Select "Add User" to add an Administrative User with role = User to your campaign.

<figure><img src="../../../../.gitbook/assets/image (504).png" alt=""><figcaption></figcaption></figure>

### User Permissions

Defines the specific capabilities granted to the user within the application.

* **Select All**
  * **Description:** Grants all available permissions to the user.
  * **Example:** Check this box to give "Billy Joel" full access to all features and settings.
* **Start/Stop Campaign**
  * **Description:** Allows the user to start and stop email campaigns.
  * **Example:** Useful for campaign managers who need to control the timing of campaigns.
* **Configure Campaign Settings**
  * **Description:** Enables the user to configure campaign settings.
  * **Example:** Suitable for users responsible for setting up campaign-specific parameters like a mail Administrator to obtain DKIM records.
* **Delete Campaign**
  * **Description:** Allows the user to delete campaigns.
  * **Example:** Important for administrators who need to manage and clean up outdated or incorrect campaigns.
* **Edit Recipients**
  * **Description:** Permits the user to edit the list of recipients for campaigns.
  * **Example:** Useful for HR or IT personnel who manage recipient lists.
* **Edit Awareness Website**
  * **Description:** Enables the user to edit the awareness website content.
  * **Example:** Suitable for content managers who update training materials.
* **Edit Schedule**
  * **Description:** Allows the user to edit the campaign schedule.
  * **Example:** Ideal for scheduling managers who need to adjust campaign timings.
* **Edit Base Scenario Settings**
  * **Description:** Permits the user to edit the base settings of scenarios.
  * **Example:** Useful for technical staff who configure scenario parameters.
* **Edit Scenario Settings**
  * **Description:** Enables the user to edit specific scenario settings.
  * **Example:** Appropriate for red team members who tailor attack scenarios to different user groups.
* **Edit Scenario Landing Page**
  * **Description:** Allows the user to edit the landing pages used in scenarios.
  * **Example:** Important for web designers who customize landing pages for better user engagement.
* **Edit Scenario Message**
  * **Description:** Permits the user to edit the messages used in scenarios.
  * **Example:** Suitable for red team members who craft phishing and awareness messages.
* **Create/View Reports**
  * **Description:** Enables the user to create and view reports.
  * **Example:** Essential for analysts who need to review campaign effectiveness.
* **Export to File**
  * **Description:** Allows the user to export data to a file.
  * **Example:** Useful for users who need to share data with external systems or stakeholders.
* **Export to Group**
  * **Description:** Permits the user to export data to a group.
  * **Example:** Ideal for administrators who manage security awareness programs.
* **Campaign Full Statistics**
  * **Description:** Grants access to full campaign statistics.
  * **Example:** Important for users who require detailed insights into campaign performance.
* **Campaign Basic Statistics**
  * **Description:** Grants access to basic campaign statistics.
  * **Example:** Suitable for stakeholders who need an overview of campaign performance without detailed data.
* **Reset Stats**
  * **Description:** Allows the user to reset campaign statistics.
  * **Example:** Useful for administrators who need to clear and restart campaign data.
* **Access Message Log**
  * **Description:** Permits the user to access the message log.
  * **Example:** Important for technical staff who troubleshoot email delivery issues.
* **Supervision Log**
  * **Description:** Enables the user to access the supervision log.
  * **Example:** Useful for supervisors who need to monitor and approve campaign activities.
* **Reminders**
  * **Description:** Allows the user to manage reminders.
  * **Example:** Suitable for users who send follow-up reminders to recipients.
* **Responses**
  * **Description:** Permits the user to manage responses.
  * **Example:** Important for users who handle recipient feedback and responses to campaigns.

#### Example Use

For "Billy Joel," if he is a campaign manager responsible for running and monitoring security awareness campaigns, you might assign permissions such as "Start/Stop Campaign," "Configure Campaign Settings," "Create/View Reports," and "Campaign Full Statistics." This ensures he has the necessary access to manage and analyze the campaigns effectively without granting excessive permissions.
