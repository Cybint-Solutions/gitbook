# Administrative Users

## Introduction

LUCY offers role-based access control (RBAC), which restricts system access to authorized users. Permissions to perform certain operations are assigned to specific roles within the user settings. Members or staff are assigned particular roles, which grant them the necessary permissions to perform specific LUCY functions.

{% hint style="info" %}
Navigate to **Users > Administrative Users**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>

***



## Add New User

Select "**New User**"

<figure><img src="../../.gitbook/assets/image (984).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (994).png" alt=""><figcaption></figcaption></figure>

### Roles

There are four types of admin accounts in LUCY:

{% tabs %}
{% tab title="Administrator" %}
**Permissions**: Full access and highest privileges.

**Capabilities**: Can create and delete campaigns, manage all custom data (recipients, clients, templates, etc.), and manage other administrative users' account data.

{% hint style="warning" %}
Administrators have access to all clients. If you want an admin-level user that is restricted to one client only, create a **User** instead.
{% endhint %}
{% endtab %}

{% tab title="View" %}
**Permissions**: Can only view campaign statistics without the ability to start/stop campaigns or change settings.
{% endtab %}

{% tab title="User" %}
**Permissions**: Limited to content related to specific clients and branches.

**Capabilities**: Can access content (campaigns, custom templates, recipient groups) attributed to their assigned clients and branches.
{% endtab %}

{% tab title="Supervisor" %}
**Supervisors** maintain oversight with access to campaign specifications, communicate directly with campaign creators, suggest changes, and approve/reject campaigns.

{% hint style="warning" %}
Supervisors cannot supervise Administrators.
{% endhint %}
{% endtab %}
{% endtabs %}

### Password

{% hint style="success" %}
You can set password policies in the [advanced system settings](../settings/advanced-system-settings/advanced-settings.md).
{% endhint %}

***

## Import Users

You can import users via [LDAP ](../settings/common-system-settings/ldap-servers.md)or [Azure (Entra ID)](../settings/common-system-settings/azure-applications.md).

<figure><img src="../../.gitbook/assets/image (985).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="LDAP" %}
Select your [pre-defined server](../settings/common-system-settings/ldap-servers.md) from the server list:

<figure><img src="../../.gitbook/assets/image (598).png" alt=""><figcaption></figcaption></figure>

Add the relevant LDAP search syntax to query your Administrative Users.

<figure><img src="../../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

Here is an example for locating an Administrative User in the following directory structure:

**Base DN** **->** Beck.ai\
**OU ->** Admin Users\
**OU ->** Distribution Groups\
**Group ->** IntuneLucy-DevOps

```
(&(objectClass=user)(memberOf=cn=IntuneLucy-DevOps,ou=Distrubution Groups,ou=Admin Users,dc=beck,dc=ai))
```

For more information on search syntax consult [Microsoft's documentation](https://learn.microsoft.com/en-us/windows/win32/ad/creating-a-query-filter).

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

## SAML Users

If you use [SAML-based SSO](../settings/common-system-settings/sso-configuration.md) you can create and manage your login links under the SAML tab.

{% hint style="info" %}
This tab also serves as an access log for SAML-based users.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (992).png" alt=""><figcaption></figcaption></figure>

Links can be exported, generated, or deleted by user type.

<figure><img src="../../.gitbook/assets/image (993).png" alt=""><figcaption></figcaption></figure>

***

## Administrative Permission List

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
