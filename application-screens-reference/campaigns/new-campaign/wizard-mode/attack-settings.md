# Attack Settings

Next up is to define the Campaign settings, Attack settings, and associate the relevant Awareness training.\
\
**3.1** Campaign settings:\
\
In this section, you can specify the campaign name, associated client, and additional automation options. These options include setting an end date for the campaign and automatically generating a report template containing all campaign metrics. The report will be sent to the email address of the administrative creator upon completion of the campaign.

<figure><img src="../../../../.gitbook/assets/image (240).png" alt="" width="375"><figcaption></figcaption></figure>

**3.2** Attack Settings:

Next, we will define the Attack parameters.\
\
**Domain** -> Select the attack domain you have registered in [step 2](../../../../guides/quick-guides/create-your-first-campaign/register-an-attack-domain.md) of the Quick Guides. This will be the primary domain to use for both the email address and the associated landing page.

<figure><img src="../../../../.gitbook/assets/image (242).png" alt="" width="281"><figcaption></figcaption></figure>

**SSL** -> Lucy is built with another efficient integration over API to the Let's Encrypt Certificate authority, which will automatically create, validate, and bind an SSL certificate to your attack domain.

<details>

<summary>What is SSL?</summary>

SSL (Secure Sockets Layer) is like a protective shield. It ensures that when your targets interact with the phishing page, their data remains secure and can't be intercepted by prying eyes. It's the trusty guard that makes sure your simulation stays safe and realistic.\
\
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could seriously affect the authenticity of your simulation if it's not properly set up. So, think of SSL as your trusty sidekick, keeping things legitimate and secure.

</details>

<figure><img src="../../../../.gitbook/assets/image (241).png" alt="" width="269"><figcaption></figcaption></figure>

**Sender Name**, **Email**, and **Subject** -> Here you will define from whom the Attack is being sent, their respective email address, and the subject.&#x20;

{% hint style="warning" %}
It's recommended to use a sender email address that matches your registered attack domain. This practice enhances email deliverability by leveraging existing DNS records, reducing the risk of emails being caught by spam filters.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (243).png" alt="" width="282"><figcaption></figcaption></figure>

**3.3** Editing the Email Content:\
\
The Lucy email editor is a dynamic tool that allows you to customize the email content according to your desired language and structural preferences. In most templates, you'll find variable placeholders like **%name%**, which automatically insert each recipient's name for personalization, enhancing the attack's relevance in a spear-phishing context. For a full list of placeholder variables, please see our dedicated section [here](../../../templates/variables-in-lucy.md).

<figure><img src="../../../../.gitbook/assets/image (245).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="warning" %}
In simulated attacks, the goal is to encourage users to click a link in the email. This action allows for the collection of click success statistics.
{% endhint %}

If you intend to create a **new** link in your email body, simply highlight the word/phrase and select the link icon, then enter the placeholder **%link%** in the text box:

<figure><img src="../../../../.gitbook/assets/image (246).png" alt="" width="563"><figcaption></figcaption></figure>

<details>

<summary>What is %link% ?</summary>

The **%link%** placeholder automatically generates a URL combining your registered attack domain with a unique tracking hash for each recipient, allowing for detailed tracking.&#x20;

For example, with "open-ai.net" as the domain, the recipient sees a link like "[https://open-ai.net/xvcskahjry](https://open-ai.net/xvcskahjry)", enabling precise monitoring of individual interactions.

</details>
