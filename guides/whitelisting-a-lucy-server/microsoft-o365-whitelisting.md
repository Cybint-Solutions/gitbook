# Microsoft O365 Whitelisting

To create, modify, or remove settings in an advanced delivery policy, you need to be a member of the specific role groups. Microsoft's new "secure by default" feature may affect your current whitelisting rules. Use Advanced Delivery Policies to whitelist emails for phishing simulations.

***

### **Avoid Spam Issues Related to Office 365**

**How are Phishing Simulation Emails Whitelisted in O365?**

Microsoft has a centralized configuration for phishing campaigns in Exchange Online Protection Policies. The Advanced Delivery section allows configuring Phishing Simulations with specific domain names and senders. Since mid-2021, changes to mail flow and filtering mean exceptions in mail flow rules are optional, and security defaults are enforced, blocking 'High Confidence Phish' emails from passing through Exchange Online Rules.

For more details, refer to the following resources:

* [Mastering Configuration in Defender for Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/mastering-configuration-in-defender-for-office-365-part-two/ba-p/2307134)
* [Configure Advanced Delivery](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/configure-advanced-delivery?view=o365-worldwide)

***

Navigate to the configuration via the [Microsoft 365 Defender portal](https://security.microsoft.com) ->[ security.microsoft.com](https://security.microsoft.com)

**Adding Sending Domain and Sending IP to Whitelist**

* Open the Microsoft 365 Defender Portal
* Navigate to "Email & Collaboration":
* Go to Policies & Rules -> Threat policies.

<figure><img src="../../.gitbook/assets/image (672).png" alt=""><figcaption></figcaption></figure>

* Select Advanced Delivery.

<figure><img src="../../.gitbook/assets/image (673).png" alt=""><figcaption></figcaption></figure>

***

**Configure Phishing Simulation:**

* On the Advanced delivery page, go to the Phishing Simulation tab. Click the Edit icon or, if no phishing simulations are configured, click Add.

<figure><img src="../../.gitbook/assets/image (675).png" alt=""><figcaption></figcaption></figure>

**Edit Phishing Simulation Settings:**

In the Edit third-party phishing simulation modal, adjust the following settings:

* **Sending Domain:** Enter at least one sending domain used as the sender email in Lucy.

<figure><img src="../../.gitbook/assets/image (676).png" alt="" width="563"><figcaption></figcaption></figure>

* **Sending IP:** Enter the sending IP address of your Lucy instance.

<figure><img src="../../.gitbook/assets/image (677).png" alt="" width="563"><figcaption></figcaption></figure>

* **Specific URLs (optional):** Enter specific URLs that are part of your phishing simulation campaign using the recommended URL syntax format: `example.com/*`

<figure><img src="../../.gitbook/assets/image (678).png" alt="" width="560"><figcaption></figcaption></figure>

**Save Changes:**

* Click Add for all options and Save

**Propagation Time:**

* Wait at least 30 minutes for changes to propagate before starting any phishing campaigns.
