# Data Entry Attack

## Understanding the Attack

A data entry attack is a targeted effort where attackers deceive victims into entering their login credentials on a fake website. These attacks often leverage email spoofing, creating a sense of urgency or trust to compel the victim to act quickly.

<figure><img src="../../../.gitbook/assets/vmware_orfVEQ4vCE.gif" alt=""><figcaption><p>This is an example of a Data Entry Attack, once clicked the user is directed to a fake landing page</p></figcaption></figure>

***

## Checklist

* [x] [Register an Attack Domain](../../../application-screens-reference/settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard)
* [x] [Add a Data Entry Attack to your Campaign](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#add-an-attack-template-to-your-campaign)
* [x] [Ensure "Data Submit" is set as your Success Action](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#success-action)
* [x] [Ensure the sending Domain is whitelisted](../../whitelisting-a-lucy-server/)

***

## Real-world Examples

* A corporate employee receives an email that appears to be from the IT department, instructing them to update their password on a fake company portal.
* A user gets a notification from a popular social media platform about unusual activity and is redirected to a fake social media site to log in.
* A recipient is notified that they are running late for a Teams or Zoom meeting and receives an email with a link to join the meeting. In their haste, they click the link and are prompted to log in on a fake Teams or Zoom login page, unknowingly entering their credentials.

{% hint style="success" %}
Ready to set up your Data Entry Attack? See our platform reference article on [Adding an Attack to your campaign.](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md)
{% endhint %}

***

## User Detection Methods

To help employees recognize and respond to Data Entry phishing attempts effectively, the following user detection methods can be incorporated into training programs:

**Email Analysis**

* **Check Sender Details:** Verify the sender's email address and domain to ensure they match the legitimate source.
* **Look for Red Flags:** Be wary of emails with poor grammar, spelling errors, or unusual formatting.

**URL Inspection**

* **Hover Over Links:** Before clicking, hover over links to view the actual URL and ensure it points to a legitimate site.
* **Check for HTTPS:** Ensure the website URL starts with "https://" and look for a padlock symbol, indicating a secure connection.

**Content Verification**

* **Suspicious Attachments:** Avoid opening unexpected attachments or downloading files from unknown sources.
* **Urgency and Threats:** Be cautious of emails that create a sense of urgency, pressure to act quickly, or threaten negative consequences.

**Login Page Checks**

* **Website Appearance:** Verify that the login page looks exactly as expected. Fake sites often have slight visual discrepancies.
* **Double-Check URLs:** Manually type the known URL of the website into your browser instead of clicking on links in emails.

**Communication Verification**

* **Cross-Check Requests:** If an email asks for sensitive information, verify the request through a separate communication channel, such as a phone call to the supposed sender.

**Incident Reporting**

* **Report Suspicious Emails:** Immediately report any suspicious emails to the IT or security department for further analysis.
* **Use Reporting Tools:** Deploy the [Lucy Phish Button](../../../application-screens-reference/settings/submitted-email-settings/) for all users to use as a reporting tool.

***
