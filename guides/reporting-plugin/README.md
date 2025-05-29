# Reporting Plugin

### Introduction

Mail reporting plugins (AKA "phishing buttons") enhance email security by allowing users to report phishing attempts directly from their email clients. They streamline the process, making it easier for organizations to identify and respond to potential threats.

***

### Supported clients

* Office 365 (Desktop, Web, Mobile)
* Outlook 2016, 2019
* Outlook for Mac (2016, 2019)
* Gmail

### Prerequisites

A connected Azure application. See [here](../../application-screens-reference/settings/common-system-settings/azure-applications.md) for details.

This application must then be selected in the plugin settings.

### Client Profiles

Starting in Lucy version 4.13 you can save plugin configurations on a per-client basis (one profile per client). When you are ready to download the plugin you will be prompted to select a client, and the plugin will use that client's settings profile.

<figure><img src="../../.gitbook/assets/image (792).png" alt=""><figcaption></figcaption></figure>

### Plugin Settings

Before we can begin using the plugin we must configure it. To configure, navigate to **Settings > Submitted Email Settings > Plugin Settings** and create a new configuration. See [this platform reference page](../../application-screens-reference/settings/submitted-email-settings/plugin-settings.md) for details on the configuration options.

{% hint style="success" %}
Remember to select your Azure application in the Plugin settings at the bottom!
{% endhint %}

***

### Download the plugin

{% hint style="success" %}
You must [configure your plugin settings](../../application-screens-reference/settings/submitted-email-settings/plugin-settings.md) before downloading and deploying.
{% endhint %}

To download the plugin navigate to the **Incidents Dashboard** and select **Download Plugin**, then select the appropriate option for your mail client.

<figure><img src="../../.gitbook/assets/image (831).png" alt=""><figcaption></figcaption></figure>

* **User/Machine Wide:** MSI installer for Outlook Native
* ~~**Classic Microsoft Outlook 365:** XML file for O365 using REST API~~
* **Microsoft Outlook 365:** XML file for O365 using [Microsoft's Graph API](https://learn.microsoft.com/en-us/graph/)
* **Gmail Addon:** [App script](https://www.google.com/script/start/) for Gmail clients.

{% hint style="danger" %}
#### Deprecation notice for REST API plugin

Microsoft has ended support for REST-based plugins, please use the Graph API version.
{% endhint %}

In Lucy version 5.4 and above the download options have been updated to reflect this change:

<figure><img src="../../.gitbook/assets/image (978).png" alt=""><figcaption></figcaption></figure>

***

### Deployment

LUCY's reporting plugin is compatible with Microsoft O365, Outlook Native, and Gmail. The deployment is a little different for each version, so be sure to use the guide for your mail client.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td><strong>Microsoft Office 365</strong><br><strong>(XML)</strong></td><td></td><td><a href="deploying-office-365.md">deploying-office-365.md</a></td><td></td></tr><tr><td></td><td><strong>Outlook Native</strong><br><strong>(MSI)</strong></td><td></td><td><a href="deploying-outlook-native.md">deploying-outlook-native.md</a></td><td></td></tr><tr><td></td><td><strong>Gmail</strong><br><strong>(apps script)</strong></td><td></td><td><a href="deploying-gmail.md">deploying-gmail.md</a></td><td></td></tr></tbody></table>

