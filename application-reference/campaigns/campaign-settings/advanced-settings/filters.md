# Filters

### Introduction

LUCY allows you to create filters within campaigns to control whether recipients can access the campaign. These filters, set by the campaign administrator, can be based on criteria such as mail clients, IP addresses, or IP ranges. In addition to enhancing security and targeting, filters help prevent false clicks by excluding automated systems or unintended interactions from services like Office365 ATP. This ensures that only the intended recipients can participate in the campaign, leading to more accurate statistics and effective engagement.

### Configuration

{% hint style="info" %}
Navigate to **Campaign -> Advanced Settings -> Filters**
{% endhint %}

#### Pre-defined Filters

Filters can be pre-defined and updated in the [Response Filte](../../../settings/common-system-settings/filter-settings.md)[rs ](../../../settings/common-system-settings/filter-settings.md)section of the platform to enable quick filter selection in campaigns.

#### Select Policy

{% tabs %}
{% tab title="Allow All" %}
The "Allow all (default)" setting in response filters permits every recipient to access the campaign, irrespective of their IP address or browser type.&#x20;

This default mode ensures that there are no restrictions on access, allowing for maximum reach and engagement with your intended audience. It's an inclusive approach, designed to facilitate widespread participation in the campaign without any preliminary filtering based on technical criteria.
{% endtab %}

{% tab title="Allow Only" %}
When you configure a response filter to "Allow only," it permits access solely to recipients or clicks that have an IP address or use a browser aligning with the rules you establish. All other recipients, whose details do not match your specified criteria, will be blocked.&#x20;

This setting is essential for creating highly targeted campaigns, where access is exclusively reserved for a predefined audience based on specific IP addresses or browser types.
{% endtab %}

{% tab title="Allow For" %}
When you set a response filter to "Deny for," it restricts access for recipients or bot clicks that have an IP address or use a browser matching any of the rules you specify. All other users, whose IP addresses or browsers do not match these rules, will be granted access.&#x20;

This feature is particularly useful for filtering out unwanted traffic or ensuring that your campaign targets only the intended audience.
{% endtab %}
{% endtabs %}

<figure><img src="../../../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

### **Preventing False Clicks**

In networks with strict policies, filters can ensure accurate statistics gathering. For example, ATP policies for Office365 track user clicks on phishing links and rewrite suspicious URLs. Consequently, the first request to the Lucy server is made by Microsoft services, which counts as a victim's action, resulting in unreliable statistics.

To avoid this, use the filters feature to deny access to specific IP addresses belonging to Microsoft protection services. The IP ranges for O365 ATP service are 40.94.0.0/16 and 104.47.0.0/16.

{% hint style="warning" %}
Please note, IP ranges may vary from client to client, and those mentioned above are known by the LUCY team. If these policies do not work, you may need to track which IP addresses the requests are made from.
{% endhint %}

{% hint style="info" %}
Adding Filter Rules can be combined with the built-in [Anti-Virus and Firewall ](../configuration/base-settings.md#antivirus-firewall-protection-interval)protection interval for the most accurate results.
{% endhint %}
