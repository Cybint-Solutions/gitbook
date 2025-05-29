# Mail Settings

### **Lucy Mail Delivery Methods**

Lucy provides various options for mail delivery, accommodating different needs and preferences for security awareness campaigns. Below is a comprehensive guide to utilizing these mail delivery methods effectively.\
\
Administrators have two choices for setting up mail delivery: globally or at the campaign level. Global settings affect all campaigns but can be overridden by campaign-specific settings, which only apply to the selected campaign. This flexibility allows for customized mail delivery preferences on a per-campaign basis:\


<details>

<summary>Global Mail Delivery Settings</summary>

Navigate to -> Settings -> Common System Settings -> Mail Settings\
\
Here you can choose your default method for sending emails. This setting will apply to all campaigns.\
\
![](<../../../.gitbook/assets/image (265).png>)

</details>

<details>

<summary>Campaign Mail Delivery Settings</summary>

Navigate to any campaign -> Configuration -> Attack/Awareness Settings -> Select the Scenario -> Mail Settings\
\
This is the campaign-based Mail Delivery settings, allowing an Administrator to deviate from the Global Mail Delivery settings for the specified scenario.\
\
![](<../../../.gitbook/assets/image (266).png>)

</details>

***

### Internal Postfix Server

Lucy incorporates a built-in internal mail server (Postfix) as its default method for email delivery. This approach is straightforward and often used due to its direct integration within Lucy. To enhance delivery success, it's advisable to align the server's name with Lucy's Fully Qualified Domain Name (FQDN), potentially using a subdomain designated for mail purposes.

***

### External Mail Relay (SMTP)

**Global Settings**

For broad application across all campaigns, Lucy allows the configuration of an external SMTP server via its general settings. This is particularly useful when aiming to circumvent spam filters that may block emails from new or untrusted IP addresses. Setting up involves adding your mail server details under "Settings -> Common System Settings -> SMTP Servers"; followed by a connection test to ensure proper setup. Please see our article on[ SMTP Servers](smtp-servers.md) for more information.

**Campaign-Specific Settings**

Within individual campaigns, it's possible to specify a unique mail delivery method, overriding the global settings if needed. This flexibility supports tailored delivery strategies for different campaigns.

***

### Pre-Paid, External Mail Server (via HTTP) - <mark style="color:red;">Currently Unavailable</mark>

{% hint style="danger" %}
<mark style="color:red;">Although previously offered, the option to utilize a pre-paid, external mail server via HTTP for mail delivery is currently under construction.</mark>
{% endhint %}

This method involved using an API to communicate with external servers like Sendgrid, offering a reliable alternative when other delivery methods faced spam filter obstacles. Campaign-specific settings allowed for the selection of limited sender domains, with the system designed to prevent reply captures to ensure security and privacy.

<details>

<summary>Configure HTTP Proxy </summary>

To configure the mail dleivery to HTTP Proxy as Global settings to your Lucy server, navigate to -> Settings -> Common System Settings -> Mail Settings\
\
Select **"HTTP Proxy"**\
\
You'll have the option to specify the mail sender's domain or name. This choice will override any campaign-specific settings, ensuring all emails in LUCY are sent with this configuration. Choosing "HTTP" as your delivery method limits the selection of sender addresses to a predefined list of domains.\
\


<img src="../../../.gitbook/assets/image (267).png" alt="" data-size="original">

The recipient will see the email's appearance vary based on the chosen domain.\
\


<img src="../../../.gitbook/assets/image (268).png" alt="" data-size="original">

Note: If a recipient replies to one of these emails, the reply-to address will be set to a "do-not-reply@example-domain.com" or similar, leading to a non-delivery error upon response. Therefore, replies to these pre-defined email domains cannot be collected.

**Mail Sender Domains for HTTP Proxy**: the following mail sender domains are pre-configured

* sendgrid.net
* security-information.xyz
* cloudservice24.xyz
* delivery365.website
* web-contest.host
* file-sharing.host
* mail-access.site
* onlineservices.space
* report365.us
* cloudaccess.space
* online-survey.site
* printservices.press
* webmail-access.space
* vpn-access.host
* online-statistics.site
* cloud-encryption.host
* web-login.site
* secure-login.host

</details>

***
