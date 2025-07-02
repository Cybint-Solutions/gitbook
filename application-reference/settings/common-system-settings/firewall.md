# Firewall

### Overview

Firewall settings in the Lucy are crucial for securing access to various services, including SSH, HTTP/HTTPS, and the admin panel.&#x20;

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> Firewall**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (201).png" alt=""><figcaption></figcaption></figure>

### **HTTP & HTTPS Access Range**

* **Purpose:** To define specific IP ranges that can access HTTP or HTTPS services. This is essential for controlling access to phishing simulations and the administrative GUI.
* **Configuration:**
  * Include the IP range of your users to ensure they can access phishing simulations.
  * To restrict access to the admin GUI while running campaigns, enable HTTP only for campaigns and restrict HTTPS access.

### Custom Admin Port

* **Purpose:** To change the default port for accessing the Lucy administrative interface.

#### Admin Access IP Range

* **Purpose:** To specify IP ranges allowed to access the Lucy admin panel, enhancing security by limiting access to authorized personnel only.

### Configuration Steps

1. **Access Firewall Settings:** Log in to the Lucy admin interface and navigate to `your.lucydomain.com/admin/settings/firewall`.
2. **Adjust Settings:** Configure each setting according to your security requirements:
   * Enable SSH block if necessary.
   * Define IP ranges for HTTP/HTTPS access.
   * Set a custom admin port (if applicable).
   * Specify IP ranges for admin panel access.
3. **Save Changes:** Ensure all configurations are saved properly.

<details>

<summary>I changed the Admin port but my firewall blocks access to that port</summary>

To revert the admin port in LUCY to 443 from a custom port (e.g., 8081), you need to access the system via SSH or directly. This process involves modifying Apache's configuration to stop listening on the custom port and ensure it listens on 443, removing specific virtual host configurations, resetting IP tables, updating the database to reflect the change, and finally restarting Apache to apply these changes. This procedure ensures the firewall no longer blocks access due to the custom admin port.\
\
**Login via the terminal and execute these commands:**\
`cd /etc/apache2`\
`nano ports.conf`\


**comment two lines**:\
`#Listen 8081`\
`#NameVirtualHost *:8081`\


**Save and exit**\
Press Ctrl+O+Enter and Ctrl+X to save\&exit.\


**Change virtual host configuration**\
`nano sites-available/phishing-ssl`\
`edit the first line like to:`\
`<VirtualHost *:443>`

**Save & Exit**\
Press Ctrl+O+Enter and Ctrl+X to save\&exit.\


**Remove entries**\
`rm sites-enabled/phishing-ssl-extra`\
`rm sites-available/phishing-ssl-extra`\


**Change IP-Tables**\
`iptables -F LUCY_ADMIN`\
`iptables -D INPUT -j LUCY_ADMIN`\
`iptables -X LUCY_ADMIN`\
`iptables -N LUCY_ADMIN`\
`iptables -I INPUT -j LUCY_ADMIN`\
`iptables-save`



**Update database**

```
sudo -u postgres psql phishing -c "UPDATE system SET value=null WHERE name='admin_port'"
```

\
**Restart Apache**\
`service apache2 restart`\
\


</details>

### Conclusion

Properly configuring firewall settings is essential for securing your Lucy Security Awareness application against unauthorized access. By carefully setting up access controls for SSH, HTTP/HTTPS services, and the admin panel, you can maintain a secure environment for both your phishing simulations and administrative operations.
