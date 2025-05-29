# LDAP Servers

### Introduction

LUCY's LDAP integration enables administrators to:

1. **Import Users and Recipients:** Directly from the organization's directory service, simplifying user management.
2. **Authorize Access:** Across the Admin Console, End-user Portal, and Awareness Website, ensuring secure and appropriate user access.

{% hint style="info" %}
**Active Directory Sync Tool for Windows**

In addition to the direct LDAP integration, LUCY offers a synchronization tool for Windows. This tool enables the synchronization of your Active Directory groups with LUCY, all communication is done over API. For detailed information and setup instructions, refer to the [LDAP Sync Tool instructions](ldap-sync-tool.md).
{% endhint %}

### LDAP Connection Setup in LUCY

To configure the LDAP connection in LUCY, follow these steps:

Navigate to Settings → Common System Settings -> LDAP Servers.

<figure><img src="../../../../.gitbook/assets/image (282).png" alt=""><figcaption></figcaption></figure>

Select "Add Server"

{% tabs %}
{% tab title="Name" %}
Provide a Suitable Name for this LDAP server
{% endtab %}

{% tab title="Client" %}
For data segregation purposes, you have the flexibility to associate the configured LDAP server with a specific client. This ensures that user and group information from the LDAP server is exclusively available to the designated client.\
\
Alternatively, you can choose to make the LDAP server accessible to **all** clients, providing a centralized authentication and user management system across your organization. This option is particularly useful for organizations seeking to streamline operations and maintain a unified user database across multiple clients or departments.
{% endtab %}

{% tab title="Address" %}
Enter the IP address of your LDAP server.
{% endtab %}

{% tab title="Port" %}
1. **Port 389:** This is the default port for LDAP (Lightweight Directory Access Protocol) connections. LDAP is an open, vendor-neutral protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP) network. Port 389 is used for LDAP connections that are not secured by default. It is suitable for scenarios where LDAP traffic is contained within a secure internal network.
2. **Port 636:** This port is designated for LDAP over SSL (Secure Sockets Layer), commonly referred to as LDAPS. When connecting to an LDAP server over port 636, the communication is encrypted, providing confidentiality and protecting the information as it travels across the network. This port is recommended when LDAP queries are conducted over public networks or when enhanced security is required.
3. **Port 3268:** This is the default port for LDAP connections to the Global Catalog service in Microsoft Active Directory. The Global Catalog is a distributed data repository that contains a searchable, partial representation of every object in every domain in a multi-domain Active Directory Domain Services (AD DS) forest. It allows users to search the directory for objects, like user accounts and groups, across all domains without needing to know the domain name.
4. **Port 3269:** This port is used for LDAP over SSL connections to the Global Catalog. It is similar to port 3268 but provides the additional security benefits of SSL encryption. This is important for Global Catalog queries that need to be secure and is especially critical if the LDAP server is accessed over an insecure network or the internet.
{% endtab %}

{% tab title="Base DN" %}
Enter your LDAP Server Root RDN (e.g., "dc=domain,dc=com").
{% endtab %}

{% tab title="Auth Method" %}
1. **Simple Authentication:**
   * This method involves sending the user's credentials (usually a distinguished name (DN) along with a password) to the LDAP server in plain text. It's the most common authentication method used for LDAP bind operations, where "binding" refers to the process of authenticating a client to the LDAP server.
   * Simple authentication is straightforward but has security implications because credentials are not encrypted unless the connection itself is secured, for example, through SSL/TLS (LDAP over SSL or LDAPS). It's suitable for environments where security can be ensured by other means, like encrypted channels.
2. **Anonymous Authentication:**
   * Anonymous authentication allows a client to bind to an LDAP server without providing any credentials. This method is used mainly for public information retrieval where individual user authentication is not required.
   * It provides limited access rights, usually only allowing the client to query or view public entries within the LDAP directory. Anonymous authentication is not recommended for environments where sensitive data access needs to be controlled or logged since it does not uniquely identify the user.
{% endtab %}

{% tab title="User DN" %}
Provide the distinguished name of the user who has permission to perform LDAP queries. In this example, it's "cn=Administrator,cn=Users."
{% endtab %}

{% tab title="Password" %}
Input the password associated with the User DN for authentication.
{% endtab %}

{% tab title="Object Class" %}
The `objectClass` in LDAP is a crucial attribute that defines the kind of data an entry in the LDAP directory represents. It's like a blueprint that dictates which attributes (such as a user's name, email, or phone number) are required and which are optional for that entry.&#x20;

When you bind Lucy to an LDAP server, the `objectClass` helps you specify and identify the types of entries you want to interact with.\
\
For example, if your application needs to authenticate users, you'll likely query entries with an `objectClass` of `user` or `inetOrgPerson`, as these classes are designed to represent user accounts in an LDAP directory. \
\
If you leave the `objectClass` attribute blank when binding Lucy to an LDAP server, the search will not be constrained by object type. This means the LDAP query could potentially return all objects within the scope of the search base, regardless of their class.
{% endtab %}

{% tab title="Filter" %}
When binding Lucy to an LDAP server, the filter is used to specify which entries in the LDAP directory you want to retrieve and work with. A well-defined filter is crucial for efficient data retrieval and system performance, ensuring that Lucy interacts only with the relevant entries.

1. **Defining Scope:** The filter helps to narrow down the search to specific LDAP objects that are important for Lucy's operations. For instance, if Lucy needs to sync user accounts, a filter like `(objectClass=user)` will target only user objects.
2. **Enhancing Performance:** By using filters, Lucy queries the LDAP server for only the required data. Without a proper filter, the server might return a large amount of data, which could slow down both the LDAP server and Lucy, leading to increased load times and possible timeouts.
3. **Improving Security:** Filters prevent unnecessary exposure of directory information. For example, by using a filter, Lucy would not retrieve or have access to privileged accounts if it only needs regular user accounts.
4. **Operational Specificity:** Filters can also include criteria based on operational needs. For instance, if Lucy is used for a specific department, a filter like `(&(objectClass=user)(department=Marketing))` could be used to fetch only users from the Marketing department.
5. **Attribute Selection:** Filters can be designed to include entries with specific attributes, such as email addresses or job titles, which might be necessary for Lucy’s features like phishing simulations or training modules.
6. **Avoiding Data Overload:** By excluding unnecessary object classes or attributes, filters help Lucy to avoid data overload and improve the application’s response time.
{% endtab %}

{% tab title="Max Page Size" %}
A field to limit the number of entries returned in a single search query. \
\
The amount of users fetched in each request to the LDAP server. This should be based on what is configured in the LDAP server. The default fetch amount is 1000.
{% endtab %}
{% endtabs %}

<figure><img src="../../../../.gitbook/assets/image (190).png" alt=""><figcaption></figcaption></figure>

