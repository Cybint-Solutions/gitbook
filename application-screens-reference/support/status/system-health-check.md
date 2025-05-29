# System Health Check

### Introduction

A System Health Check is a crucial process in maintaining the optimal performance and security of your server. It involves running various tests and checks on essential system services, configurations, permissions, and files.

***

{% hint style="info" %}
Navigate to **Support -> Status -> System Health Check**&#x20;
{% endhint %}

### Overall Result

The overall result of the system health check indicates the health status of the server by summarizing the outcomes of individual checks.&#x20;

<figure><img src="../../../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure>

***

### Statuses

{% tabs %}
{% tab title="Passed" %}
* **Description**: The check was successful, and no issues were found.
* **Implication**: The component is functioning correctly and does not require any attention.
{% endtab %}

{% tab title="Low (Info)" %}
* **Description**: A minor issue or informational notice was found that does not immediately affect system performance or security.
* **Implication**: It is advisable to review and address this notice, but it is not urgent.
{% endtab %}

{% tab title="Medium (Warning)" %}
* **Description**: A warning indicates a potential issue that could affect system performance or security if not addressed.
* **Implication**: It is important to investigate and resolve this warning to prevent possible future problems.
{% endtab %}

{% tab title="Critical (Error)" %}
* **Description**: A critical error was found that significantly impacts system performance or security.
* **Implication**: Immediate action is required to resolve this issue to restore optimal system functionality and security.
{% endtab %}
{% endtabs %}

{% hint style="success" %}
Contact our [Technical Support department](../../../when-to-contact-us/contact-technical-support.md) for assistance with critical issues.
{% endhint %}

***

### Categories of System Health Checks

1. **Apache Server**
   * **Purpose**: Ensures that the Apache server is running correctly and configured properly.
   * **Importance**: Apache is a widely-used web server, and its proper functioning is crucial for hosting your Lucy server and campaign landing pages.
2. **Application**
   * **Purpose**: Checks the status and performance of installed applications.
   * **Importance**: Ensures applications are up-to-date and functioning correctly, preventing potential disruptions and vulnerabilities.
3. **Cache**
   * **Purpose**: Validate the status of system caches, ensuring they are configured and functioning correctly.
   * **Importance**: Efficient caching improves system performance by reducing data retrieval times for frequently accessed data.
4. **Database Configuration**
   * **Purpose**: Check that databases are correctly configured, including connection settings and performance tuning.
   * **Importance**: Proper database configuration is critical for data integrity, performance, and security of database-driven applications.
5. **Database Content**
   * **Purpose**: Verify the integrity and consistency of the data stored in the databases.
   * **Importance**: Ensures reliable data storage and retrieval, preventing data corruption and loss.
6. **Directories Structure**
   * **Purpose**: Ensure that directory structures are correctly set up and organized.
   * **Importance**: Proper directory structure ensures efficient file management and can prevent issues related to file access and permissions.
7. **Error Logs**
   * **Purpose**: Analyzes system and application error logs to identify potential issues.
   * **Importance**: Regularly monitoring error logs helps in early detection and resolution of problems, preventing system downtime.
8. **External Services**
   * **Purpose**: Checks the status and connectivity of external services that the system relies on.
   * **Importance**: Ensures that all external dependencies are functional, and critical for system operations that rely on these services.
9. **Files & Directories Access Permissions**
   * **Purpose**: Verifies that files and directories have appropriate access permissions.
   * **Importance**: Correct permissions are vital for system security, preventing unauthorized access and modifications.
10. **Files & Directories Owners**
    * **Purpose**: Ensures that files and directories have the correct ownership.
    * **Importance**: Proper ownership is necessary for maintaining security and accountability within the system.
11. **LUST Server**
    * **Purpose**: Checks the connection of your Lucy server with the LUST licensing server.
    * **Importance**: The LUST server is important for specific functions in Lucy; its proper functioning is critical to ensure your server receives a license and all license-related features remain active.
12. **Mail Server & Mailboxes**
    * **Purpose**: Verifies the status and configuration of the mail server and mailboxes.
    * **Importance**: Ensures reliable email communication, which is essential for simulated emails and awareness training.
13. **NodeJS & NPM**
    * **Purpose**: Checks the status of NodeJS and NPM installations.
    * **Importance**: NodeJS is a runtime environment, and NPM is a package manager for JavaScript applications.
14. **PHP**
    * **Purpose**: Verifies the status and configuration of PHP installations.
    * **Importance**: PHP is a widely-used scripting language for web development. Ensuring its proper configuration is critical for the performance and security of PHP-based applications.
15. **Plugins**
    * **Purpose**: Checks the status and compatibility of phishing reporting plugins.
    * **Importance**: Plugins extend the functionality of Lucy. Ensuring their compatibility and proper communication is essential for collecting reported emails to Lucy.
16. **Python**
    * **Purpose**: Verifies the status and configuration of Python installations.
    * **Importance**: Python is a versatile programming language. Its proper configuration is essential for applications and scripts that depend on it.
17. **SSL Certificates**
    * **Purpose**: Checks the status and validity of SSL certificates.
    * **Importance**: SSL certificates are crucial for securing communications over the internet. Ensuring their validity is essential for maintaining secure connections for both the Lucy administration panel and campaign landing pages.
18. **System Info & Configuration**
    * **Purpose**: Verifies the overall system information and configuration settings.
    * **Importance**: Ensuring correct system configuration is vital for the optimal performance and security of the server.
19. **System Services & Applications**
    * **Purpose**: Checks the status of system services and applications.
    * **Importance**: Ensures that all critical services and applications are running smoothly and are properly configured.
20. **Templates**
    * **Purpose**: Verifies the status and configuration of available, installed, and required templates.
    * **Importance**: Properly configured templates are important for consistent and efficient awareness programs.
21. **VueJS**
    * **Purpose**: Checks the status of VueJS installations.
    * **Importance**: VueJS is a popular JavaScript framework for building user interfaces.

#### Conclusion

Performing regular system health checks is essential for maintaining the stability, performance, and security of your server. By understanding the various components and their respective checks, you can ensure that all aspects of your system are running optimally and address any issues promptly.
