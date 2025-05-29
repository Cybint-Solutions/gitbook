# Awareness Settings

The Awareness Settings tab lets you attach a default or pre-configured awareness template to your campaign.

***

### Add an Awareness Template to your campaign

Select "New Awareness"

<figure><img src="../../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

This displays the Awareness Template Gallery.

<figure><img src="../../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Use filters to find the correct awareness template. For guidance on navigating the Awareness Template Gallery,[ see our related article](../../../templates/awareness-templates.md).
{% endhint %}

Search for your desired Awareness Template, select "Use Template," and specify the default language.

<figure><img src="../../../../.gitbook/assets/image (531).png" alt="" width="282"><figcaption></figcaption></figure>

{% hint style="info" %}
You can dynamically preview templates. For further instructions, see our[ reference article](../../../templates/awareness-templates.md#dynamically-preview-an-awareness-template).
{% endhint %}

***

### Awareness Template Base Settings

The base settings of the awareness template provide an opportunity to define key parameters regarding the template's behavior.

<figure><img src="../../../../.gitbook/assets/image (532).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Name" %}
By default, the original template name will be populated, but you can change this name to apply only to the specific campaign associated with the awareness template.
{% endtab %}

{% tab title="Risk Level" %}
Based on the success rate of attack simulations for individual users, you can tailor the e-learning content in LUCY accordingly. For users who have not yet fallen for a phishing simulation, you might choose less advanced e-learning content compared to what you'd assign to someone who has repeatedly submitted sensitive data in previous phishing attempts.\
\
**Example:**

**Risk Level 0:** For users who have not succumbed to any of the phishing attempts.

**Risk Level 1:** For users who fell for one phishing simulation.

**Risk Level 2:** For users who succumbed to two or more phishing simulations.

By default, your awareness template is set to Risk Level = 0, assuming that the campaign does not have additional awareness training associated with it. This setting is used for basic introductory content suitable for all users at the start of their awareness training.
{% endtab %}

{% tab title="Website Enabled" %}
Select this option if you want the user to be directed to a landing page to complete their training. Typically, this setting should be enabled to gather statistical data on the user's training metrics. Only disable it if you intend for the user to receive an email without tracking their training progress.
{% endtab %}

{% tab title="Create Awareness Training Diploma" %}
This option is available only for awareness templates that include a Quiz/Exam. It is designed to automatically send users a predefined Training Diploma once they have successfully completed the training and achieved a score above the minimum passing threshold.

{% hint style="success" %}
See our reference article to define your [Training Diploma](../../../templates/training-diploma.md).
{% endhint %}
{% endtab %}

{% tab title="Languages" %}
This is the default language setting for your template. If a user is imported into Lucy without a specified language, they will receive the awareness scenario in the default language selected here.&#x20;

{% hint style="info" %}
Most templates are available in our core languages. If you need a translation in a language not already provided, select that language in this tab. You will then have the opportunity to manually translate the content in the subsequent steps of this article.
{% endhint %}
{% endtab %}
{% endtabs %}

Click "Save" to commit your changes.

***

### Website

The Website tab enables administrators to define all parameters related to the landing page of the awareness training content. This includes customization options such as layout, design elements, and interactive features.

<figure><img src="../../../../.gitbook/assets/image (530).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Domain / Subdomain" %}
Define the base domain to which the user will be redirected to access their awareness training content. You can also specify a subdomain, which is the portion of the URL before the base domain, such as **training**.lucysecurity.help

{% hint style="info" %}
**Hint:** Ensure that this domain is related to your company to create a sense of familiarity for the user. This is particularly important as users might be reluctant to click on links after being successfully phished.
{% endhint %}

{% hint style="warning" %}
If you are using a domain owned by your company, all [DNS records](../../../settings/common-system-settings/domains/#dns-records-explained) must be correctly configured to point to your Lucy server for successful mail delivery.
{% endhint %}
{% endtab %}

{% tab title="Quiz / Extended Tracking" %}
By default, if your campaign contains a Quiz or Exam, the "Quiz" selection box will be enabled. This means that once the user completes the first quiz, they will be marked as trained. Additionally, the system will provide the score and a list of answers submitted by the user which can be viewed in the [statistics section of the campaign results](../results/statistics.md#awareness-website).

The "Use extended method of tracking the end of the quiz" option tracks when users complete a pre-defined Quiz or Exam. For instance, in Advanced Awareness templates containing multiple quizzes and a final exam, enabling only "Quiz" logs the results of the first quiz the user interacts with and marks them as trained, disregarding any subsequent quizzes or exams. With this option enabled, you can specify which quiz or exam should determine the statistical outcome.

By default, this option is disabled.

To activate this feature, you need to add a call to the "lucyQuizEnd()" function without any parameters. Launch this function after the user answers the last question in your quiz. More information can be found in our [Guide: Use Extended Method of Tracking.](../../../../guides/awareness-training/use-extended-method-of-tracking-the-end-of-the-quiz.md)

{% hint style="warning" %}
If you enable this option without calling the "lucyQuizEnd()" function, recipients will not be marked as "trained".&#x20;
{% endhint %}
{% endtab %}

{% tab title="Preview Link" %}
The preview link offers a public URL for sharing with colleagues who do not have access to the Lucy administration panel. This feature is ideal for validating campaigns across different departments without running a campaign or adding stakeholders as administrative users on your Lucy server.
{% endtab %}
{% endtabs %}

<figure><img src="../../../../.gitbook/assets/image (541).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Language" %}
Each edit is confined to the selected language. If the default template does not include your target language, you can add and manually translate all text into the desired language. Remember to click 'Save' to commit the changes for each language.

{% hint style="warning" %}
Editing templates after binding them to a campaign commits the changes only to that specific campaign, not to the original template.

Editing a template within a campaign should be campaign-specific, indicating that the modifications are exclusive to that campaign and not intended for reuse in future campaigns. For more information, see our guide on [customizing Awareness templates](../../../../guides/awareness-training/awareness-template-customization.md).
{% endhint %}
{% endtab %}

{% tab title="Editor Type" %}
Lucy employs a standard open-source visual editor, known as a "What You See Is What You Get" (WYSIWYG) editor, as the default editing tool. For administrators who prefer editing in the source code directly, the "Code Mirror" editor is available as an alternative option.

{% hint style="info" %}
You can change your default editor in the [Advanced Settings](../../../settings/advanced-system-settings/advanced-settings.md#default-editor-type)
{% endhint %}
{% endtab %}

{% tab title="File" %}
This file directory contains all files related to your template, with index.html as the main file. Preview index.html to inspect the entire template.

Changes to quiz questions and logic are discussed in the [Awareness customization guide](../../../../guides/awareness-training/awareness-template-customization.md).
{% endtab %}

{% tab title="Content" %}
This is the main content editor for campaign-specific customizations.

{% hint style="info" %}
Editing a template within a campaign should be campaign-specific, indicating that the modifications are exclusive to that campaign and not intended for reuse in future campaigns. See our [Awareness template customization](../../../../guides/awareness-training/awareness-template-customization.md) guide for more info.
{% endhint %}
{% endtab %}
{% endtabs %}

***

### SSL Settings

Lucy features SSL automation that connects to GoDaddy via API to generate wildcard SSL certificates with 90-day validity in just seconds.

<details>

<summary>What is SSL?</summary>

SSL (Secure Sockets Layer) is like a protective shield. It ensures that when your targets interact with the awareness page, their data remains secure and can't be intercepted by prying eyes. It's the trusty guard that makes sure your training stays securely encrypted over the internet.\
\
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could seriously affect the authenticity of your training if it's not properly set up. So, think of SSL as your trusty sidekick, keeping things legitimate, secure and encrypted.

</details>

Select the checkbox to include an "**SSL Certificate**"

<figure><img src="../../../../.gitbook/assets/image (528).png" alt=""><figcaption></figcaption></figure>

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
See our platform reference article "[SSL Settings](../../../settings/common-system-settings/ssl-settings/)" for more information.
{% endhint %}

***

### Certificate

The certificate tab pertains to the recipient's completion training diploma certificate, issued when the user successfully achieves a score above the pre-configured pass threshold on the quiz.

{% hint style="info" %}
Ensure "**Create Awareness Training Diploma**" is enabled on the template **Base Settings**.

![](<../../../../.gitbook/assets/image (524).png>)
{% endhint %}

{% hint style="warning" %}
Editing the certificate diploma in a campaign commits changes only to that campaign, similar to editing attack/awareness templates. To edit certificates on a global level, please refer to our platform reference article on [Awareness Training Diploma](../../../templates/training-diploma.md).
{% endhint %}

Choose one of the ready-made Training Diplomas.

<figure><img src="../../../../.gitbook/assets/image (525).png" alt=""><figcaption></figcaption></figure>

Provide a suitable title to be displayed as the subject in the email when users receive their Training Diploma attachment.

<figure><img src="../../../../.gitbook/assets/image (526).png" alt=""><figcaption></figcaption></figure>

Use the "**Message**" section to make modifications to the content of your Training Diploma Certificate.

<figure><img src="../../../../.gitbook/assets/image (527).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Certificate Variable Placeholders</summary>

In the certificate template, you can use the following variables:

* `%name%` — name of the certificate recipient.
* `%awareness%` — name of the awareness training.
* `%gender("MALE ADDRESSING", "FEMALE ADDRESSING", "NO GENDER")%` — recipient's gender.
* `%score%` — recipient's score.
* `%date%` — date of the certificate.
* `%time%` — time of the certificate issuance.

Please note that these variables are not available in CSS and JavaScript files.

</details>

***

### Message

The email (Message) template is triggered if the "**Send link to Awareness website automatically via Email**" setting is enabled in your attack scenario.

This is your opportunity to customize the default email template to match your organization's branding, font, and voice.

**Setting Up the Email**

Choose the language from the "Language" dropdown, e.g., English.

{% hint style="warning" %}
Languages are not automatically translated; all adaptations must be applied to each selected language.
{% endhint %}

**Email Details**

* Fill in the "Subject" field, e.g., "Advanced course on security in the cloud".
* Enter "Sender Name", e.g., "IT Security".
* Provide "Sender Email", e.g., "security@your-company.com".

{% hint style="info" %}
It's advisable to use a [sender domain ](../../../settings/common-system-settings/domains/#dns-records-explained)related to your company to create a sense of familiarity, especially since the user was just successfully phished.
{% endhint %}

**Content Editor**

Choose "Editor Type" from the dropdown to select your preferred email editor.

{% tabs %}
{% tab title="Visual Editor" %}
The Visual Editor is a WYSIWYG interface, offering an easy way for users to create content as it will appear in its final form. With a straightforward toolbar, users can format text and add multimedia without coding knowledge.
{% endtab %}

{% tab title="Code Mirror" %}
The Code Mirror Editor is geared towards users with coding expertise. It provides a code-highlighting text editor for direct HTML and CSS manipulation, offering granular control over the content's appearance and structure.
{% endtab %}
{% endtabs %}

**Composing the Email**

Use the "Content" section for email composition.

#### Format text with the toolbar options (bold, italic, underline, etc.).

<figure><img src="../../../../.gitbook/assets/chrome_waltwZLXge.gif" alt=""><figcaption></figcaption></figure>

#### Insert dynamic variables into the content.

<figure><img src="../../../../.gitbook/assets/chrome_eqG0Q7TCD1.gif" alt=""><figcaption></figcaption></figure>

<details>

<summary>Dynamic Variables Explained</summary>

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

#### assetsClick "Upload File or Image" to add company branding or assets.

<figure><img src="../../../../.gitbook/assets/chrome_eiYtGWmOUv.gif" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Attachments" %}
Add your own attachments. Keep in mind that most common email clients filter certain types of attachments, like executables, to prevent malware risks.
{% endtab %}

{% tab title="General Email Settings" %}
Set custom SMTP headers to meet specific needs. For example, you can add a custom email header to help your SPAM gateway distinguish between actual SPAM and emails sent from LUCY.
{% endtab %}

{% tab title="Advanced Email Settings" %}
* Send emails as plain text.
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

***

### Mail Settings

Administrators have two choices for setting up mail delivery: globally or at the campaign level. Global settings affect all campaigns but can be overridden by campaign-specific settings, which only apply to the selected campaign. This flexibility allows for customized mail delivery preferences on a per-campaign basis:

{% tabs %}
{% tab title="Use System Settings" %}
Navigate to -> [Settings -> Common System Settings -> Mail Settings](awareness-settings.md#mail-settings)\
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

### Awareness Groups

This feature is designed to automate the provisioning of multiple awareness templates based on three pre-defined goals.

1. Group recipients into Awareness Groups and serve them training content related to their day-to-day activities
2. Automate the sending of awareness content based on the recipient's **risk level**
3. Use the Scheduler to create specific rules for different scenarios to manage selected Awareness Groups.

{% hint style="warning" %}
Awareness Groups are active only in campaigns with awareness scenarios, excluding phishing scenarios.
{% endhint %}

