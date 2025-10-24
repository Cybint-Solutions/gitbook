# Advanced Settings

## Filter Settings

Filters can be pre-defined and updated in the [Response Filte](../../../settings/common-system-settings/filter-settings.md)[rs ](../../../settings/common-system-settings/filter-settings.md)section of the platform to enable quick filter selection in campaigns.

## User Settings

User Settings allow you to add an [Administrative User](../../../users/administrative-users.md) with the **User** role to a campaign. This is ideal for including stakeholders in the campaign, ensuring they are bound by their respective [client](../../../settings/clients/) for data isolation and are given only the necessary permissions to view or make minor changes to the campaign configuration.

{% hint style="success" %}
Administrative users with **Access All Campaigns** will automatically have access to campaigns for their client.
{% endhint %}

### Adding Users

Select **Add User** to add a User to your campaign.

<figure><img src="../../../../.gitbook/assets/image (1034).png" alt=""><figcaption></figcaption></figure>

### User Permissions

| Permission                                    | Description                                                   |
| --------------------------------------------- | ------------------------------------------------------------- |
| Start/Stop Campaign                           | Start and stop the campaign.                                  |
| Configure Campaign Settings                   | Configure campaign settings.                                  |
| Delete Campaign                               | Delete the campaign                                           |
| Edit Recipients                               | Edit the recipient list(s)                                    |
| Edit Awareness Website                        | Edit the awareness content                                    |
| Edit Schedule                                 | Edit the email schedule                                       |
| Edit Base Scenario Settings                   | Edit the Base scenario settings                               |
| Edit Scenario (Settings/Landing Page/Message) | Edit the settings for each scenario                           |
| Reports (Create/View)                         | Create and download reports                                   |
| Export (File/Group)                           | Export recipients and data                                    |
| Campaign Statistics (Full/Base)               | View individual (full) and/or aggregate (base) campaign stats |
| Reset Stats                                   | Reset campaign stats                                          |
| Message Log                                   | View the campaign email log                                   |
| Supervision Log                               | View the campaign supervision log                             |
| Reminders                                     | Edit/configure reminders                                      |
| Responses                                     | View/manage campaign responses                                |

***

## Custom Fields

Beyond the common statistical data in LUCY, such as link clicks and submitted form data, you might want to track additional custom statistics from a live campaign. These custom statistics can provide deeper insights into user behavior and response to phishing campaigns.

{% hint style="info" %}
Custom Statistics require per-recipient manual intervention, making them ideal for manually tracking specific statistics that do not apply to the general group.
{% endhint %}

#### Examples of custom statistics

* CERT (Computer Emergency Response Team) responses from users.
* Users who replied to the attacker.
* Users who participated in security training programs prior to the phishing campaign.

### Adding Custom Fields

Select **Add** to add a custom field to your campaign.

<figure><img src="../../../../.gitbook/assets/image (1035).png" alt=""><figcaption></figcaption></figure>

### **Tracking Custom Field Statistics**

Custom statistics must be tracked manually:

* **Go to Campaign Statistics**
  * &#x20;**Campaign Name** → **Statistics** → **Recipients**
* **Select Recipients**
  * Choose the recipient(s) who "Completed Office Security Webinar".
* **Activate Custom Fields**
  * The custom field(s) will appear as a checkbox next to the recipient's information. Activate the checkbox for  "Completed Office Security Webinar".

<figure><img src="../../../../.gitbook/assets/image (495).png" alt=""><figcaption></figcaption></figure>

***

## Campaign List Settings

These settings control how the campaign appears and behaves in the campaign dashboard.

<figure><img src="../../../../.gitbook/assets/image (1037).png" alt=""><figcaption></figcaption></figure>
