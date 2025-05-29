# Backup and Restore

### Location of backup files

{% hint style="info" %}
Navigate to **Settings -> Backup & Restore > Backups**
{% endhint %}

All backups are stored in a centralized directory on your server: `/opt/phishing/backups`. Backups and exports are displayed in the dashboard under **Settings -> Backup & Restore**.&#x20;

<figure><img src="../../../.gitbook/assets/image (730).png" alt=""><figcaption><p>Here you can view, download, and delete your backups and exports.</p></figcaption></figure>

***

### What data can I back up?

You can create backups of your campaigns and templates from the dashboard by selecting the object you want to backup and then selecting "Backup" from the Actions menu:

{% tabs %}
{% tab title="Campaigns" %}
<figure><img src="../../../.gitbook/assets/image (727).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
A campaign backup is a tar.gz archive that contains the following:

* Campaign settings and statistics.
* Email and Landing Page templates.
* LUCY version info.
{% endhint %}
{% endtab %}

{% tab title="Templates" %}
<figure><img src="../../../.gitbook/assets/image (729).png" alt=""><figcaption><p>You can backup Attack, Awareness, Attachment (File), and Report templates. </p></figcaption></figure>

{% hint style="info" %}
A template backup is a .tar.gz archive that contains the following:

* Email and Landing Page files (html, css, javascript files).
* Static assets (like images and videos).
* SCORM data (if the template is SCORM-compatible).
{% endhint %}
{% endtab %}
{% endtabs %}

***

### Restoring backups

You can restore backups to any LUCY server with the same Actions menu.\*

Just select "Restore" and then select the template's archive from your file browser.

{% hint style="warning" %}
\*Backups should be restored on a server running the same LUCY version as the one used to create the backup. Avoid mixing different versions to prevent compatibility issues.
{% endhint %}

***
