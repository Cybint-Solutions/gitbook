# Administrative Users

### Introduction

LUCY offers role-based access control (RBAC), which restricts system access to authorized users. Permissions to perform certain operations are assigned to specific roles within the user settings. Members or staff are assigned particular roles, which grant them the necessary permissions to perform specific LUCY functions.

### Configuring User Settings

{% hint style="info" %}
Navigate to **Users -> Administrative Users**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (595).png" alt=""><figcaption></figcaption></figure>

***

### Add New User

Select "**New User**"

<figure><img src="../../.gitbook/assets/image (596).png" alt="" width="563"><figcaption></figcaption></figure>

#### Role:

There are four types of admin accounts in LUCY:

{% tabs %}
{% tab title="Administrator" %}
**Permissions**: Full access and highest privileges.

**Capabilities**: Can create and delete campaigns, manage all custom data (recipients, clients, templates, etc.), and manage other administrative users' account data.

**Notes**: Administrators cannot be segregated by client visibility.
{% endtab %}

{% tab title="Supervisor" %}
**Role**: Maintain oversight with access to campaign specifications, communicate directly with campaign creators, suggest changes, and approve/reject campaigns.

**Notes**: Supervisors cannot supervise system admins. They can start/stop campaigns created by users under their supervision.
{% endtab %}

{% tab title="User" %}
**Permissions**: Limited to content related to specific clients and branches.

**Capabilities**: Can access content (campaigns, custom templates, recipient groups) attributed to their assigned clients and branches.

**Notes**: Ensure to disable the "Access all Campaigns" permission to prevent users from different clients/branches from accessing each other's data.
{% endtab %}

{% tab title="View" %}
**Role**: Can only view campaign statistics without the ability to start/stop campaigns or change settings.

**Setup**: Associate the user with a specific client and branch to restrict view to campaigns belonging to that client.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Please note that there are also [**End User accounts**](end-users.md) in LUCY that come as part of the [**End User Portal**](end-user-portal-settings.md) functionality and have no admin rights. These accounts are automatically created for recipients assigned to awareness training.
{% endhint %}

#### Password:

**Password Policy ->** Adjustable in the [advanced settings](../settings/advanced-system-settings/advanced-settings.md#password-settings).

**SSO Authentication ->** Possible via [SAML 2.0](../settings/common-system-settings/sso-configuration.md#saml-2.0) or [OAuth 2.0 (Entra ID)](../settings/common-system-settings/sso-configuration.md#oauth-2.0-azure) for automatic user authentication.

***

### Import Administrative Users

Importing administrative users can be directly done from your company directory either via [LDAP ](../settings/common-system-settings/ldap-servers/)or [Azure (Entra ID)](../settings/common-system-settings/azure-applications.md).

{% hint style="info" %}
Navigate to **Users -> Administrative Users**
{% endhint %}

Select "**Import**"

<figure><img src="../../.gitbook/assets/image (597).png" alt="" width="563"><figcaption></figcaption></figure>

{% tabs %}
{% tab title="LDAP" %}
Select your [pre-defined server](../settings/common-system-settings/ldap-servers/) from the server list:

<figure><img src="../../.gitbook/assets/image (598).png" alt=""><figcaption></figcaption></figure>

Add the relevant LDAP search syntax to query your Administrative Users.

<figure><img src="../../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

For example, locating an Administrative User in the following directory structure:

**Base DN** **->** Beck.ai\
**OU ->** Admin Users\
**OU ->** Distribution Groups\
**Group ->** IntuneLucy-DevOps

<figure><img src="../../.gitbook/assets/image (491).png" alt=""><figcaption></figcaption></figure>

A well-formulated [Active Directory search filter](https://learn.microsoft.com/en-us/archive/technet-wiki/5392.active-directory-ldap-syntax-filters) to obtain an Administrative user in the Group = IntuneLucy-DevOps:

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

Select your user(s) and import:

<figure><img src="../../.gitbook/assets/image (601).png" alt=""><figcaption></figcaption></figure>

Once "**Import**" is selected, a pop-up will appear to define the **Role**.

<figure><img src="../../.gitbook/assets/image (483).png" alt="" width="422"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Azure" %}
### Import Role

Define the Role of the imported user group.

<figure><img src="../../.gitbook/assets/image (480).png" alt="" width="403"><figcaption></figcaption></figure>

***

### Azure Application

Select the specific Azure Entra ID tenant.

<figure><img src="../../.gitbook/assets/image (481).png" alt="" width="422"><figcaption></figcaption></figure>

***

### Filter Azure Groups

Select the desired group to import from the drop-down.

<figure><img src="../../.gitbook/assets/image (482).png" alt="" width="420"><figcaption></figcaption></figure>

***

### Filter

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
{% endtab %}
{% endtabs %}

***

### Multitenant Capable Administration

#### Use Case 1: Customer Access to Campaign Statistics

**Scenario:** You create a campaign for your customer and want to give them access to view the statistics without allowing them to change the campaign configuration.

**Create View-Only Account**

* Navigate to **Users -> Administrative Users**
* Create a new user account with "view-only" status. This account will only have permission to view campaign statistics.

<figure><img src="../../.gitbook/assets/image (602).png" alt=""><figcaption></figcaption></figure>

**Assign Campaign to Client**

* When creating a campaign, you will be prompted to enter the [**Client**](../settings/clients/) for the campaign. This client can be yourself, an organizational unit, or a third party.

<figure><img src="../../.gitbook/assets/image (603).png" alt=""><figcaption></figcaption></figure>

**Add User to Campaign**

* Add the view-only user account to the campaign by navigating to the created campaign, selecting **Advanced Settings -> User Settings**.

<figure><img src="../../.gitbook/assets/image (604).png" alt=""><figcaption></figcaption></figure>

**Assign Viewing Rights**

* Assign the necessary permissions to the view-only user to allow them to view the campaign statistics.

<figure><img src="../../.gitbook/assets/image (605).png" alt=""><figcaption></figcaption></figure>

***

#### Use Case 2: Customer Creates Their Own Campaigns

**Scenario:** A customer wants to create their own campaigns, but should only have access to their own campaign data and not see data from other customers.

**Create a Limited User Account**

* Navigate to **Users -> Administrative Users**
* Create a new user account with the role of "user".

<figure><img src="../../.gitbook/assets/image (606).png" alt=""><figcaption></figcaption></figure>

**Assign Create/Delete Campaign Rights**

* Give the user the "Create/delete campaign" permission. This allows the user to create and delete their own campaigns.

<figure><img src="../../.gitbook/assets/image (607).png" alt=""><figcaption></figcaption></figure>

**Customer Access**

* When the customer logs in, they can create their own campaigns and will only see data related to the campaigns they created.
* The user will not have access to other menu items or data from other customers.

***

### Administrative Permission List

| Permission                        | Description                                                            |
| --------------------------------- | ---------------------------------------------------------------------- |
| Access All Campaigns              | Right to access all campaigns, overriding Clients and Branches policy. |
| Create/Delete Campaigns           | Right to create and delete campaigns.                                  |
| Save Campaign As Template         | Right to save a campaign as a template.                                |
| Attack Templates                  | Access to predefined attack templates.                                 |
| Campaign Templates                | Access to campaign templates.                                          |
| Awareness Templates               | Access to awareness training templates.                                |
| File Templates                    | Access to file-based attack templates.                                 |
| Report Templates                  | Access to report templates.                                            |
| Download Templates                | Access to download templates.                                          |
| Clients                           | Access to clients menu.                                                |
| Recipients                        | Access to the list of recipients.                                      |
| End Users                         | Access to the list of end users.                                       |
| User Management                   | Access to user management.                                             |
| Reputation Levels                 | Access to reputation levels.                                           |
| SSH Access                        | Access to SSH menu.                                                    |
| SSH Password                      | Right to reset SSH password.                                           |
| Benchmark Sectors                 | Access to benchmark sectors.                                           |
| License                           | Access to license menu.                                                |
| Update                            | Right to update LUCY.                                                  |
| Reboot                            | Right to reboot LUCY.                                                  |
| Domains                           | Access to domains menu.                                                |
| Register Domains                  | Right to register a domain.                                            |
| Dynamic DNS                       | Access to dynamic DNS feature.                                         |
| Automated Response Detection      | Access to automated response detection menu.                           |
| Settings                          | Access to advanced settings, including customization of the 404 page.  |
| SMS Settings                      | Ability to set up SMS systems for text message delivery.               |
| Performance Test                  | Access to performance tests.                                           |
| Test Email                        | Right to send a test email.                                            |
| Spam Test                         | Access to spam test.                                                   |
| System Monitoring                 | Access to system monitoring.                                           |
| System Status Page                | Access to system status page.                                          |
| Incident Management               | Access to incident management.                                         |
| Plugin Configuration              | Right to configure the Outlook plugin.                                 |
| Incident Management Configuration | Right to configure incident management.                                |
| Manual                            | Access to the LUCY manual.                                             |
| Exports                           | Access to exports.                                                     |
| Invoices                          | Access to invoices.                                                    |
| Send Logs                         | Access to send logs menu.                                              |
| Service Logs                      | Access to service logs.                                                |
| Changelog                         | Access to changelog.                                                   |
| Mail Manager                      | Access to mail manager.                                                |
| Tickets                           | Access to the ticket system.                                           |
