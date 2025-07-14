# Advanced Settings

## Introduction

The Advanced settings in Lucy offer administrators detailed control over security, storage management, server time settings, global anonymization, and system notifications.

{% hint style="info" %}
Navigate to Settings > Advanced System Settings > Advanced Settings&#x20;
{% endhint %}

***

## **Date & Time**

Displays the current date and time according to the Lucy application server's clock.

#### **Automatically adjust DST**

Adjust for daylight saving time automatically.

#### **Time Zone**

This dropdown allows you to set the time zone that the Lucy server should operate in, aligning tasks and operations with local time.

{% hint style="warning" %}
If you have active campaigns with running [Schedules](../../campaigns/campaign-settings/configuration/schedule/), you will not be able to change the Time Zone until these campaigns have been stopped.
{% endhint %}

#### **Date Format**

Customize how dates are displayed throughout the Lucy application, allowing consistency with regional format preferences.

***

## **Proxy Settings**

When checked, this enables the use of a proxy server for network communications. It is useful if Lucy operates within a network that restricts direct internet access.

{% tabs %}
{% tab title="Proxy Host" %}
This field should be filled with the hostname or IP address of the proxy server that Lucy should use to route traffic.
{% endtab %}

{% tab title="Proxy Port" %}
Enter the port number on which the proxy server listens. Common proxy ports include 8080, 80, or 3128, but this can vary depending on the proxy service configuration.
{% endtab %}

{% tab title="Proxy Login" %}
If the proxy server requires authentication, input the username or login ID here.
{% endtab %}

{% tab title="Proxy Password" %}
Corresponding to the Proxy Login, this is where you would input the password associated with the proxy user account.
{% endtab %}

{% tab title="Do not use proxy for Master/Slave" %}
Check this option to ignore proxy server settings for communication between Master and Slave servers. This is useful when both servers are on the local network.
{% endtab %}
{% endtabs %}

***

## **Storage Management**

Manage how Lucy archives or deletes stopped campaign scenarios and Incidents to optimize storage usage.

#### Incident Management

Deletes Incident Reports Automatically:

* **Daily Deletion:** Incident reports are deleted every day at 02:00.
* **Weekly Deletion:** Incident reports are deleted every Sunday at 02:00.
* **Monthly Deletion:** Incident reports are deleted on the first day of each month at 02:00.

#### Scenario Management:

* Automatically Archive: Choose to automatically move stopped campaigns to an archive after a specified number of months.
* Automatically Delete: Set Lucy to automatically delete stopped campaigns after a certain period, maintaining storage efficiency.

***

## **Default Editor Type**

Select the default editor interface for crafting campaigns and templates in Lucy, such as a visual editor for a more intuitive, design-focused experience.

***

## **Template Rating**

Optionally disable the prompt asking users to rate templates on a five-star scale.

***

## Auto Logout Timeout

Specify the time (in minutes) before users are logged out for inactivity.

***

## **Automatic Updates**

Lucy' can downlaod and install essential updates automatically, addressing critical issues prevalent across various environments that require immediate action.

{% hint style="danger" %}
Turning off this setting will exclude your server from receiving automatic patch updates, which cover essential bug fixes and security enhancements.&#x20;
{% endhint %}

***

## **Password Policies**

<figure><img src="../../../.gitbook/assets/image (1003).png" alt=""><figcaption></figcaption></figure>

#### Password Rotation

Force users to renew their passwords every 1, 3, 6, or 12 months.

#### 2FA Key

This input field is where you should enter your Authy 2FA API key. To obtain this key, you must create an account at [Authy.com](https://www.twilio.com/try-twilio), a two-factor authentication (2FA) service provider. Once you have an account, Authy will provide an API key which you can input here to enable 2FA for added security in your Lucy application.

#### Password History

Remember a user's previous N passwords and prevent them from re-using any of those passwords.

#### Most Used Passwords

Prevent the use of common passwords that are deemed too weak or used too frequently.

#### Brute Force Protection

Integrate a CAPTCHA challenge on the login page.

#### Account Lockout

Restrict access to login and password recovery after multiple failed attempts from the same IP address. Separate restrictions are available for login and recovery attempts, as well as for the Administration Panel and End User Portal.

***

## Enable Ajax Updating

Ajax (Asynchronous JavaScript and XML) allows a webpage page to refresh or update content dynamically without the need to reload the entire page.

#### **Ajax Update Period (seconds)**

This field allows you to set the frequency, in seconds, at which the Ajax calls will occur to update or refresh content. In the example given, with it set to '5', Ajax will make a call to the server every five seconds to check for and retrieve any new data. This keeps the displayed content up to date in near real-time, improving user experience by providing the latest information without manual page refreshes.

***

## Export Data Separator

This option allows you to select the character that will be used to separate fields in exported data files. The options provided are comma, tab, colon, and semicolon. For example, choosing 'Tab', as highlighted, means that each field in the exported data will be separated by a tab space, typically used in TSV (Tab-Separated Values) files.

#### **Export Double Quotes**

An additional setting related to enclosing all fields in double quotes during data export. This is commonly used to ensure that field data that might contain commas or other separators are treated as single fields in the exported data.

***

## Campaign Approval Period (days)

A [Supervisor](../../users/administrative-users.md#supervisor) must approve a campaign within this period, otherwise the launch will be rejected.

***

## **Spam Test**

This setting, when enabled, allows for the campaign content to be checked against the complete spam blacklist database. Utilizing the full list for spam checking could significantly slow down the process due to the extensive nature of the blacklist. This option would enhance the thoroughness of the spam filtering but at the cost of performance speed.

***

## **Generate Short Recipient Links**

By enabling this option, the system will create concise links for recipients, limited to a maximum of five alphanumeric characters. This feature is designed to make links more manageable and user-friendly, potentially increasing the likelihood that recipients will engage with them. Selecting this option can be particularly useful in simplifying the appearance of URLs and making communications look cleaner.

***

## **Let's Encrypt Autorenew**

Automatically renew the admin domain's [SSL certificate](../common-system-settings/ssl-settings/).\
Only available if using HTTP mode for Let's Encrypt.

***

## **Disable Campaign Checks**

If checked, this option would deactivate certain automated checks that are typically run on campaigns before they are launched. This includes validation of links, checking for spam triggers, etc.

***

## **Benchmark Sharing**

* **Send Anonymous Benchmark Data**: By selecting this option, the system would anonymously send data regarding campaign performance to a central benchmarking service, helping to compare the effectiveness of campaigns against a broader dataset.
* **Don't ask to send Anonymous Benchmark Data**: This option, when checked, will not ask to send data for benchmarking purposes.

***

## Anonymous settings

**Global Anonymous Setting**: Activating this setting will apply anonymity by default to all campaigns, ensuring that all collected data lacks personally identifiable information, in compliance with various privacy laws.

#### Anonymize Recipient Attributes:

* **Hide Country Attribute**: Masks the country information of the recipients in reports.
* **Hide OS Attribute**: Conceals the operating system details of the recipients' devices.
* **Hide Browser Attribute**: Omits the browser type used by the recipients.
* **Hide Location Attribute**: Removes the location data of the recipients from visibility.
* **Hide Division Attribute**: Hides the division or departmental information of the recipients.
* **Hide Comment Attribute**: Ensures that any comments or notes related to recipients are not shown.
* **Hide Staff Type Attribute**: Obscures the designation or staff type of the recipients.

***

## Use DLP Activation String

The DLP String functionality is designed to enhance email security by embedding specific identifying data within the body of emails:

* **DLP String Activation**: When enabled, this feature allows for the inclusion of specific data points in the email body to help classify emails and manage responses effectively.
* **Data Included in DLP String**:
  * Recipient's Email
  * Email's SHA256 hash
  * Victim ID, a unique identifier within the system
  * Campaign ID, which identifies the specific email campaign

By enabling the DLP String, users can organize and sort victims' replies in the [Mail Manager](../../support/mail-manager.md) with greater ease, allowing for more efficient email management and review processes.

* **Invisibility of DLP String**: If discretion is required, the visibility of the DLP string can be concealed by setting the DLP String Font Size to 0px. This ensures that the string does not disrupt the recipient's reading experience while still maintaining the functionality for administrative purposes.

***

## Local IP Address

Specify the IP address to use as the local IP address.

***

## System Notification Email

This setting is used to specify the email address from which system-generated notifications, such as alerts, password reset notifications, updates, or automated responses, are sent to users.

{% hint style="info" %}
Lucy will send system notification emails from the defined mail server (internal postfix/external SMTP) as defined in [Mail Settings](../common-system-settings/mail-settings.md)
{% endhint %}

***
