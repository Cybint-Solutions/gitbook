# Attack Settings

## Campaign settings

In this section, you can specify the campaign name, associated client, and additional automation options. These options include setting an end date for the campaign and automatically generating a report template containing all campaign metrics. If enabled, a campaign report will be sent to the campaign creator upon completion.

<figure><img src="../../../../.gitbook/assets/image (240).png" alt="" width="563"><figcaption></figcaption></figure>

## Attack Settings

### **Domain**

Select an [attack domain you have registered](../../../settings/common-system-settings/domains/).\
This will be the primary domain for both the sender email address and the associated landing page.

<figure><img src="../../../../.gitbook/assets/image (242).png" alt="" width="421"><figcaption></figcaption></figure>

### **SSL**

You should never run an attack campaign from the same domain as your Lucy portal. When using a secondary domain, it's important to [create an SSL certificate](../../../settings/common-system-settings/ssl-settings/).

{% hint style="danger" %}
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could seriously affect the authenticity of your simulation if it's not properly set up.
{% endhint %}

If you've already created an SSL certificate you can use the **Select Existing SSL Certificate** option. If not, you can either manually **generate** one yourself or automatically generate and install one using **Let's Encrypt** (this is much easier).

<figure><img src="../../../../.gitbook/assets/image (1013).png" alt=""><figcaption></figcaption></figure>

### **Sender Name**, **Email**, and **Subject**

Here you will define from whom the Attack is being sent, their respective email address, and the subject.&#x20;

{% hint style="success" %}
It's recommended to use a sender email address that matches your registered attack domain. This practice enhances email deliverability by leveraging existing DNS records, reducing the risk of emails being caught by spam filters.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (243).png" alt="" width="423"><figcaption></figcaption></figure>
