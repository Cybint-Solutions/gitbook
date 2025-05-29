# QR Codes

## Understanding the Attack

A QR-code phishing attack involves embedding a malicious URL within a QR code. When victims scan the QR code, they are directed to a fake website designed to steal sensitive information, such as login credentials or personal data.



## Checklist

* [x] [Register an Attack Domain](../../../application-screens-reference/settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard)
* [x] [Add a QR-code template to your campaign](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#add-an-attack-template-to-your-campaign)
* [x] [Set the success action](../../quick-guides/create-your-first-campaign/campaign-setup/attack-settings.md)
  * [x] If the QR code links to a data-entry page, select **Data Submit**.
  * [x] If the QR code redirects to an awareness training or other page, select **Click**.
* [x] [Ensure the sending Domain is whitelisted](../../whitelisting-a-lucy-server/)

## Real-world Examples

* At a conference, attackers place fake QR codes near registration, leading attendees to a phishing site to steal login credentials. Victims think they're logging into the event portal.
* Attackers replace parking meter QR codes with fake ones, tricking users into entering credit card details on a fraudulent payment page. The stolen data is used for financial theft.
* Diners scan fake QR codes on restaurant tables, leading to phishing sites that steal personal information. They believe they’re accessing the digital menu.

## User Detection Methods

**Avoid Scanning from Unverified Sources**: Be cautious about scanning codes from posters, emails, social media, or ads that seem suspicious, especially in public places or unexpected messages.

**Look for Tampering**: Malicious actors sometimes overlay a fraudulent QR code on top of a legitimate one (on posters, signs, or printed materials). If a QR code looks like it’s been altered or pasted over something else, avoid scanning it.

**Check the Link Before Opening**: Many QR scanning apps and smartphones offer a feature that displays the URL before visiting the site. Review the link carefully for suspicious or misspelled URLs.

**Avoid Shortened URLs**: Phishers often use URL shorteners to disguise malicious links. If the previewed link is a shortened URL (e.g., bit.ly), proceed with caution, or use a service to expand the link and check where it leads.
