# Managing Google SafeBrowsing Alerts

If your domain is blacklisted by Google, it will display a "Deceptive site ahead" warning, adversely affecting your phishing simulation campaigns.

<figure><img src="../../.gitbook/assets/image (666).png" alt="" width="563"><figcaption></figcaption></figure>

<details>

<summary>Why did Google SafeBrowsing blacklist my domain?</summary>

1. **Spoofed Brands:**
   * Domains mimicking well-known brands (e.g., Google, Facebook, Microsoft) can be flagged. Google’s algorithms detect visual and structural similarities to known brands to prevent phishing.
2. **Phishing Indicators:**
   * If the domain hosts landing pages that solicit login credentials, personal information, or payment details, it can be flagged as a phishing site. Google analyzes the content for common phishing tactics and deceptive practices.
3. **New or Untrusted Domains:**
   * Newly registered domains often lack a reputation. If these domains are used for phishing simulations, they are more likely to be blacklisted. Google evaluates the age and trustworthiness of a domain.
4. **Domain Configuration:**
   * The setup of SPF, MX, and A records pointing to the Lucy server is scrutinized. Misconfigurations or anomalies in these records can trigger blacklisting. Google checks for alignment with typical usage patterns and legitimate email configurations.
5. **SSL Certificates:**
   * Even with valid SSL certificates, if the domain shows signs of misuse or if the certificates are not from well-known Certificate Authorities, the domain can be flagged. Google inspects the validity and trustworthiness of the SSL certificates.
6. **Malware Distribution:**
   * If the domain inadvertently hosts or distributes malware (e.g., through attachments or linked downloads), it will be blacklisted. Google scans for malicious software and scripts.
7. **Deceptive Content:**
   * Google looks for content that is intentionally deceptive or misleading, designed to trick users into performing unsafe actions. This includes fake warnings, alerts, and instructions.
8. **Suspicious Behavior Patterns:**
   * High volumes of emails sent from the domain, especially those resembling phishing emails, can raise red flags. Google monitors sending patterns and email content for suspicious activities.
9. **User Reports:**
   * If users report the domain as suspicious or harmful, Google will take these reports into consideration. High numbers of user complaints can lead to a domain being blacklisted.
10. **Embedded Links and Redirects:**
    * Google checks for suspicious links and redirects within the domain. If the site redirects to known malicious or phishing sites, it can be flagged.

</details>

<details>

<summary>What can I do to prevent Blacklisting?</summary>

### **Choose Reputable Domain Providers:**

* Register your domains with well-known and reputable domain providers. This helps establish initial trust. You can use the built-in [Domain wizard](../../application-screens-reference/settings/common-system-settings/domains/#register) for registration with GoDaddy.

### **Set Up Proper DNS Records:**

* Ensure your SPF, DKIM, and DMARC records are correctly configured to authenticate your emails.
*   [Example SPF record:](../../application-screens-reference/settings/common-system-settings/domains/#dns-records-explained)

    ```plaintext
    v=spf1 ip4:{your_lucy_ip_address} ~all
    ```
*   [Example DKIM record:](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#dkim-support)

    ```plaintext
    default._domainkey IN TXT "v=DKIM1; k=rsa; p=<public_key>"
    ```
*   Example DMARC record:

    ```plaintext
    _dmarc IN TXT "v=DMARC1; p=none; rua=mailto:dmarc-reports@yourdomain.com"
    ```

See our platform reference article on [DNS records](../../application-screens-reference/settings/common-system-settings/domains/#add-a-domain)

### **Implement HTTPS:**

* Use SSL/TLS certificates from reputable Certificate Authorities (CAs) to secure your domains. Use the built-in [Let's Encrypt certificate generator](../../application-screens-reference/settings/common-system-settings/ssl-settings/) for your domains.

### **Regularly Update Your DNS Records:**

* Keep your DNS records up-to-date and ensure there are no misconfigurations.

### **Content and Email Practices:**

**Avoid Exact Brand Imitation:**

* Do not exactly replicate the appearance of Google, Facebook, or Microsoft emails and pages. Add slight variations to avoid detection by algorithms.

**Use Clear Disclaimers:**

* Include disclaimers in your emails and landing pages stating that they are part of a security awareness program.

**Limit Email Volume:**

* Send your phishing simulation emails in small batches to avoid triggering spam filters. Use the built-in [Scheduler](../../application-screens-reference/campaigns/campaign-settings/configuration/schedule/) to achieve this.

**Monitor Email Content:**

* Ensure your emails do not contain elements commonly associated with spam or phishing, such as excessive links or suspicious attachments.

**Test Content with Spam Checkers:**

* Use tools like Mail-Tester or Litmus to test your emails for spammy elements before sending them out.

### **Domain Management and Monitoring:**

**Warm-Up Your Domain:**

* Gradually increase your email sending volume to establish a good sending reputation. Use the built-in [Scheduler](../../application-screens-reference/campaigns/campaign-settings/configuration/schedule/) to achieve this.

**Monitor Domain Health:**

* Use tools like [Google Search Console ](https://search.google.com/search-console/about)to monitor your domain’s health and address any issues promptly.

**Engage in Regular Clean-Up:**

* Periodically review and clean your email lists to ensure you are sending to valid addresses. Use [Lucy's built-in automation](../../application-screens-reference/settings/common-system-settings/ldap-settings.md#action-for-new-users) to automatically keep your users up to date with your organization's directory.&#x20;

**Utilize Subdomains:**

* Consider using subdomains specifically for simulations to isolate potential issues from your main domain.

### **Google Safe Browsing and User Reports:**

**Regularly Check for Blacklisting:**

* Periodically check your domains using tools like Google Safe Browsing to ensure they are not blacklisted.

**Promptly Address User Reports:**

* Respond quickly to any user reports of suspicious activity related to your domains.

**Verify and Whitelist Your Domain:**

* Verify your domain ownership with Google Search Console and request reviews if blacklisting occurs.

### **Legal and Ethical Considerations:**

**Stay Within Legal Boundaries:**

* Ensure your simulations comply with local laws and regulations regarding email communications and data privacy.

**Communicate with Stakeholders:**

* Inform relevant stakeholders within your organization about the phishing simulations to avoid misunderstandings and false reports to Google.

</details>

***

### **Domain Verification and Ownership Proof**

**Verify Domain Ownership:**

* Go to [Google Search Console Security Issues](https://www.google.com/webmasters/tools/security-issues) and click "Add property now".

<figure><img src="../../.gitbook/assets/image (667).png" alt="" width="361"><figcaption></figcaption></figure>

* Enter the URL of the property you want to verify and click "Continue".

<figure><img src="../../.gitbook/assets/image (668).png" alt="" width="563"><figcaption></figcaption></figure>

**Domain Name Provider Verification:**

* Choose your domain provider from the dropdown menu or select "Any DNS provider" for the TXT record method.

<figure><img src="../../.gitbook/assets/image (669).png" alt="" width="563"><figcaption></figcaption></figure>

* Sign in to your domain name provider and add a TXT record as instructed.

> In this example, we will add the Google provided TXT record to my domains DNS panel in GoDaddy. This procedure should be similar for all Domain registration panels.

<figure><img src="../../.gitbook/assets/image (670).png" alt=""><figcaption></figcaption></figure>

* Go back to Google Search Console and click Verify

<figure><img src="../../.gitbook/assets/image (671).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
Sometimes DNS changes can take a while to appear. Please wait a few hours, then reopen your property in Search Console. If verification fails again, try adding a different DNS TXT record.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (773).png" alt="" width="563"><figcaption></figcaption></figure>

***

### What is next?

After verifying domain ownership, Google may take 48 to 72 hours to whitelist it. Updates and notifications will be sent to the registered email in Google Search Console.
