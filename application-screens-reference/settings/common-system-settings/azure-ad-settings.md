# Azure AD Settings

### Introduction

After successfully synchronizing Lucy with your [Azure app registration](azure-applications.md), the next step involves configuring how Lucy will automate the importation process for Administrative users and End users within Azure AD Settings.

### Configuration

{% hint style="info" %}
Navigate to Settings -> Common System Settings -> Azure AD Settings
{% endhint %}

On the next page, enable "Autoupdate Azure AD users"

<figure><img src="../../../.gitbook/assets/image (304).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Name" %}
Add a name for your specific Azure preference.
{% endtab %}

{% tab title="Client" %}
This is the client associated with the Azure app registration. Lucy ensures data segregation on a client basis, meaning that all data is containerized within the respective client. This setup guarantees that the app integration remains accessible solely to administrative users for the specified client. Moreover, it enables Managed Security Service Providers (MSSPs) and Partners to integrate multiple Azure tenants for their respective clients, further enhancing security and customization.
{% endtab %}

{% tab title="Azure Application" %}
Select the specific [Azure Application](azure-applications.md).
{% endtab %}

{% tab title="Action for New Users" %}
* **Automatically add:** When new users are detected in Entra ID, they are automatically added to pre-defined campaigns within Lucy. This ensures new users are immediately included in ongoing training or phishing simulation campaigns.
* **Waiting for administrator's decision:** When new users are added to the Entra ID directory, Lucy will not automatically take any action. Instead, an administrator must manually decide to approve the new user to be added to the relevant campaigns. The approval of Recipients/Users is collected on the Recipient/User control list - see the below table "**Azure Preferences Continued**" as a reference.
{% endtab %}

{% tab title="Action for Deleted Users" %}
1. **Automatically Delete Inactive:** If this option is selected, Lucy will automatically remove user accounts that are no longer active in the Entra ID directory. This ensures that Lucy's user database is current and that inactive users do not remain part of ongoing campaigns or receive notifications.
2. **Waiting for Administrator's decision:**  If this option is selected when a user is deleted from the Entra ID directory, Lucy will not immediately take any action. Instead, the system will flag the user for review, and an administrator will need to decide on the appropriate action, such as whether to delete the user from Lucy or perhaps keep them in the database for reporting or historical purposes. The approval of Recipients/Users is collected on the Recipient/User control list - see the below table "**Azure Preferences Continued**" as a reference.
{% endtab %}

{% tab title="Importing" %}
Lucy permits administrators to configure Azure preferences for individual or multiple user groups by activating the required "roles" selection option.\
\
For instance, to configure the preference for automatically importing users with the Enduser role, you would select the "Import Enduser role" option and specify the necessary group/s associated with the End User role:\
\


<figure><img src="../../../.gitbook/assets/image (180).png" alt=""><figcaption></figcaption></figure>

This process can be repeated for all other "Role" importation options.
{% endtab %}
{% endtabs %}

### Azure Preferences Continued

After defining your Azure preferences, if you return to the settings by navigating to Settings -> Common System Settings -> Azure AD Settings, you will find three selectable actions available to you:

<figure><img src="../../../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Import Users From Azure AD" %}
This tab enables you to manually filter and import your chosen users from Entra ID, effectively overriding the pre-set Azure AD preferences.

Select the Role, Azure Application, and Group filter:

<figure><img src="../../../.gitbook/assets/image (178).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Recipient Control List" %}
This tab presents the administrator with a list of recipients awaiting importation. These are specifically the recipients who were added to the Import Settings under [Recipient Groups](../../users/recipient-groups.md), marked with the option "Waiting for Administrator's decision."

<figure><img src="../../../.gitbook/assets/image (174).png" alt=""><figcaption></figcaption></figure>

The above users will be in a pending status on the Recipient control list waiting for the administrator to approve the importation of recipients from Entra ID.

<figure><img src="../../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="User Control List" %}
If you have enabled the option for "Action for new users" and selected "Waiting for administrator's decision" then all pending users will be listed here.

<figure><img src="../../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

The "Event" column indicates the status of each user, categorizing them as either a "New User" or a "Deleted User." You have the option to apply the event to users on an individual basis or select all users at once to apply the event in bulk.

<figure><img src="../../../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Technically, an End-User and a Recipient refer to the same identity in Lucy, though they are distinguished based on the required function for the identity. If the user needs access to the End-user portal, these identities are referred to as "End-users." Conversely, if the user will not have access to a dedicated End-user portal, then these identities are considered as recipients.
{% endhint %}
{% endtab %}
{% endtabs %}



