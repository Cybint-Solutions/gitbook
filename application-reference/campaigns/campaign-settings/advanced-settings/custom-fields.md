# Custom Fields

### Introduction

Beyond the common statistical data in LUCY, such as link clicks and submitted form data, you might want to track additional custom statistics from a live campaign. These custom statistics can provide deeper insights into user behavior and response to phishing campaigns.

{% hint style="info" %}
Custom Statistics require per-recipient manual intervention, making them ideal for manually tracking specific statistics that do not apply to the general group.
{% endhint %}

***

### Examples of custom statistics

* CERT (Computer Emergency Response Team) responses from users.
* Users who replied to the attacker.
* Users who participated in security training programs prior to the phishing campaign.

***

### Configuration

{% hint style="info" %}
Navigate to **Campaign -> Advanced Settings -> Custom Fields**
{% endhint %}

Select "Add" to add a custom field to your campaign.&#x20;

<figure><img src="../../../../.gitbook/assets/image (494).png" alt=""><figcaption></figcaption></figure>

Click "Save" to commit your custom fields.

***

### **Tracking Custom Statistics**

Once the campaign has started and you receive feedback on user actions, follow these steps to track custom statistics:

* **Go to Campaign Statistics**
  * &#x20;**Campaign Name** → **Statistics** → **Recipients**.
* **Select Recipients**
  * Choose the recipient(s) who "Completed Office Security Webinar".
* **Activate Custom Fields**
  * The custom field(s) will appear as a checkbox next to the recipient's information. Activate the checkbox for  "Completed Office Security Webinar".

<figure><img src="../../../../.gitbook/assets/image (495).png" alt=""><figcaption></figcaption></figure>

***

### **Use the Data in Reports**

[Generate a report](../results/exports.md) that includes the custom field to analyze the effectiveness of the campaign and user responses. Export the data to CSV for a comprehensive review.
