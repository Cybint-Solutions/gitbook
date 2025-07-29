# Recipient Groups

Every LUCY campaign needs at least one recipient group—users who will receive the simulation or training content. You can create multiple groups per campaign to target users by department, location, domain, or other criteria. Users can belong to multiple groups, and there’s no limit to how many you can create.

## Creating a New Group

{% hint style="info" %}
Navigate to **Users > Recipient Groups**
{% endhint %}

You can add recipients manually or import them via CSV, LDAP, or Azure (Entra ID).

{% hint style="success" %}
Importing recipients from company directories is recommended as it allows you to include additional information about each user, which enhances automatic analysis and statistics.
{% endhint %}

1. Select "**New Group**" and fill out the group information.

<figure><img src="../../.gitbook/assets/image (579).png" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Name" %}
This is a required field where you'll enter the name of the new group you are creating. It's important to emphasize clear identification for efficient management within the system.
{% endtab %}

{% tab title="Client" %}
This dropdown menu allows you to select which [client](../settings/clients/) the group is associated with.
{% endtab %}

{% tab title="Default Language" %}
This setting determines the language used for group content delivery when the recipient records do not specify a language.
{% endtab %}

{% tab title="Portable Media Attack" %}
{% hint style="danger" %}
This feature is deprecated, do not enable it.
{% endhint %}
{% endtab %}
{% endtabs %}

***

## Adding Recipients

There are four methods to import recipients into Lucy.

{% tabs %}
{% tab title="Manual" %}
Directly input recipient details one by one. This method is feasible for small numbers of recipients but becomes time-consuming for larger sets.

<figure><img src="../../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

Select "**New Recipient**"

Provide all necessary details of the recipient. The more fields that are filled, the more granular the statistics can be.

{% hint style="success" %}
Each recipient must have a first name and at least one contact method—either an email address, a phone number, or both.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (582).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="CSV" %}
<figure><img src="../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

Here is an example CSV for reference:

{% file src="../../.gitbook/assets/lucy_example_csv.csv" %}

The import file should contain text in UTF-8 encoding. Each line should represent one recipient. Each record can have 1 to 12 columns, separated by a comma, colon, or semicolon (, : or ;). The possible columns are:

1. Email - recipient's email address (**mandatory**)
2. Full Name - recipient's full name
3. Staff - job position or related information
4. Location - recipient's location
5. Division - company division
6. Comment - any custom comment
7. Link - unique link part for the landing page (ensure uniqueness if specified; otherwise, it will be generated automatically)
8. Phone - recipient's phone number
9. Language - recipient's language
10. Gender - recipient's gender ("m" for Male; "f" for Female)
11. First Name - recipient's first name (**mandatory**)
12. Last Name - recipient's last name

{% hint style="success" %}
To leave a column blank, leave it empty between the separators like so:

user@example.com;Jane Doe;;USA;HR;;;;English;F;Jane;Doe;

This recipient does not have values for Staff, Comment, Link, or Phone.
{% endhint %}

#### Import CSV

Select "**Choose File**" to import your recipients, then select **"Import"**.

<figure><img src="../../.gitbook/assets/image (488).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="LDAP Server" %}
For instructions on connecting an LDAP server refer to the [LDAP Integration article](../settings/common-system-settings/ldap-servers.md).

***

### Import Options

<figure><img src="../../.gitbook/assets/image (490).png" alt=""><figcaption></figcaption></figure>

**Update existing recipients**

* If this option is enabled, any existing recipients in this group will have their attributes updated during the LDAP import. This ensures that the latest information from the LDAP server is reflected in the recipient list.

**Add recipients to bound campaigns**

* Enabling this option will add the imported recipients to any campaigns that are already bound to the group. This is useful if you want to expand the reach of your current campaigns to include new or updated recipients.

**Send emails if bound campaigns are running**

* If this option is selected, emails will be sent to the newly imported recipients if they are part of running campaigns. This ensures that any active campaigns will immediately include the new recipients in their email distribution.

**Add more groups**

* This option allows you to import additional groups already present in Lucy. This can be helpful if you want to organize recipients into specific categories or segment groups for targeted campaigns.

***

### LDAP Server

Select the [LDAP Server](../settings/common-system-settings/ldap-servers.md) which needs to be associated with this group.

***

### LDAP Search

You can use standard Active Directory search filters, such as:

```
(|(objectClass=inetOrgPerson)(objectClass=user))
```

For more information, refer to the [Microsoft Documentation](https://docs.microsoft.com/en-us/windows/win32/adsi/search-filter-syntax).

***

### Import

After successfully retrieving the desired recipients from your company directory, select the checkbox to include All, and click "Import" to begin the import process.

<figure><img src="../../.gitbook/assets/image (486).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Azure (Entra ID)" %}
For instructions on connecting an Azure application refer to the [Azure Applications](../settings/common-system-settings/azure-applications.md) article.

***

### Import Options

<figure><img src="../../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

**Update existing recipients**

* If this option is enabled, any existing recipients in this group will have their attributes updated during the Entra ID import. This ensures that the latest information from the Entra ID server is reflected in the recipient list.

**Add recipients to bound campaigns**

* Enabling this option will add the imported recipients to any campaigns that are already bound to the group. This is useful if you want to expand the reach of your current campaigns to include new or updated recipients.

**Send emails if bound campaigns are running**

* If this option is selected, emails will be sent to the newly imported recipients if they are part of running campaigns. This ensures that any active campaigns will immediately include the new recipients in their email distribution.

**Add more groups**

* This option allows you to import additional groups already present in Lucy. This can be helpful if you want to organize recipients into specific categories or segment groups for targeted campaigns.

***

### Azure Application

Select the [Azure Application](../settings/common-system-settings/azure-applications.md) which needs to be associated with this group.

***

### Azure Search

**Filter by Groups**

Select a group from the dropdown list:

<figure><img src="../../.gitbook/assets/image (584).png" alt=""><figcaption></figcaption></figure>

**Filter by Search Parameters**

Use [Microsoft search filters](https://learn.microsoft.com/en-us/graph/query-parameters?tabs=http#filter-parameter).

Here are some common examples:

1. All users with a certain email domain

```
endsWith(mail, '@example.com')
```

2. All users with a certain username

```
startsWith(mail, 'username')
```

3. All users in the same location

```
officeLocation eq 'Regional Headquarters'
```

### Import

After successfully retrieving the desired recipients from your company directory, select the checkbox to include All, and click "Import" to begin the import process.

<figure><img src="../../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

***

## Autoupdate Recipients

You can automatically sync your recipients from LDAP or Azure AD by defining the import parameters on the **Import Settings** tab. This sync runs in the background every 10 minutes.

<figure><img src="../../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>

***

### Import Type

Automatically sync from your LDAP or Azure AD application.

<figure><img src="../../.gitbook/assets/image (586).png" alt="" width="563"><figcaption></figcaption></figure>

{% tabs %}
{% tab title="LDAP" %}
You can employ standard Active Directory search filters, such as:

```
(|(objectClass=inetOrgPerson)(objectClass=user))
```

This filter retrieves objects that are either of type `inetOrgPerson` or `user`.

For further details and guidance, refer to the [Microsoft Documentation](https://learn.microsoft.com/en-us/archive/technet-wiki/5392.active-directory-ldap-syntax-filters).
{% endtab %}

{% tab title="Azure Entra ID" %}
**Filter by Groups**

Select a group from the dropdown list:

<figure><img src="../../.gitbook/assets/image (485).png" alt=""><figcaption></figcaption></figure>

**Filter by Search Parameters**

Use [Microsoft search filters](https://learn.microsoft.com/en-us/graph/query-parameters?tabs=http#filter-parameter).

Here are some common examples:

1. All users with a certain email domain

```
endsWith(mail, '@example.com')
```

2. All users with a certain username

```
startsWith(mail, 'username')
```

3. All users in the same location

```
officeLocation eq 'Regional Headquarters'
```
{% endtab %}
{% endtabs %}

***

### Action for New Recipients

{% tabs %}
{% tab title="Waiting for Administrator" %}
If this option is selected, the automatic import will list all recipients in the Control List for both LDAP and Azure Entra ID integrations.

<figure><img src="../../.gitbook/assets/image (588).png" alt=""><figcaption></figcaption></figure>

Your Lucy server will make a query every 10 minutes to your company directory to obtain the most updated list of your recipient directory.

You can manually **add** each recipient:

<figure><img src="../../.gitbook/assets/image (591).png" alt=""><figcaption></figcaption></figure>

Or you can select All recipients and **Apply** them to your Group:

<figure><img src="../../.gitbook/assets/image (592).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Automatically Add" %}
#### Automatically Add to Bounded Campaigns

When this option is selected, the recipients will be imported automatically and added to all campaigns the recipient group is bound to.

***

#### Automatically Add to Bounded Campaigns and Schedule Plans

When this option is selected, the recipients will be imported automatically and added to all campaigns the recipient group is bound to, in addition any Schedule Plans with this recipient group will also be updated to reflect the new recipients.
{% endtab %}
{% endtabs %}

***

### Action for Deleted Recipients

{% tabs %}
{% tab title="Waiting for Administrator" %}
If this option is selected, the automatic deletion will list all recipients in the Control List for both LDAP and Azure Entra ID integrations.

<figure><img src="../../.gitbook/assets/image (590).png" alt=""><figcaption></figcaption></figure>

Your Lucy server will make a query every 10 minutes to your company directory to obtain the most updated list of your recipient directory.

You can manually **Discard** each recipient:

<figure><img src="../../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

Or you can select All recipients and **Discard** them to your Group:

<figure><img src="../../.gitbook/assets/image (593).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Automatically Delete Inactive" %}
When this option is selected, the recipients not "Active" or deleted in the company directory will be automatically removed from the group and all subsequent campaigns.&#x20;
{% endtab %}

{% tab title="Never Delete" %}
When this option is selected, no recipients will be deleted even if Lucy has determined the recipient is not "Active" in your company directory.
{% endtab %}
{% endtabs %}
