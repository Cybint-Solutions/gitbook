# SSL Settings

### Introduction

LUCY provides the ability to generate SSL certificates for various purposes, including campaigns, admin interface access, and end-user portal access. Here's a concise guide on how to generate SSL certificates in LUCY.

<details>

<summary>What is an SSL certificate?</summary>

SSL (Secure Sockets Layer) is like a protective shield. It ensures that when your targets interact with the phishing page, their data remains secure and can't be intercepted by prying eyes. It's the trusty guard that makes sure your simulation stays safe and realistic. Similarly, your administrative interface also requires an SSL certificate to encrypt and keep your data secure.\
\
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could seriously affect the authenticity of your simulation if it's not properly set up. So, think of SSL as your trusty sidekick, keeping things legitimate and secure.

</details>

### Admin Interface Certificate

\
Ensure you have a domain configured for your Lucy server

{% tabs %}
{% tab title="VPS" %}
Each VPS server provided by Lucy Awareness comes with a default administrative domain, such as access.cloudserver123.com. Should you wish to use a custom domain instead, please refer to our guide on [custom domain configuration.](../domains/#dns-records-explained)
{% endtab %}

{% tab title="Self Hosted (on-prem)" %}
Configure your domain within LUCY's [setup script](broken-reference). For instance, if your domain is "company.com," you might set up an FQDN like "access.company.com."
{% endtab %}
{% endtabs %}

**Admin Certificate Generation**:

Navigate to "Settings -> Common System Settings -> SSL Settings" in the LUCY admin interface.

<figure><img src="../../../../.gitbook/assets/image (269).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Make sure to set the "Let's Encrypt Notification Email" to an email address you control. This will ensure you receive notifications about SSL certificate expirations.
{% endhint %}

**Let’s Encrypt Mode**

{% tabs %}
{% tab title="HTTP" %}
* **How it Works**: The HTTP challenge requires you to place a specific file with specific content, provided by Let's Encrypt, on your web server. Lucy will automatically create this file and no further action is needed from the administrator. Let's Encrypt CA then makes HTTP requests to this URL to verify that the file exists and has the correct content.&#x20;
* **Use Case**: This challenge is suitable for websites and services already accessible via HTTP. It's straightforward if you can easily upload files to your server and make them accessible over the web.
* **Advantages**:
  * Simple and quick for web servers and sites already running.
  * Direct verification of your domain through the web server.
* **Limitations**:
  * The server must be publicly accessible via port 80.
  * Not suitable for wildcard certificates directly (wildcard certificates require a DNS challenge).
{% endtab %}

{% tab title="DNS" %}
* **How it Works**: The DNS challenge requires you to create a DNS TXT record under the domain you're validating. The record's name is `_acme-challenge.<your_domain>`, and its value is a token provided by Lucy when this option is selected. Let's Encrypt then queries the DNS system for this TXT record to verify domain ownership.\
  \
  ![](<../../../../.gitbook/assets/image (272).png>)
* **Use Case**: This challenge is particularly useful for:
  * Obtaining wildcard certificates (e.g., `*.example.com`), which secure all subdomains of a domain.
  * When HTTP validation is not possible or practical, such as when the server isn't accessible from the internet on port 80.
*   **Advantages**:

    * Enables validation of domains without having to host a website.
    * Necessary for issuing wildcard certificates.


* **Limitations**:
  * Requires access to manage DNS records.
  * DNS propagation might delay the validation process since the changes must propagate throughout the internet's DNS system before Let’s Encrypt can verify it.
{% endtab %}
{% endtabs %}

Select "Use Custom SSL Certificate" - You will be presented with three options:

{% tabs %}
{% tab title="Let's Encrypt" %}
Our default method, designed for maximum user-friendliness, enables your Lucy server to automatically generate a Certificate Signing Request (CSR) through the integrated Let's Encrypt API. It then submits this request to Let's Encrypt and automatically installs the full certificate chain on your Lucy server.&#x20;

This process may take up to 5 minutes to complete. Please wait for the "certificate successfully generated" notification before proceeding further.

{% hint style="info" %}
Let's Encrypt certificates are issued with a maximum validity period of 90 days.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (270).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Please be aware that Let's Encrypt, a third-party SSL provider, imposes certain limitations. One notable restriction is the issuance cap of no more than 5 certificates per week for the same domain name. For additional details on these limitations, you can visit: [Let's Encrypt Rate Limits](https://letsencrypt.org/docs/rate-limits/).
{% endhint %}
{% endtab %}

{% tab title="Generate or Upload" %}
This option is ideal if you already have an SSL certificate chain from a trusted certificate authority or if you would like to generate a self-signed certificate.&#x20;

{% hint style="info" %}
Be aware that self-signed certificates are not issued by trusted certificate authorities. As a result, browsers will mark your domain as not secure when using these certificates.
{% endhint %}

**Option 1: Generate a self-signed Certificate**

<figure><img src="../../../../.gitbook/assets/image (274).png" alt="" width="301"><figcaption></figcaption></figure>

1. **Domain**: Enter the domain name for which you want to generate the SSL certificate (e.g., lucysecurity.help).
2. **Email**: Provide a valid email address. This is where Let's Encrypt will send notifications about your certificate, such as renewal reminders.
3. **Details**: Fill in the Country, State, City, Organization Name, and Organizational Unit. These details are often used in the certificate's subject field and can be important for organizational certificates.
4. **Generate**: Click on the "Generate Certificate" button to create your self-signed certificate.

#### Option 2: Upload an Existing Certificate

1. **SSL Certificate**: Click "Choose File" to browse and select your existing certificate file (usually a `.crt` or `.pem` file).
2. **SSL Key**: Click "Choose File" to upload the private key file associated with your SSL certificate (this is a `.key` file and must be kept secure).
3. **SSL Key Password**: If your private key is password-protected, enter the password here.
4. **SSL Chain**: Click "Choose File" to upload the chain file (also known as the CA bundle or intermediate certificate) if required. This is needed for browsers to trust your certificate by establishing a chain of trust to a root certificate.
5. **Wildcard**: If you are uploading a wildcard certificate, you would check the "Wildcard" box. Wildcard certificates secure a domain and all its subdomains (e.g., `*.example.com`).
{% endtab %}

{% tab title="Use Existing SSL Certificate " %}
Choose this option if you have already generated an SSL certificate and uploaded it to your Lucy server. This option allows you to reuse the existing certificate.

{% hint style="info" %}
Be advised that the validity period of the existing certificates will not be extended.
{% endhint %}
{% endtab %}
{% endtabs %}

### All Certificates

This tab provides an overview of all the certificates generated on your Lucy server. It offers the functionality to edit or permanently delete any certificate. This feature is especially valuable for renewing or replacing certificates associated with a specific domain across the entire Lucy server, including those used in attack and awareness campaigns.

<figure><img src="../../../../.gitbook/assets/image (194).png" alt="" width="375"><figcaption></figcaption></figure>

