# LDAP Settings

### Introduction

After successfully integrating your Lucy server with your [LDAP server](ldap-servers/), the next step is to fine-tune the LDAP preferences within Lucy.&#x20;

{% hint style="info" %}
You can only associate one LDAP preference for a single LDAP server listed
{% endhint %}

{% hint style="info" %}
Navigate to Settings -> Common System Settings -> LDAP Settings
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (286).png" alt=""><figcaption></figcaption></figure>

Select "Add New LDAP Preferences"

On the next page, enable "Autoupdate LDAP users"

<figure><img src="../../../.gitbook/assets/image (287).png" alt="" width="375"><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Name" %}
Add a name for your specific LDAP preference.
{% endtab %}

{% tab title="Client" %}
Associate this preference with a specific client to ensure data segregation among multiple clients.
{% endtab %}

{% tab title="LDAP Server" %}
Select the specific LDAP server you have configured in [LDAP Servers](ldap-servers/).
{% endtab %}

{% tab title="Action for New Users" %}
* **Automatically add to bounded campaigns:** When new users are detected in the LDAP server, they are automatically added to pre-defined campaigns within Lucy. This ensures new users are immediately included in ongoing training or phishing simulation campaigns.
* **Waiting for administrator's decision:** When new users are added to the LDAP directory, Lucy will not automatically take any action. Instead, an administrator must manually decide to approve the new user to be added to the relevant campaigns. The approval of Recipients/Users is collected on the Recipient/User control list - see the below table "**LDAP Preferences Continued**" as a reference.
* **Automatically add to bounded campaigns and schedule plan:** When new users are detected in the LDAP server,  Lucy may be configured to automatically update the campaigns and schedule plans associated with that user group.
{% endtab %}

{% tab title="Action for Deleted Users" %}
1. **Automatically Delete Inactive:** If this option is selected, Lucy will automatically remove user accounts that are no longer active in the LDAP directory. This ensures that Lucy's user database is current and that inactive users do not remain part of ongoing campaigns or receive notifications.
2. **Waiting for Administrator's decision:**  If this option is selected when a user is deleted from the LDAP directory, Lucy will not immediately take any action. Instead, the system will flag the user for review, and an administrator will need to decide on the appropriate action, such as whether to delete the user from Lucy or perhaps keep them in the database for reporting or historical purposes. The approval of Recipients/Users is collected on the Recipient/User control list - see the below table "**LDAP Preferences Continued**" as a reference.
{% endtab %}

{% tab title="Importing" %}
Lucy permits administrators to configure LDAP preferences for individual or multiple user groups by activating the required "roles" selection option.\
\
For instance, to configure the preference for automatically importing users with the Enduser role, you would select the "Import Enduser role" option and specify the necessary parameters for the LDAP filter parameters:

<figure><img src="../../../.gitbook/assets/image (181).png" alt=""><figcaption></figcaption></figure>

This process can be repeated for all other "Role" importation options.
{% endtab %}
{% endtabs %}

### LDAP Preferences Continued

After defining your LDAP preferences, if you return to the settings by navigating to Settings -> Common System Settings -> LDAP Preferences, you will find four selectable actions available to you:

<figure><img src="../../../.gitbook/assets/image (182).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Import Users From LDAP" %}
This tab enables you to manually filter and import your chosen users from LDAP, effectively overriding the pre-set LDAP preferences.

Simply select your LDAP server (based on IP) and perform the necessary importing.\
\


<figure><img src="../../../.gitbook/assets/image (187).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
You can also filter by group or username.
{% endhint %}
{% endtab %}

{% tab title="Recipient Control List" %}

{% endtab %}

{% tab title="Users Control List" %}
If you have enabled the option for "Action for new users" and selected "Waiting for administrator's decision" then all pending users will be listed here.

<figure><img src="../../../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

The "Event" column indicates the status of each user, categorizing them as either a "New User" or a "Deleted User." You have the option to apply the event to users on an individual basis or select all users at once to apply the event in bulk.

<figure><img src="../../../.gitbook/assets/image (185).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Technically, an End-User and a Recipient refer to the same identity in Lucy, though they are distinguished based on the required function for the identity. If the user needs access to the End-user portal, these identities are referred to as "End-users." Conversely, if the user will not have access to a dedicated End-user portal, then these identities are considered as recipients.
{% endhint %}
{% endtab %}

{% tab title="LDAP Field Associations" %}
The LDAP Fields Associations screen allows administrators to map LDAP directory attributes to corresponding fields within Lucy for user profiles. Here's an explanation for each text box:

**Common Fields:**

1. **Full Name:** Maps to the `cn` (Common Name) LDAP attribute. Typically used to store the full name of a user.
2. **First Name:** Corresponds to the `givenName` LDAP attribute, which holds a user's given (or first) name.
3. **Last Name:** Linked to the `sn` (Surname) LDAP attribute, representing a user's family name or last name.
4. **Email Address:** Matches the `mail` LDAP attribute, containing the user's email address.
5. **Phone Number:** Connects to the `telephoneNumber` LDAP attribute for storing the user's telephone number.
6. **Location:** Associates with the `l` (localityName) LDAP attribute, indicating the user's location.
7. **Staff Type:** This is not matched with a default LDAP attribute in the screenshot and can be used for specifying the type of staff, such as permanent, contractor, etc., if a relevant attribute is available in LDAP.
8. **Comment:** An optional field for additional comments, not mapped in the screenshot.
9. **Link:** This could be used to associate a URL or a link relevant to the user profile, not mapped in the screenshot.
10. **Language:** Tied to the `preferredLanguage` LDAP attribute, specifying the user's preferred language.

**Custom Fields:**

11. **Division:** Linked to the `ou` (Organizational Unit) LDAP attribute, which can be used to define the division or department a user belongs to.
12. **Division Object Class:** This could be an advanced field to further specify the LDAP object class of the division attribute if needed.

Fields marked with an asterisk (\*) are required, meaning Lucy expects these LDAP attributes to be present and populated in the LDAP directory for successful user import.

**LDAP fields that can be used:**

Lucy automatically matches certain LDAP attributes to Lucy recipient attributes during import. The default mappings are:

1. **Email** corresponds to the recipient's email address.
2. **Name** matches the recipient's full name.
3. **Location** is used for the recipient's location.
4. **Phone** ties to the recipient's phone number.
{% endtab %}
{% endtabs %}







