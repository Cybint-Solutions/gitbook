# Campaigns Dashboards

### Introduction

Upon logging into Lucy, the Dashboard presents an overview of all campaigns, active or inactive. It includes tools for quick campaign management—start, stop, copy, restore, or delete—and features like sortable columns, filters, and search to simplify navigation. An export option is also available for detailed analysis, making campaign oversight efficient and straightforward.

### Overview

<figure><img src="../.gitbook/assets/image (350).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Campaign" %}
"Campaigns" is the term used to describe security awareness programs, often named after specific divisions or locations for easier identification and organization.
{% endtab %}

{% tab title="Client" %}
The term "Client" can signify a single organization or, in a multi-tenant configuration, each organization is considered a separate client.

{% hint style="info" %}
Lucy segregates all data by client, ensuring that information is organized and secured on a per-client basis.
{% endhint %}
{% endtab %}

{% tab title="Type" %}
The type indicates the campaign's components, distinguishing between attack only, attack with awareness combined, or awareness only.

Phishing -> <img src="../.gitbook/assets/image (220).png" alt="" data-size="line">

&#x20;Awareness -> <img src="../.gitbook/assets/image (221).png" alt="" data-size="line">

&#x20;Phishing and Awareness -> <img src="../.gitbook/assets/image (219).png" alt="" data-size="line">
{% endtab %}

{% tab title="Status" %}
The current phase or condition of the campaign.\


<img src="../.gitbook/assets/image (259).png" alt="" data-size="line"> -> Before a campaign is launched

&#x20;<img src="../.gitbook/assets/image (260).png" alt="" data-size="line"> -> After a campaign has been launched

<img src="../.gitbook/assets/image (261).png" alt="" data-size="line">-> When a campaign has been stopped
{% endtab %}

{% tab title="Recipients" %}
The total number of recipients targeted by the campaign.
{% endtab %}

{% tab title="Started" %}
The date the campaign was started
{% endtab %}

{% tab title="Stopped" %}
The date the campaign was stopped
{% endtab %}

{% tab title="Sent" %}
The total count of emails that the campaign has successfully processed.
{% endtab %}

{% tab title="Clicked" %}
The number of recipients that clicked on the link in the email
{% endtab %}

{% tab title="Success" %}
The number of recipients successfully phished.
{% endtab %}

{% tab title="Trained" %}
The number of recipients that were successfully trained.
{% endtab %}
{% endtabs %}

***

### Campaign Actions

The Campaign Actions tab allows an administrator to quickly make changes to the selected campaign(s):\
\


<figure><img src="../.gitbook/assets/image (263).png" alt="" width="163"><figcaption></figcaption></figure>



**Copy:** Duplicate the selected campaign to create a new campaign with the same settings and content.

**Start:** Initiate the selected campaign, enabling it to begin sending out messages or performing its defined actions.

**Stop:** Halt the ongoing activities of the selected campaign without affecting other campaigns.

**Stop All:** Cease all active campaigns currently running across the system.

**Restart:** Stop and then immediately start the selected campaign to reset its activities.

**Archive:** Move the selected campaign to a storage area for inactive campaigns, removing it from active listings.

**Unarchive:** Retrieve the selected campaign from the archive to make it active or editable again.

**Restore:** Import and reinstate a campaign from an external backup file into the system.

**Backup:** Create a backup of the selected campaign's data and configuration for recovery or archival purposes.

**Delete:** Permanently remove the selected campaign and all its associated data from the system.

***

### Campaign Export

In the Dashboard, the "Export" feature provides administrators with a streamlined method to extract metrics from all campaigns or detailed statistics from a single chosen campaign. This functionality serves as a convenient access point for administrators to quickly gather comprehensive insights into campaign performance.\


<figure><img src="../.gitbook/assets/image (209).png" alt="" width="375"><figcaption></figcaption></figure>

#### **Campaigns:**

This export provides a comprehensive overview of each campaign, including its creation and active times, whether awareness components were enabled, the client name, the number of scenarios, recipients, messages sent, and the engagement metrics like opens, clicks, and responses. It offers insights into the campaign's performance and reach, including the average time spent on scenarios and awareness training.

<figure><img src="../.gitbook/assets/image (210).png" alt=""><figcaption></figcaption></figure>

#### **Campaign Scenarios:**

This export focuses on the individual scenarios within campaigns, detailing their creation time, name, duration, associated campaign, domain, language, status, template used, recipient engagement, and the time metrics for the first click and report after delivery. It gives detailed information on how recipients interact with specific scenarios, enabling analysis of scenario effectiveness.

<figure><img src="../.gitbook/assets/image (211).png" alt=""><figcaption></figcaption></figure>

### **Full Statistics for Selected Campaigns:**&#x20;

This export provides an in-depth analysis of individual interactions within a specific campaign. Here’s a breakdown of the data points included in the export:

* **Client and Campaign Details:** Identifies the client (e.g., Amazon) and the specific campaign name (e.g., Amazon Intranet Quishing), allowing for easy association of the data with its source.
* **Participant Information:** Includes detailed contact information and identifiers for the individuals targeted in the campaign, such as name, email, and a unique link provided to them.
* **Engagement Metrics:** Tracks the actions taken by recipients, including whether they clicked on a link (clicked), succeeded in a desired action (succeeded), were trained (trained), or reported the lure (reported), along with the timestamps for each action.
* **Campaign Effectiveness:** Presents key performance indicators such as success rate and click rate, offering insights into the overall effectiveness of the campaign.
* **Scenario and Awareness Details:** Details the specific scenario used in the campaign, the time spent on the scenario (scenario\_time), and any awareness components, including when awareness content was clicked (awareness\_clicked\_at) and the time spent on awareness (awareness\_time).
* **Additional Metrics:** Records other relevant data such as the subject of the email used in the campaign, time metrics related to the first click and report after delivery, and whether files were downloaded or data was collected.
*   **Outcome and Feedback:** Notes any out-of-office responses, bounced emails, and direct responses from the recipients, as well as whether a certificate was received or training (with or without a quiz) was completed, providing a comprehensive view of recipient engagement and learning outcomes.\
    \


    <figure><img src="../.gitbook/assets/image (212).png" alt=""><figcaption></figcaption></figure>

***
