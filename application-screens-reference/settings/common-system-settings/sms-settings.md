# SMS Settings

### Introduction

LUCY features an integrated API that links to a central LUCY gateway to initiate SMS delivery. This gateway conducts initial checks to confirm if the LUCY client has enough credits and permission to send SMS messages. Once these verifications are successful, the gateway utilizes a secondary API to connect with an international SMS provider, such as MessageBird or SmsMode.

### Requirements

* A Commercial (Pro or Elite) license.&#x20;
* Enough balance for SMS dispatch.&#x20;
* Selecting an SMS provider.

### Setup

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> SMS Settings**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (275).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Default" %}
The Default SMS Setting will automatically integrate with our 3rd party provider [MessageBird](https://bird.com/).
{% endtab %}

{% tab title="Alternative" %}
Our alternative provider, [SmsMode](https://www.smsmode.com/en/), is specifically introduced to cater to our French customers, helping them navigate the strict regulations on sending promotional SMS messages within France.&#x20;

SmsMode offers capabilities for global SMS campaign sending, making it a versatile option for international outreach.
{% endtab %}

{% tab title="Custom" %}
The Custom option enables you to set up your own account with either [MessageBird](https://bird.com/) or [SmsMode](https://www.smsmode.com/en/), allowing for direct interaction with the SMS providers. By adding your API key, you gain access to features such as whitelisting, viewing SMS logs, and creating your own unique sending numbers, offering a more personalized and hands-on approach to managing your SMS campaigns.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Smishing campaigns are more complex to set up, as they involve variables beyond what Lucy handles directly. We recommend reaching out to your Customer Success Manager or Solution Engineer before starting a campaign to ensure everything is properly configured.
{% endhint %}

{% hint style="danger" %}
Before initiating any SMS campaigns, it's essential to submit whitelisting information to the SMS providers. This step ensures that your campaign's traffic is permitted across all relevant carrier networks, preventing potential delivery issues or restrictions.\
\
**Ensure to allocate a minimum of&#x20;**<mark style="color:red;">**4 weeks**</mark>**&#x20;for the completion of the whitelisting process.**
{% endhint %}

For more information on building a smishing attack, please see our [smishing guide](../../../guides/attack-simulations/attack-types/smishing.md).

### FAQ

<details>

<summary>How do I check my available balance?</summary>

1. On your license page:

\
&#x20;![](<../../../.gitbook/assets/image (277).png>)



2. On the Message Template for your Attack scenario:

![](<../../../.gitbook/assets/image (278).png>)

</details>

<details>

<summary>What are the cost per SMS?</summary>

One SMS costs 15 cents (USD)

</details>
