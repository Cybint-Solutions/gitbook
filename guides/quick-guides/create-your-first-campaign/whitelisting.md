# Whitelisting

<details>

<summary>What is Whitelisting?</summary>

Whitelisting involves allowing certain IP addresses to bypass an organization's defense systems, ensuring successful phishing simulations and awareness training. This requires adding the Lucy server IP and sender domain(s) to trusted sources in email gateways, anti-virus software, and web proxies, preventing simulated phishing emails from being blocked or marked as spam.

</details>

> The main objective of a Security Awareness program is to evaluate the recipients' awareness, not the strength of your network defenses. Ensure your defensive systems allow traffic from your Lucy server so it isn't blocked.

{% hint style="info" %}
Below are quick guides for **Microsoft 365 (O365)** and **Google Workspace**. For more detailed information, refer to our[ advanced whitelisting guides.](../../whitelisting-a-lucy-server/)
{% endhint %}

**Google Workspace:**

1. Log in to `admin.google.com` and navigate to "Apps" -> "Google Workspace" -> "Gmail".
2. Under "Spam, phishing, and malware", add the Lucy IPv4 to "Email Allowlist" and save.
3.  In the same menu, go to "Inbound Gateway". Add Lucy IPv4, activate Message Tagging, add a symbol set to the Regular Expression field, select "Disable Gmail spam evaluation on mail from this gateway", and save.

    <figure><img src="../../../.gitbook/assets/image (230).png" alt="" width="360"><figcaption></figcaption></figure>

**Microsoft 365 (O365):**

1. Open the Microsoft 365 Defender portal -> `security.microsoft.com`
2. Go to Email & Collaboration > Policies & Rules > Threat Policies.
3. In Advanced Delivery, under Phishing Simulation, click "Edit" to add the sending domain, the IP of Lucy, and the simulation URL.\


<figure><img src="../../../.gitbook/assets/image (231).png" alt="" width="375"><figcaption></figcaption></figure>

\
