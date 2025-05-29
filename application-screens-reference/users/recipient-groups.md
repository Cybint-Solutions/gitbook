# Recipient Groups

### Introduction

Every LUCY campaign requires a recipient group, which consists of users who will receive the attack simulation or awareness content. Multiple groups can be created for a single campaign, allowing for targeted phishing or training campaigns. Organizations often group users by department, location, or domain. Recipients can belong to any number of groups, and there is no limit on the number of groups you can set up.

### Creating a New Group

{% hint style="info" %}
Navigate to **Users -> Recipient Groups**
{% endhint %}

You can add recipients manually or import them via CSV, LDAP, or Azure (Entra ID). Groups are defined globally and can be reused across different campaigns.&#x20;

{% hint style="success" %}
Importing recipients from company directories is recommended as it allows you to include additional information about each user, which enhances automatic analysis and statistics.
{% endhint %}

Select "**New Group**"

<figure><img src="../../.gitbook/assets/image (579).png" alt="" width="563"><figcaption></figcaption></figure>

The Group base settings are defined in the form:

<figure><img src="../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Name" %}
This is a required field where you'll enter the name of the new group you are creating. It's important to emphasize clear identification for efficient management within the system.
{% endtab %}

{% tab title="Client" %}
This dropdown menu allows you to select which [client](../settings/clients/) the group is associated with. This helps in organizing and managing groups under different clients while ensuring recipient data remains segregated.
{% endtab %}

{% tab title="Default Language" %}
This dropdown menu allows you to set a default language for the group. This setting determines the language used for group content delivery when the recipient records do not specify a language.
{% endtab %}

{% tab title="Portable Media Attack" %}
Enable this checkbox if this group is intended to execute a [Portable Media Attack](recipient-groups.md#portable-media-attack).
{% endtab %}
{% endtabs %}

***

### Adding Recipients to Lucy

There are four methods to import recipients into Lucy.

{% tabs %}
{% tab title="Manual" %}
Directly input recipient details one by one. This method is feasible for small numbers of recipients but becomes time-consuming for larger sets.

<figure><img src="../../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

Select "**New Recipient**"

{% hint style="info" %}
First name and Email are the only two mandatory fields.
{% endhint %}

Provide all necessary details of the recipient. The more fields that are filled, the more granular the statistics can be.

<figure><img src="../../.gitbook/assets/image (582).png" alt=""><figcaption></figcaption></figure>

Once completed, click "**Save**" to commit your recipient to the group.
{% endtab %}

{% tab title="CSV" %}
{% hint style="info" %}
Select "**Import from File**"
{% endhint %}

<figure><img src="../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

#### Ensure the CSV is correctly formatted

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
11. First Name - recipient's first name
12. Last Name - recipient's last name

{% hint style="info" %}
To skip a column value, leave it empty between the separators. Columns at the end of the record can be omitted if not needed. For example, if you have only Email and Full Name, you can specify just these two columns.
{% endhint %}

#### Import CSV

Select "**Choose File**" to import your recipients.

<figure><img src="../../.gitbook/assets/image (488).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="LDAP Server" %}
You can add your recipients by using an LDAP server. For setup instructions, refer to the [LDAP Integration article](../settings/common-system-settings/ldap-servers/).

{% hint style="info" %}
Select "**LDAP Server**" to Import from.
{% endhint %}

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

Select the [LDAP Server](../settings/common-system-settings/ldap-servers/) which needs to be associated with this group.

***

### LDAP Search

You can use standard Active Directory search filters, such as:

```
(|(objectClass=inetOrgPerson)(objectClass=user))
```

For more information, refer to the [Microsoft Documentation](https://docs.microsoft.com/en-us/windows/win32/adsi/search-filter-syntax).

***

### LDAP Search Examples

**Goal:** Import all users in the distribution group name "IntuneLucy-DevOps"

**Directory Structure:**

**Base DN** **->** Beck.ai\
**OU ->** Admin Users\
**OU ->** Distribution Groups\
**Group ->** IntuneLucy-DevOps

<figure><img src="../../.gitbook/assets/image (491).png" alt=""><figcaption></figcaption></figure>

A well-formulated Active Directory search filter to obtain all users in the Group = IntuneLucy-DevOps:

```
(&(objectClass=user)(memberOf=cn=IntuneLucy-DevOps,ou=Distrubution Groups,ou=Admin Users,dc=beck,dc=ai))
```

**`&`**: This is the logical operator "AND". It indicates that all the conditions enclosed within the parentheses must be true for the query to return a result. This operator combines multiple search filters.

**`(objectClass=user)`**: This filter specifies that the object being searched should be of the type "user". The `objectClass` attribute in LDAP is used to define the schema or type of an object in the directory.

**`(memberOf=cn=IntuneLucy-DevOps,ou=Distrubution Groups,ou=Admin Users,dc=beck,dc=ai)`**: This filter is used to find users who are members of a specific group. Here's a breakdown of the group's distinguished name (DN):

* **`cn=IntuneLucy-DevOps`**: "cn" stands for Common Name. In this case, it refers to the name of the group.
* **`ou=Distrubution Groups`**: "ou" stands for Organizational Unit.
* **`ou=Admin Users`**: Another Organizational Unit, indicating a higher-level grouping within the directory.
* **`dc=beck,dc=ai`**: "dc" stands for Domain Component. These components are part of the LDAP naming context and represent different levels of the domain.

This query is structured to ensure that only objects that are users (`objectClass=user`) and are members of the specified group (`memberOf=...`) are returned.

***

### Import

After successfully retrieving the desired recipients from your company directory, select the checkbox to include All, and click "Import" to begin the import process.

<figure><img src="../../.gitbook/assets/image (486).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Azure (Entra ID)" %}
You can add your recipients by using Azure Entra ID. For setup instructions, refer to the [Azure Applications](../settings/common-system-settings/azure-applications.md).

{% hint style="info" %}
Select "**Azure AD**" to Import from.
{% endhint %}

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

**Filter by Groups ->** Select the Group dropdown menu:

<figure><img src="../../.gitbook/assets/image (584).png" alt=""><figcaption></figcaption></figure>

**Filter by Search Parameters ->** Enter [Microsoft search filters](https://learn.microsoft.com/en-us/graph/query-parameters?tabs=http#filter-parameter)

#### Scenario 1: Filter by Email Domain

To import only recipients whose email domain ends with "@lucysecurity.company", use the `endswith` function:

```plaintext
(mail, '@lucysecurity.com')
```

This filter ensures that only users with emails ending in "@lucysecurity.company" are included in the import.

#### Scenario 2: Filter by Name Prefix

To import recipients whose names begin with "User", utilize the `startswith` function:

```plaintext
startswith(displayName, 'User')
```

This filter will match and import users whose display names start with "User".

#### Scenario 3: Filter by Location

To find all users located in 'Ext1', you can directly match the `officeLocation` attribute:

```plaintext
officeLocation eq 'Ext1'
```

This query ensures that only users with 'Ext1' listed as their office location are selected.

#### Scenario 4: Filter by Phone Number Exclusion

To exclude recipients whose phone number is '911', apply the `ne` (not equal) operator:

```plaintext
mobilePhone ne '911'
```

This filter imports users whose mobile phone number is not '911'.

***

### Import

After successfully retrieving the desired recipients from your company directory, select the checkbox to include All, and click "Import" to begin the import process.

<figure><img src="../../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

***

### Import Settings

The "Import Settings" tab enables you to configure automated import processes for recipients from your organization's directory.

{% hint style="info" %}
Select -> **Import Settings**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>

***

### Import Type:

Select the Type of Import:

<figure><img src="../../.gitbook/assets/image (586).png" alt="" width="563"><figcaption></figcaption></figure>

***

### Action for New Recipients:

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

### Action for Deleted Campaigns

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

***

### Import Filters

Both Azure Entra ID and LDAP use standard Microsoft syntax filters.

{% tabs %}
{% tab title="LDAP" %}
You can employ standard Active Directory search filters, such as:

```
(|(objectClass=inetOrgPerson)(objectClass=user))
```

This filter retrieves objects that are either of type `inetOrgPerson` or `user`. For further details and guidance, refer to the [Microsoft Documentation](https://learn.microsoft.com/en-us/archive/technet-wiki/5392.active-directory-ldap-syntax-filters).

### LDAP Search Example:

in the "Import Settings", you will need to define both the Base DN and Search Filter separately.

&#x20;**Goal:** Import all users in the distribution group name "IntuneLucy-DevOps"

**Directory Structure:**

**Base DN** **->** Beck.ai\
**OU ->** Admin Users\
**OU ->** Distribution Groups\
**Group ->** IntuneLucy-DevOps

<figure><img src="../../.gitbook/assets/image (491).png" alt=""><figcaption></figcaption></figure>

A well-formulated Active Directory search filter to obtain all users in the Group = IntuneLucy-DevOps:

#### Base DN:

```
dc=beck,dc=ai
```

#### Filter:

```
(&(objectClass=user)(memberOf=cn=IntuneLucy-DevOps,ou=Distrubution Groups,ou=Admin Users,dc=beck,dc=ai))
```

<figure><img src="../../.gitbook/assets/image (484).png" alt=""><figcaption></figcaption></figure>

**`&`**: This is the logical operator "AND". It indicates that all the conditions enclosed within the parentheses must be true for the query to return a result. This operator combines multiple search filters.

**`(objectClass=user)`**: This filter specifies that the object being searched should be of the type "user". The `objectClass` attribute in LDAP is used to define the schema or type of an object in the directory.

**`(memberOf=cn=IntuneLucy-DevOps,ou=Distrubution Groups,ou=Admin Users,dc=beck,dc=ai)`**: This filter is used to find users who are members of a specific group. Here's a breakdown of the group's distinguished name (DN):

* **`cn=IntuneLucy-DevOps`**: "cn" stands for Common Name. In this case, it refers to the name of the group.
* **`ou=Distrubution Groups`**: "ou" stands for Organizational Unit.
* **`ou=Admin Users`**: Another Organizational Unit, indicating a higher-level grouping within the directory.
* **`dc=beck,dc=ai`**: "dc" stands for Domain Component. These components are part of the LDAP naming context and represent different levels of the domain.

This query is structured to ensure that only objects that are users (`objectClass=user`) and are members of the specified group (`memberOf=...`) are returned.
{% endtab %}

{% tab title="Azure Entra ID" %}
**Filter by Groups ->** Select the Group dropdown menu:

<figure><img src="../../.gitbook/assets/image (485).png" alt=""><figcaption></figcaption></figure>

**Filter by Search Parameters ->** Enter [Microsoft search filters](https://learn.microsoft.com/en-us/graph/query-parameters?tabs=http#filter-parameter)

#### Scenario 1: Filter by Email Domain

To import only recipients whose email domain ends with "@lucysecurity.company", use the `endswith` function:

```plaintext
(mail, '@lucysecurity.com')
```

This filter ensures that only users with emails ending in "@lucysecurity.company" are included in the import.

#### Scenario 2: Filter by Name Prefix

To import recipients whose names begin with "User", utilize the `startswith` function:

```plaintext
startswith(displayName, 'User')
```

This filter will match and import users whose display names start with "User".

#### Scenario 3: Filter by Location

To find all users located in 'Ext1', you can directly match the `officeLocation` attribute:

```plaintext
officeLocation eq 'Ext1'
```

This query ensures that only users with 'Ext1' listed as their office location are selected.

#### Scenario 4: Filter by Phone Number Exclusion

To exclude recipients whose phone number is '911', apply the `ne` (not equal) operator:

```plaintext
mobilePhone ne '911'
```

This filter imports users whose mobile phone number is not '911'.
{% endtab %}
{% endtabs %}
