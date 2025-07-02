# Backup Settings

### Introduction

Administrators can configure regular, automatic backups of their workstation. These backups are stored locally and help to preserve snapshots of your installation.

***

### Configuration

{% hint style="info" %}
Navigate to **Settings -> Backup Settings**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (638).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Backup Target" %}
You can choose which parts of the system you want to back up.\
If you don't want to back up anything, click "Deselect All".&#x20;

<figure><img src="../../../.gitbook/assets/image (639).png" alt=""><figcaption></figcaption></figure>

* **Database**: Backs up the entire Lucy database by creating an SQL dump.
* **Files**: Saves a copy of the folder "/opt/phishing/files", which includes data for campaigns, templates, and more. It's usually good to back this up along with the Database.
* **Emails**: Creates a backup of the Mail Manager's settings and all its folders.
* **Config**: Saves copies of Lucy’s configuration files for web and mail servers, among others.
* **Code**: Backs up Lucy's source code and executable files.
{% endtab %}

{% tab title="Backup Frequency" %}
Configure how often the backup job runs:

<figure><img src="../../../.gitbook/assets/image (640).png" alt=""><figcaption></figcaption></figure>

Note that creating backups more frequently will consume more storage on your workstation.

See the "Backup Days" tab for examples of how to use each setting.
{% endtab %}

{% tab title="Backup Time" %}
The backup job will run at the specified time. The job can take some time and consumes resources on your server while it is running (RAM and CPU), so it's a good idea to schedule this at a time when you expect decreased activity on the server, such as overnight or on weekends.

<figure><img src="../../../.gitbook/assets/image (641).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Backup Days" %}
For Weekly, Monthly, and Yearly backups, you can choose specific days and months for scheduling. Use commas to separate values within the same category and semicolons to distinguish between months and days.

<figure><img src="../../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>

* **Weekly:** 1-7 for each day of the week. For example `1,3,5` will create backups every Sunday, Tuesday, and Thursday.
* **Monthly:** 1-31 for days. For example, `1,15` will create backups on the 1st and 15th of every month.
* **Yearly:**  1-12 for months, 1-31 for days. For example, `1,3,5,7;1,15` will create backups on the 1st and 15th of January, March, May, and July.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Notify About Errors**

When this setting is enabled, the [notification email](../advanced-system-settings/advanced-settings.md#system-notification-email) defined in the **Advanced System Settings** will send an email to your Lucy admins if the backup operation encounters an error.
{% endhint %}

### Automated backups location

Backup files are stored locally on your workstation, in the `/opt/phishing/files/db-backups` directory.
