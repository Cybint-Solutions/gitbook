# Other Settings

After configuring Attack and Awareness settings there are a few other miscellaneous settings left.

## Email Settings

<figure><img src="../../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

**Receive Sender Email Replies**

Enable this if you want Lucy to capture any replies to the campaign email and forward them to an inbox of your choosing. To use this feature you must enter a **Forward Email** in the box at the bottom.

**Send Plaintext Email**

Enable this if you want Lucy to send the email as plaintext. This is mostly a troubleshooting method as it will cause all HTML tags to appear as text in the email body, but if your email contains no HTML or other rich text it can be used for live emails as well.

**Random Email**

Enable this option to use a randomly generated email address as the Sender, using the configured email domain.

**DKIM Support**

Enable this option to insert a DKIM record into the campaign email. Please note that this option does not work if you are using an [external SMTP server](../../../settings/common-system-settings/smtp-servers.md) to send campaign emails.

## Tracking

<figure><img src="../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Track Bounced Emails**

Enable this option to detect when a recipient sends an auto-reply in response to a Lucy email, such as an Out-of-Office reply. See [here](../../../settings/submitted-email-settings/incident-autoresponder.md#autoresponse-detection) for info on autoresponse detection.

**Interval Email Testing**

Use an email inbox to keep track of your campaign. Enable this option to send the campaign email to your **tracking email** after every N regular emails, defined by the **tracking interval**.

## Data Collection

<figure><img src="../../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## Campaign Presets

When you are finished with this page, you might want to save these settings as a **Preset:**

<figure><img src="../../../../.gitbook/assets/image (1014).png" alt=""><figcaption></figcaption></figure>

Campaign presets save you even more time by loading in your most commonly re-used settings such as domains, SSL, sender information, and even templates.

You can load these settings by selecting the **Presets** menu at the top of the campaign wizard.

<figure><img src="../../../../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>
