# Attack Settings

## **Domain**

Select an [attack domain you have registered](../../../settings/common-system-settings/domains/).\
This will be the primary domain for both the sender email address and the associated landing page.

<figure><img src="../../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

## **SSL**

When using an attack domain, it's important to [create an SSL certificate](../../../settings/common-system-settings/ssl-settings/).

{% hint style="danger" %}
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could seriously affect the authenticity of your simulation if it's not properly set up.
{% endhint %}

If you've already created an SSL certificate you can use the **Select Existing SSL Certificate** option. If not, you can either manually **generate** one yourself or automatically generate and install one using **Let's Encrypt** (this is much easier).

<figure><img src="../../../../.gitbook/assets/image (1013).png" alt=""><figcaption></figcaption></figure>

## **Sender Name**, **Email**, and **Subject**

Here you will define from whom the Attack is being sent, their email address, and the subject.&#x20;

{% hint style="success" %}
It's recommended to use a sender email address that matches your registered attack domain. This practice enhances email deliverability by leveraging existing DNS records, reducing the risk of emails being caught by spam filters.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## Template Language

Select a default language for the template. Later on you can add additional language configurations.

<figure><img src="../../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## Email Preview

Later on you can edit this email, for now the campaign wizard simply shows you what the template email looks like.

<figure><img src="../../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

