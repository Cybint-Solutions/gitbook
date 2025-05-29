# Filter Settings

## Introduction

Filters in Lucy provide an additional layer of protection to minimize false positives and control access to the platform's web pages. These filters, applicable both at the campaign and system-wide levels, enable you to allow or block specific IP addresses and user-agent strings. This feature enhances security by preventing unauthorized access and mitigating false-positive clicks caused by antivirus tools and spam filters.

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> Filter Settings**
{% endhint %}

***

## Policies

{% tabs %}
{% tab title="Allow All" %}
The **Allow All** setting grants unrestricted access to the campaign, regardless of the recipient's IP address or browser type. This default configuration removes access limitations, maximizing reach and engagement with your target audience. It offers an inclusive approach, encouraging broad participation without applying any technical filters.
{% endtab %}

{% tab title="Allow Only" %}
The **Allow Only** setting permits access exclusively to recipients or clicks that match the IP address or browser rules you define. All other recipients whose details do not meet these criteria will be blocked. This setting is ideal for creating highly targeted campaigns, where access is reserved for a predefined audience based on specific IP addresses or browser types.
{% endtab %}

{% tab title="Deny For" %}
The **Deny For** setting restricts access for recipients or bot clicks that match the IP address or browser rules you specify. All other users whose IP addresses or browsers do not meet these rules will be granted access. This feature is particularly useful for filtering out unwanted traffic and ensuring your campaign reaches only the intended audience.
{% endtab %}
{% endtabs %}

## Campaign Filters

Campaign filters are pre-defined lists of rules that can be loaded in to any campaign.

### Create a Filter

To create a campaign filter list, go to the **Campaign Filters** tab and select **+ Add New**. Give the list a name and client, then **Save**. Next select a policy and add IP addresses and/or user-agent strings to it. When you're done, click **Save** again.

<figure><img src="../../../.gitbook/assets/image (916).png" alt=""><figcaption></figcaption></figure>

### Import Filters

You can also import rules from a CSV.\
To download a sample CSV file click the tooltip icon next to the import button:

<figure><img src="../../../.gitbook/assets/image (917).png" alt=""><figcaption></figcaption></figure>

### Add Filter to a Campaign

After creating your campaign filters you can add them to any campaign by going to that campaign's **Filter Settings**.

{% hint style="info" %}
Navigate to **Campaign -> Advanced Settings -> Filter Settings**
{% endhint %}

Here you can add filters manually or import the pre-defined rules you've created:

<figure><img src="../../../.gitbook/assets/image (918).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Importing a pre-defined filter overwrites all existing filters, so be sure to import your filter first before adding any additional ones.
{% endhint %}

***

## System Filters

System filters are applied to every campaign.

### Create a Filter

To create a system filter, go to the **System Filters** tab and select **+ Add New**. Select either IP or User-Agent and enter a value and description for the filter. Then select a policy type. When you're done, click **Save** at the bottom of the page.

<figure><img src="../../../.gitbook/assets/image (919).png" alt=""><figcaption></figcaption></figure>

### Automatic Filters

Lucy runs a background service that automatically detects bot-like behavior and adds the source IP(s) to the filter list with a "Deny Always" policy.

{% hint style="danger" %}
If users are reporting that they cannot access content, check this page for their source IP. If they are using a VPN (and therefore connecting from the same source IP as many other users), Lucy may have blocked the IP.

To resolve this permanently simply flip the policy from "Deny Always" to "Allow Always". Better yet, create an Allow policy for your VPNs in advance to avoid this issue entirely.
{% endhint %}

