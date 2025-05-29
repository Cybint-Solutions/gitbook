# Hyperlink Attack

### **Understanding the Attack**

**Definition**&#x20;

A hyperlink attack involves embedding malicious URLs in emails. When users click these links, they may be redirected to phishing sites, download malware, or unintentionally disclose personal information. For Lucy, success is measured by whether the user clicks the link.

<figure><img src="../../../.gitbook/assets/vmware_iq5PxlFR0d.gif" alt=""><figcaption><p>This is an example of a Hyperlink Attack, once clicked redirecting to awareness training</p></figcaption></figure>

***

### **Checklist**

* [x] [Register an Attack Domain](../../../application-screens-reference/settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard)
* [x] [Add a Hyperlink Attack to your Campaign](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#add-an-attack-template-to-your-campaign)
* [x] [Ensure "Click" is set as your Success Action](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#success-action)
* [x] [Ensure the sending Domain is whitelisted](../../whitelisting-a-lucy-server/)

***

### **Real-world Examples**

* An employee in the finance department receives an email that appears to be from their HR department, prompting them to complete a timesheet.
* An employee receives an email purportedly from the HR department, containing a link to view their colleagues' performance metrics compared to their own.
* A finance executive receives an urgent email that seems to be from the CEO, containing a payment link for an emergency account transfer.

{% hint style="success" %}
Ready to set up your Hyperlink Attack? See our platform reference article on [Adding an Attack to your campaign.](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#add-an-attack-template-to-your-campaign)
{% endhint %}

***

### **User Detection Methods**

To help employees recognize and respond to hyperlink phishing attempts effectively, the following user detection methods can be incorporated into training programs:

#### Email Analysis

**Check Sender Details:** Verify the sender's email address and domain to ensure they match the legitimate source.

**Look for Red Flags:** Be wary of emails with poor grammar, spelling errors, or unusual formatting.

#### URL Inspection

**Hover Over Links:** Before clicking, hover over links to view the actual URL and ensure it points to a legitimate site.

**Check for HTTPS:** Ensure the website URL starts with "https://" and look for a padlock symbol, indicating a secure connection.

#### Content Verification

**Suspicious Attachments:** Avoid opening unexpected attachments or downloading files from unknown sources.

**Urgency and Threats:** Be cautious of emails that create a sense of urgency, pressure to act quickly, or threaten negative consequences.

#### Link Appearance Checks

**Verify Link Text:** Ensure the visible text of the hyperlink matches the actual URL. For example, a link labeled as “www.lucysecurity.com” should not redirect to “www.lucysecurtiy.com.”

**Type Known URLs Manually:** Instead of clicking on a link, manually type the known and trusted URL into your browser to ensure you are visiting the correct site.

#### Communication Verification

**Cross-Check Requests:** If an email or message asks for sensitive information, verify the request through a separate communication channel, such as a phone call to the supposed sender.

#### Incident Reporting

**Report Suspicious Links:** Immediately report any suspicious links to the IT or security department for further analysis.

**Use Reporting Tools:** Deploy the [Lucy Phish Button](../../../application-screens-reference/settings/submitted-email-settings/) for all users to use as a reporting tool.

***
