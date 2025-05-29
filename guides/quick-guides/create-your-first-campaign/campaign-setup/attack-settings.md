# Attack Settings

Next, define the Campaign and Attack settings, then link the relevant Awareness Training.\
\
**3.1** Campaign settings:\
\
Specify the campaign name, associated client, and additional options in this section.

<figure><img src="../../../../.gitbook/assets/image (240).png" alt="" width="375"><figcaption></figcaption></figure>

**3.2** Attack Settings:

Next, we will specify the parameters for the Attack.\
\
**Domain** -> Select the attack domain registered in [step 2](../register-an-attack-domain.md) of the Quick Guides. This will be the primary domain for the email address and the associated landing page.

<figure><img src="../../../../.gitbook/assets/image (242).png" alt="" width="281"><figcaption></figcaption></figure>

**SSL** -> Lucy seamlessly integrates with Let's Encrypt to automatically create, validate, and bind SSL certificates to your domain.

<details>

<summary>What is SSL?</summary>

SSL (Secure Sockets Layer) acts as a protective shield. It ensures that data exchanged with the phishing page remains secure and protected from eavesdropping. This safeguard helps maintain the realism and safety of your simulation.

Without an SSL certificate, recipients will see a red warning page, indicating an insecure site. This can undermine the authenticity of your simulation.

</details>

<figure><img src="../../../../.gitbook/assets/image (241).png" alt="" width="269"><figcaption></figcaption></figure>

**Sender Name**, **Email**, and **Subject** -> Define the sender of the attack, their email address, and the subject.

{% hint style="warning" %}
Using a sender email that matches your registered domain is recommended. This improves email deliverability by leveraging existing DNS records and reduces the risk of emails being flagged as spam.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (243).png" alt="" width="282"><figcaption></figcaption></figure>

**3.3** Editing the Email Content:\
\
The Lucy email editor is a versatile tool that lets you tailor email content to your preferred language and structure. Most templates include variable placeholders like **%name%**, which auto-insert each recipient's name for a personalized touch, making spear-phishing attacks more effective.

<figure><img src="../../../../.gitbook/assets/image (245).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="warning" %}
The objective of simulated attacks is to persuade users to click on an email link, enabling the collection of click-through statistics.
{% endhint %}

To add a **new** link in your email, highlight the desired word or phrase, click the link icon, and enter **%link%** in the URL field.

<figure><img src="../../../../.gitbook/assets/image (246).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
The `%link%` placeholder automatically generates a URL combining your registered attack domain with a unique tracking hash for each recipient, allowing for detailed tracking.

For example, with "open-ai.net" as the domain, the recipient sees a link like "[https://open-ai.net/<mark style="background-color:red;">xvcskahjry</mark>](https://open-ai.net/xvcskahjry)", enabling precise monitoring of individual interactions.
{% endhint %}
