# Attack Simulation

### Add an Attack Template

Select **+ New Scenario** to view the template gallery.

<figure><img src="../../../../.gitbook/assets/image (1026).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

Search for an Attack template, select **Use Template**, and specify the default language.

<figure><img src="../../../../.gitbook/assets/image (544).png" alt="" width="312"><figcaption></figcaption></figure>

{% hint style="info" %}
You can dynamically preview templates. For further instructions, see our [reference article](../../../templates/attack-templates.md#filtering).
{% endhint %}

***

### Base Settings

The base settings of the attack template provide an opportunity to define key parameters regarding the template's behavior.

<figure><img src="../../../../.gitbook/assets/image (1028).png" alt=""><figcaption></figcaption></figure>

#### Template

You can change the attack template at any time by clicking the edit button on the right.

#### Name

Give the attack simulation a name. This will show up in the campaign report.

#### Domain

Configure a domain (and an optional subdomain) for the attack simulation.

{% hint style="danger" %}
Avoid using your System Domain for phishing simulations to prevent potential blacklisting issues. - See our reference article on [Domains](../../../settings/common-system-settings/domains/) for more information.
{% endhint %}

{% tabs %}
{% tab title="URL Shortener" %}
You can select a URL-shortening service from the dropdown menu. This feature is available only for domain names, not IPs.

{% hint style="warning" %}
URL-shortening services may scan the links, leading to inaccurate statistics.\
To avoid this, use the [system filter](../../../settings/common-system-settings/filter-settings.md) settings to ignore the IP.
{% endhint %}
{% endtab %}

{% tab title="Advanced Tracking" %}
The statistic for recipients opening the email is based on a tracking image embedded within the email. However, many email clients block the automatic download of images, which can make this number less accurate.

{% hint style="info" %}
Please refer to our Guide on [Email Tracking Technologies](../../../../guides/attack-simulations/email-tracking-technologies.md) for more information.
{% endhint %}
{% endtab %}

{% tab title="Advanced Information Gathering" %}
Lucy provides a suite of features designed to enhance your understanding of user behavior and system security when interacting with simulated phishing tests. Each option delves into different aspects of the recipient's environment, from browser configurations to network connections, offering valuable insights for cybersecurity awareness and training.

{% hint style="info" %}
Please refer to our detailed Guide on [Advanced Information Gathering](../../../../guides/attack-simulations/advanced-information-gathering.md) for more information.
{% endhint %}

1. **Browser Details:** This tracks specific details about the browser the recipient is using, such as the browser type, version, and any associated browser extensions. Understanding the browser details can help identify potential security weaknesses or confirm if the browser is up-to-date and configured with security best practices.
2. **Firebug Information:** Firebug is a popular web development tool. If a user has Firebug installed, it could potentially be used to debug or modify webpages. Tracking whether Firebug or similar tools are present can reveal if there's an increased risk of web-based threats or attacks.
3. **Popup Blocker:** This checks if the user’s browser is configured to block popup windows. Popups are often used in phishing attacks to deliver malicious content, so knowing whether popup blockers are active can be indicative of the user's level of vulnerability.
4. **Geo Location:** By determining the geographic location of the user, the organization can assess if there are access patterns from unusual locations that could indicate compromised credentials or other security issues.
5. **Social Network:** This feature checks for active connections to social networks from the user’s browser. Given that social networks can be platforms for phishing and malware distribution, awareness of such activity can be crucial for understanding the social media risk landscape.
6. **Proxy:** Identifying whether the user is connected to the internet via a proxy can be important for security. Proxy usage can obscure the true IP address, which could either be a legitimate privacy measure or a method to hide malicious activity.
{% endtab %}

{% tab title="Training Settings" %}
**Send link to Awareness Website Automatically via Email:**

This feature dispatches a link to the Awareness Website to a user immediately after they've fallen for a simulated attack. For this functionality to operate correctly, the Awareness Website must be active and published.&#x20;

**Send Awareness By Click Rate**

This feature allows you to set a threshold for historical click rate that triggers the sending of an awareness email. For instance, setting it at 50% means a user will receive an awareness email only if they have clicked on at least half of the links presented in previous phishing simulations.

**Send Awareness By Success Rate**

Similarly, the success rate determines the rollout of awareness training but is based on different successful interactions, not just link clicks, to initiate the e-learning process.

**Awareness Delay**

Within LUCY, you have the option to set a delay for sending the automated awareness email. This delay ensures that individuals within the same office aren't notified simultaneously about the occurrence of a phishing simulation, which can prevent immediate cross-talk and maintain the integrity of the test environment.

{% hint style="info" %}
Alternatively, users can be automatically [redirected to the Awareness training through their browser](../../../../guides/attack-simulations/redirecting-users.md) immediately after engaging with the simulated attack.
{% endhint %}
{% endtab %}

{% tab title="Success Action" %}
This setting in LUCY determines what is considered a successful attack and subsequently triggers the start of eLearning.&#x20;

There are four options available for defining success actions. Each option specifies the condition under which eLearning is initiated. For instance, if you select "data submit" as the success action, eLearning will only begin once the user enters data and submits it on a landing page.&#x20;

{% hint style="warning" %}
It’s important to note that if you use "data submit" as the success action on a file-based template that doesn’t include a login mechanism, the eLearning will never be initiated for the user.
{% endhint %}

**Click:** triggered when the user clicks on the link in the email.

**Data Submit:** triggered when the user enters data and submits it on a landing page of the attack.

**File Download:** triggered when the user clicks on the file download button on the landing page.

**File Data Received:** triggered when the user executes the file and Lucy received the dummy data.
{% endtab %}

{% tab title="Collect Data" %}
Collected data encompasses information gathered from web-based phishing simulations, including credentials entered on a fake login page or data transmitted to LUCY from simulated document macros activated by users.

{% hint style="info" %}
Refer to our platform reference article on [viewing collected data](../results/statistics.md#collected-data).
{% endhint %}

{% hint style="warning" %}
Lucy collects only "Partial" or "No" data to comply with data regulations, revealing the first three characters of usernames and passwords.
{% endhint %}
{% endtab %}

{% tab title="Double Barrel Attack" %}
When employing the Double Barrel Attack, the system initially dispatches a "Lure" email with teaser text. Subsequently, the system pauses for a specified duration before sending the actual phishing email. This advanced strategy involves the "Lure" potentially impersonating a known authority figure within your organization, who then endorses the follow-up attack simulation as bait.

The delay for the "Lure" defines, in seconds, the interval between the "Lure" and attack emails for a Double-Barrel Attack.

{% hint style="info" %}
Refer to our Guide on [Lure Attacks](../../../../guides/attack-simulations/attack-types/lures.md) for more information.
{% endhint %}
{% endtab %}

{% tab title="RegExp" %}
Another option involves defining login filters to exclusively capture valid logins. For instance, you could specify the domain name in the User Name field or stipulate that passwords must be at least 8 characters long to be accepted by LUCY.

If you wish to validate logins and passwords using regular expressions (via the "Login Regexp" and "Password Regexp" fields in Scenario Settings), please ensure that the login field is named "Login" and the password field is named "Password".

{% hint style="info" %}
Refer to our Guide on [Regular Expressions in Login Fields](../../../../guides/attack-simulations/regular-expressions-in-login-fields.md).
{% endhint %}
{% endtab %}
{% endtabs %}

***

### Mail Settings

Administrators have two choices for setting up mail delivery: globally or at the campaign level. Global settings affect all campaigns but can be overridden by campaign-specific settings, which only apply to the selected campaign. This flexibility allows for customized mail delivery preferences on a per-campaign basis:

{% tabs %}
{% tab title="Use System Settings" %}
Navigate to -> [Settings -> Common System Settings -> Mail Settings](attack-simulation.md#mail-settings)\
\
Here you can choose your default method for sending emails. This setting will apply to all campaigns.
{% endtab %}

{% tab title="Internal Postfix Server" %}
Lucy incorporates a built-in internal mail server (Postfix) as its default method for email delivery. This approach is straightforward and often used due to its direct integration within Lucy. To enhance delivery success, it's advisable to align the server's name with Lucy's Fully Qualified Domain Name (FQDN), potentially using a subdomain designated for mail purposes.
{% endtab %}

{% tab title="External SMTP Server" %}
Lucy allows the configuration of an external SMTP server via its general settings. This is particularly useful when aiming to circumvent spam filters that may block emails from new or untrusted IP addresses. Setting up involves adding your mail server details under "[Settings -> Common System Settings -> SMTP Servers](../../../settings/common-system-settings/smtp-servers.md)"; followed by a connection test to ensure proper setup.
{% endtab %}
{% endtabs %}

***

### SSL Settings

Select the checkbox to include an SSL Certificate:

<figure><img src="../../../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Select Existing" %}
Choose this option if you have already generated an SSL certificate on your Lucy server. This option allows you to reuse the existing certificate.

{% hint style="info" %}
Be advised that the validity period of the existing certificates will not be extended.
{% endhint %}
{% endtab %}

{% tab title="Generate or Upload" %}
This option is ideal if you already have an SSL certificate chain from a trusted certificate authority or if you would like to generate a self-signed certificate.&#x20;

{% hint style="warning" %}
Be aware that self-signed certificates are not issued by trusted certificate authorities. As a result, browsers will mark your domain as not secure when using these certificates.
{% endhint %}

**Option 1: Generate a self-signed Certificate**

<figure><img src="../../../../.gitbook/assets/image (274).png" alt="" width="301"><figcaption></figcaption></figure>

1. **Domain**: Enter the domain name for which you want to generate the SSL certificate (e.g., thrivedx.help).
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

{% tab title="Let's Encrypt" %}
Our default method, designed for maximum user-friendliness, enables your Lucy server to automatically generate a Certificate Signing Request (CSR) through the integrated Let's Encrypt API. It then submits this request to Let's Encrypt and automatically installs the full certificate chain on your Lucy server.&#x20;

This process may take up to 5 minutes to complete. Please wait for the "certificate successfully generated" notification before proceeding further.

{% hint style="info" %}
Let's Encrypt certificates are issued with a maximum validity period of 90 days.
{% endhint %}

{% hint style="danger" %}
Please be aware that Let's Encrypt, a third-party SSL provider, imposes certain limitations. One notable restriction is the issuance cap of no more than 5 certificates per week for the same domain name. For additional details on these limitations, you can visit: [Let's Encrypt Rate Limits](https://letsencrypt.org/docs/rate-limits/).
{% endhint %}
{% endtab %}
{% endtabs %}

{% hint style="success" %}
See our platform reference article [SSL Settings](../../../settings/common-system-settings/ssl-settings/) for more information.
{% endhint %}

***

### Bound Awareness Scenarios

Lucy enhances the effectiveness of educational campaigns by allowing for a targeted approach, focusing on individual user performance across different simulated attack scenarios. This personalized method not only makes the training more relevant but also more engaging for users.

**Scenario-Based Training Customization:**

* **Specific Attack Recognition:** Consider a campaign that includes various types of phishing attacks such as data entry, hyperlink, and file download attacks. Lucy allows you to monitor how each user responds to these different scenarios.
* **Customized Learning Experiences:** If a user fails in one scenario but performs well in others, Lucy enables you to tailor the training specifically to their needs. For example, a user who mistakenly downloads malware thinking it is a legitimate document does not necessarily need a broad phishing course. Instead, they can benefit from a focused session on identifying and avoiding file-based threats.
* **Efficient and Effective Training:** By providing training specific to the user's vulnerabilities, Lucy ensures that the learning is both efficient and directly applicable. This targeted education approach helps in reinforcing the correct practices without overloading the user with unnecessary information.

**Configuration**

Bound Awareness Scenarios can only be configured directly on the **Awareness Scenario**. In your current campaign, navigate to **Configuration -> Awareness Settings -> Select your Awareness Scenario**, then navigate to the tab "**Bound Attack Scenarios**":

<figure><img src="../../../../.gitbook/assets/image (552).png" alt=""><figcaption></figcaption></figure>

Here, you can specifically link each awareness scenario with the corresponding attack simulation that aligns with the training material.

This capability allows you to provide targeted and efficient awareness training that addresses users' specific needs based on their performance in different attack scenarios.

***

### Landing Page Template

The "Landing Page Template" tab in Lucy is a powerful tool for creating and managing phishing simulation landing pages.

See our guide for attack template customization [here](../../../../guides/attack-simulations/attack-template-customization.md).

Lucy's attackt emplates will always include two files, **index.html** and **account.html:**

<figure><img src="../../../../.gitbook/assets/image (520).png" alt="" width="326"><figcaption></figcaption></figure>

{% hint style="info" %}
Lucy adheres to a strict naming convention for these files. If you create a custom template, make sure to name the files **`index.html`** and **`account.html`.**
{% endhint %}

**Index.html**

* **Purpose:** Serves as the initial landing page for the simulated attack. When users click a link in the attack email, they are directed to this page.
* **Function:** Mainly used for credential harvesting, this page typically prompts users to enter login details or other personal information.

**Account.html**

* **Post-Attack Redirection:** After data is submitted on index.html, users are redirected to account.html.
* **Function:** This page facilitates the conclusion of the attack. It may:
  * Automatically redirect users to the associated awareness training in the campaign.
  * Display a fake notification, such as "Your VPN was successfully authenticated."
  * Show a blank page that redirects immediately to awareness training with no delay, following the data exploitation on index.html.

{% hint style="danger" %}
The first page the user accesses should be named **`index.html`**.
{% endhint %}

#### **Preview the landing page**

Select the **Preview** button to view how the landing page looks in real-time, allowing for adjustments before deployment.

<figure><img src="../../../../.gitbook/assets/image (516).png" alt="" width="563"><figcaption></figcaption></figure>

***

### Message Template

**Setting Up the Email**

{% hint style="warning" %}
Settings are not automatically shared across Languages; all adaptations must be applied to each selected language. Translated content must be applied separately.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (517).png" alt="" width="563"><figcaption></figcaption></figure>

#### Subject

The subject line of the email.

#### Sender Name

The name of the sender. This can be anything you want.

#### Sender Email

The email address of the sender. This does **not** need to be an existing email address, but the domain **does** need to point to your Lucy server. For best results, use the same domain as your awareness website.

{% hint style="info" %}
It's advisable to use a sender domain that is associated with the registered domain of the attack since this domain's DNS records (SPF, MX) are automatically configured to point to your Lucy server. This alignment helps ensure that the emails appear more legitimate and reduces the risk of them being flagged as spam.
{% endhint %}

#### **Content**

Choose "Editor Type" from the dropdown to select your preferred email editor.

{% tabs %}
{% tab title="Visual Editor" %}
The Visual Editor is a WYSIWYG interface, offering an easy way for users to create content as it will appear in its final form. With a straightforward toolbar, users can format text and add multimedia without coding knowledge.
{% endtab %}

{% tab title="Code Mirror" %}
The Code Mirror Editor is geared towards users with coding expertise. It provides a code-highlighting text editor for direct HTML and CSS manipulation, offering granular control over the content's appearance and structure.
{% endtab %}
{% endtabs %}

<details>

<summary>Email Variables</summary>

When creating email templates, you can personalize the content by using various placeholders that will be automatically replaced with specific user data when the email is sent. Below is an explanation of each variable available for use in the templates:

* `%link%`: This variable represents the base URL of your site. Use it to construct absolute URLs for navigation within your emails.
* `%user-password-reset%`: This placeholder is replaced with the unique URL for a password reset action.
* `%user-profile-link%`: Inserts a direct link to the user's profile page in the End User Portal.
* `%user-login-url%`: Provides a link to the End User Portal that utilizes SSO (OAuth 2.0) for login.
* `%name%`: The full name of the email recipient.
* `%firstname%`: The recipient's first name.
* `%lastname%`: The recipient's last name.
* `%email%`: The recipient's email address.
* `%client%`: The name of the client associated with the recipient.
* `%gender("MALE ADDRESSING", "FEMALE ADDRESSING", "NO GENDER")%`: This is a conditional variable that changes the greeting or addressing based on the recipient's gender.
* `%subject%`: The subject line of the phishing email.
* `%sender%`: The name of the sender of the phishing email.
* `%sender-email%`: The email address from which the phishing email is sent.
* `%started%`: The date when the related phishing campaign was started.
* `%stopped%`: The date when the related phishing campaign was stopped.
* `%time(FORMAT, OFFSET, ZONE)%`: A dynamic time variable where:
  * `FORMAT` refers to the format in which the date/time should be displayed.
  * `OFFSET` is the time offset from the mail send time, which can be positive or negative.
  * `ZONE` is the time zone to be applied.
  * Example: `%time("l, H:i", "0", "Europe/Zurich")%` would display the time of the email submission in the Europe/Zurich time zone.
  * Example: `%time("Y/m/d H:i:s", "60")%` would show a timestamp one hour ahead of the email submission time.

Note that these variables are intended for use in the HTML body of the email and are not applicable within CSS and Javascript files. They serve to customize the email content for each recipient and should be used accordingly to ensure a personalized user experience.

</details>

{% tabs %}
{% tab title="Attachments" %}
Add your own attachments. Keep in mind that most common email clients filter certain types of attachments, like executables, to prevent malware risks.
{% endtab %}

{% tab title="General Email Settings" %}
Set custom SMTP headers to meet specific needs. For example, you can add a custom email header to help your SPAM gateway distinguish between actual SPAM and emails sent from LUCY.
{% endtab %}

{% tab title="Advanced Email Settings" %}
* **Send emails as plain text.**
*   **Random Email**:

    LUCY will generate a random email account with a random sender. The email account will be deleted after the campaign ends.

If you want to catch email replies from your awareness email, LUCY provides two options:

1. **Define a Reply-to Header**:
   * The Reply-to address is where email replies are directed, rather than the 'From' address. This is useful if the 'From' address cannot receive replies, for example, if you do not control the domain or lack a mail server setup for it. For instance, if the email shows as being sent from "mitchel@guysfromrolla.com" and the recipient clicks reply, the email will be directed to the Reply-to address set in the header, such as "[billg@microsoft.com](mailto:billg@microsoft.com)". Choose a Reply-to address you have access to.
2. **Define a Forward Mail**:
   * LUCY can forward incoming replies to a specified email address. This requires setting a [DNS entry (MX record)](../../../settings/common-system-settings/domains/#dns-records-explained) for the sender’s domain that points to LUCY. For example, if you send emails from "attacker@phishing-test.com" and LUCY's IP is 201.35.77.12, you need an MX record like "phishing-test.com MX 10 201.35.77.12". Enter your own custom mail address in the forward mail field (e.g., "user@example.com"). When someone replies to "attacker@phishing-test.com", LUCY receives the email and forwards it to "user@example.com". Note that many registration services offer free mail/DNS packages, allowing you to set up an email forwarder directly at the domain level, eliminating the need for LUCY’s forwarding feature.
{% endtab %}

{% tab title="DKIM Support" %}
**DKIM Overview:**&#x20;

DomainKeys Identified Mail (DKIM) enhances email security by attaching a domain name identifier to a message, utilizing cryptographic techniques to validate authorization. This identifier is separate from other message identifiers such as the author's "From" field. DKIM effectively 'signs' emails to verify their origin, helping to identify and prevent spoofed emails. The process involves the sending mail server signing the email with a private key, while the receiving server uses a public key listed in the domain's DNS to verify the signature. Each domain can list multiple DKIM keys in its DNS, but each private key is unique to one mail server.

**Setting Up DKIM in LUCY:**

1. **Enable DKIM:**
   * Navigate to "Advanced Email Settings" in the message template of your Attack Scenario. Enable DKIM support and save the changes. A DKIM information box will then appear.
2. **DNS Configuration:**
   * Copy the provided key and create the corresponding DNS entry. Here’s an example of how to set it up with namecheap.com:

```
Name: selector._domainkey
Type: TXT
Value: "v=DKIM1; k=rsa; p=[YOUR_PUBLIC_KEY]"
```

**Validate DKIM Setup:**

* To confirm your DKIM is working, add an email from a service like [dkimvalidator.com](https://dkimvalidator.com/) to your DKIM test recipient group. Launch the campaign targeting this group, then check the results at dkimvalidator.com. If configured correctly, your setup should match the expected status.

**DKIM Header Details:** The DKIM signature is added to emails as an RFC2822 header field. Here's a breakdown of the common fields in a DKIM signature:

* **b:** Digital signature of the email's contents.
* **bh:** Hash of the email body.
* **d:** Signing domain.
* **s:** Selector used for the DKIM signature.
* **a:** Signing algorithm, typically rsa-sha1.
* **c:** Canonicalization algorithm for the header and body.
* **q:** Default query method, usually DNS.
* **t:** Timestamp of when the email was signed.
* **x:** Expiry time of the signature.
* **h:** List of header fields that were signed.

This setup ensures that emails sent through LUCY's mail server are authenticated, boosting trust and security for your email campaigns.
{% endtab %}
{% endtabs %}
