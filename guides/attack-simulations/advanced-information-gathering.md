# Advanced Information Gathering

### **Introduction**

LUCY helps organizations run phishing simulations to identify vulnerable users. However, ensuring a user's browser is safely configured, especially when accessing corporate email from personal devices, remains a challenge.

### **Advanced Information Gathering Framework**

LUCY's Advanced Information Gathering (AIG) tool enhances user awareness training by mimicking drive-by malware attacks to test internal security. AIG targets vulnerabilities in web browsers, the primary entry point for many security threats.

AIG can safely expose web and browser-based vulnerabilities, such as cross-site scripting (XSS), using client-side attack vectors. If a user clicks on a link embedded by AIG, their browser connects to the AIG server integrated into LUCY. This connection allows AIG to perform various actions on the browser, such as redirecting the user, changing URLs, or generating dialogue boxes.

### **Purpose of Advanced Information Gathering**

With AIG integrated into LUCY, companies can assess two critical security questions:

1. Would an employee potentially fall for a phishing attack?
2. If they did, would their browser's security settings prevent further damage from browser-exploitation malware?

### What Information is Gathered?

**Browser Details:** Tracks specific browser information like type, version, and extensions. This helps identify security weaknesses or confirm if the browser is up-to-date with best practices.

**Firebug Information:** Firebug is a popular web development tool. If a user has Firebug installed, it could potentially be used to debug or modify webpages. Tracking whether Firebug or similar tools are present can reveal if there's an increased risk of web-based threats or attacks.

**Popup Blocker:** This checks if the user’s browser is configured to block popup windows. Popups are often used in phishing attacks to deliver malicious content, so knowing whether popup blockers are active can be indicative of the user's level of vulnerability.

**Geo Location:** By determining the geographic location of the user, the organization can assess if there are access patterns from unusual locations that could indicate compromised credentials or other security issues.

**Social Network:** This feature checks for active connections to social networks from the user’s browser. Given that social networks can be platforms for phishing and malware distribution, awareness of such activity can be crucial for understanding the social media risk landscape.

**Proxy:** Identifying whether the user is connected to the internet via a proxy can be important for security. Proxy usage can obscure the true IP address, which could either be a legitimate privacy measure or a method to hide malicious activity.

### **Setting Up Advanced Information Gathering in LUCY**

Advanced Information Gathering runs in the background of a phishing campaign's landing page. It is operational only in scenarios where a user-accessible landing page is active.

{% hint style="info" %}
For detailed setup instructions, please consult our platform reference article on [Advanced Information Gathering](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#advanced-information-gathering).
{% endhint %}

### Advance Information Gathering Statistics

After completing the attack, the Advanced Information Gathering (AIG) statistics will be accessible in multiple locations. Initially, an administrator can quickly view these by navigating to the [Recipient Statistics](../../application-screens-reference/campaigns/campaign-settings/results/statistics.md#recipients) within the campaign, where the report can be directly evaluated in the user interface.

<figure><img src="../../.gitbook/assets/image (546).png" alt=""><figcaption></figcaption></figure>

Once the recipient's profile is selected, scroll down to view the Advance Information Gathering tab:

<figure><img src="../../.gitbook/assets/image (547).png" alt=""><figcaption></figcaption></figure>

Exporting the campaign results to a CSV or XML file will provide detailed information, including the operating system (OS), IP address, browser type, plugins, Proxy-IP and Geo-Location of the user in the report:

<figure><img src="../../.gitbook/assets/image (548).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Refer to our platform reference article on [Campaign Exports](../../application-screens-reference/campaigns/campaign-settings/results/exports.md)
{% endhint %}

