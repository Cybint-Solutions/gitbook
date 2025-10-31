# Optional Settings

## Certificate (Awareness Diploma)

{% hint style="info" %}
See [here](../../../templates/awareness-training-diploma.md) for a guide on editing awareness diplomas.
{% endhint %}

If you wish to send your users a diploma after they complete the training content, select the diploma here.

## Email Settings

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Receive Sender Email Replies**

Enable this if you want Lucy to capture any replies to the campaign email and forward them to an inbox of your choosing. To use this feature you must enter a **Forward Email** in the box at the bottom.

#### **Send Plaintext Email**

Enable this if you want Lucy to send the email as plaintext. This is mostly a troubleshooting method as it will cause all HTML tags to appear as text in the email body, but if your email contains no HTML or other rich text it can be used for live emails as well.

#### **Random Email**

Enable this option to use a randomly generated email address as the Sender, using the configured email domain.

#### **DKIM Support**

Enable this option to insert a DKIM record into the campaign email. Please note that this option does not work if you are using an [external SMTP server](../../../settings/common-system-settings/smtp-servers.md) to send campaign emails.

## Tracking

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Track Bounced Emails**

Enable this option to detect when a recipient sends an auto-reply in response to a Lucy email, such as an Out-of-Office reply. See [here](../../../settings/submitted-email-settings/incident-autoresponder.md#autoresponse-detection) for info on autoresponse detection.

#### **Interval Email Testing**

Use an email inbox to keep track of your campaign. Enable this option to send the campaign email to your **tracking email** after every N regular emails, defined by the **tracking interval**.

## Data Collection

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

## End User Profiles

Enable this option to create End User accounts for your recipients and enable the End User portal.

{% hint style="info" %}
[End User](../../../users/end-users.md) accounts give your recipients access to a dashboard where they can view their stats and training materials. See [here](../../../users/end-user-portal-settings.md) for a guide on setting up the end user portal.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Domain

We recommend selecting **System Defaults** for this option and configuring the portal by following the instructions linked above.

#### Send Credentials Type

**Plaintext Passsword:** Add the user's password to the awareness email as an attachement.

**Password Reset Link:** Provide a password reset link the user can click on. Be sure to use the `%user-password-reset%` variable in the email message!

**Login with SSO:** Only use this if you have [configured SSO](../../../settings/common-system-settings/sso-configuration.md) using OAuth for your Lucy portal.

## Campaign Presets

When you are finished with this page, you might want to save these settings as a **Preset:**

<figure><img src="../../../../.gitbook/assets/image (1014).png" alt=""><figcaption></figcaption></figure>

Campaign presets save you even more time by loading in your most commonly re-used settings such as domains, SSL, sender information, and even templates.

You can load these settings by selecting the **Presets** menu at the top of the campaign wizard.

<figure><img src="../../../../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>
