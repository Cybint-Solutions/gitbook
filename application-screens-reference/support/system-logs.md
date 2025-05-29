# System Logs

Introduction

Lucy maintains an internal log of application events. This allows for comprehensive monitoring and investigation of most application events, beyond just the service logs (e.g., Apache2 web server, Postfix mail server). By analyzing these logs users can effectively track and diagnose errors within the application.

{% hint style="info" %}
Navigate to **Support -> System Logs -> Service Logs**
{% endhint %}

***

### How to view mail and web server logs

First select a file from the dropdown menu. On this page you can view the postfix mail log as well as the web server access and error logs.

<figure><img src="../../.gitbook/assets/image (877).png" alt=""><figcaption></figcaption></figure>

Next define an interval, and Lucy will automatically paginate all the log entries from that file within that time frame. Keep in mind that log files are appended, meaning the most recent entries will be at the **end** of the file.

***

### How to export log files from Lucy

Often it is necessary to extract not just the mail and web server logs, but also runtime log files from the environment. Lucy offers a convenient way to download the runtime logs with a single click, just go to **Support > System Logs > Send Logs** and click the **Download Logs** button in the top-right.

<figure><img src="../../.gitbook/assets/image (878).png" alt=""><figcaption></figcaption></figure>

You will download a `.zip` archive with the following:

* `mail.log` (postfix log)
* `access.log` and `error.log` (apache2 logs)
* All log files in `/opt/phishing/runtime/` (Lucy's application runtime logs)

***

### Runtime logs

The `/opt/phishing/runtime/` folder contains a number of log files. Here is a breakdown of what types of operations are logged in each file.

<table><thead><tr><th width="243">File</th><th>Content</th></tr></thead><tbody><tr><td>application.log</td><td>Application errors from the database and web server.</td></tr><tr><td>awarenessrescheduler.log</td><td>Notifications for rescheduled awareness messages sent to recipients.</td></tr><tr><td>console.log</td><td>Events from various services and utilities used by background processes.</td></tr><tr><td>mailcrawler.log</td><td>Events related to the mail manager job.</td></tr><tr><td>migration.log</td><td>Activities during Lucy version migrations (for versions &#x3C; 4.2).</td></tr><tr><td>proxystat.log</td><td>Events related to proxy operations when Lucy is behind a proxy.</td></tr><tr><td>reminders.log</td><td>Events related to campaign reminders.</td></tr><tr><td>reqsue_emailparse.log</td><td>Events for the email parsing job.</td></tr><tr><td>resque_enduser.log</td><td>Updates to victim statistics.</td></tr><tr><td>resque_letsencrypt.log</td><td>Events related to Let's Encrypt API interactions.</td></tr><tr><td>resque_scheduler.log</td><td>Scheduler events, including start and finish times for each recipient's schedule.</td></tr><tr><td>resque_ssl.log</td><td>SSL-related events such as certificate creation, renewal, and import.</td></tr><tr><td>resque_stats.log</td><td>Updates to campaign statistics displayed in the web interface.</td></tr><tr><td>resque_system.log</td><td>System performance-related jobs such as updates, reboots, shutdowns, and process terminations.</td></tr><tr><td>resque_victim.log</td><td>Events related to assigning recipient groups to campaigns.</td></tr><tr><td>resque_visit.log</td><td>Recipient visits to scenario web pages (both attack and awareness). The victim's ID is used to anonymize personal data, while visit data (IP address, user agent, OS, etc.) is recorded.</td></tr><tr><td>resque_worker.log</td><td>All Lucy events. Each job logs at least two notifications: start and finish.</td></tr><tr><td>scheduler.log</td><td>Scheduler activities.</td></tr><tr><td>systemmonitoring.log</td><td>System status and health information.</td></tr></tbody></table>

***

### Campaign Logs

Each campaign in Lucy maintains its own message and error logs, which you can find in the campaign menu on the left of every campaign:

<figure><img src="../../.gitbook/assets/image (833).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Supervision log" %}
If you have supervisor users managing campaigns, a record of their actions will appear here.
{% endtab %}

{% tab title="Message log" %}
You can sort messages logs by type or search by text, and here you can also clear the message log to reset the campaign status.
{% endtab %}

{% tab title="Errors" %}
A record of any error messages the campaign received while transmitting. These error messages originate from your recipient servers, Lucy simply displays any error responses that it received in relation to this campaign.


{% endtab %}
{% endtabs %}

***
