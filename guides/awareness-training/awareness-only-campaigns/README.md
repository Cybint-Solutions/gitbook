# Awareness Only Campaigns

## Introduction

This guide provides instructions for setting up an Awareness-Only Campaign in Lucy, from initial configuration to final reporting. Awareness-Only Campaigns are designed to educate users on specific security topics without involving any phishing simulation or tracking. They typically include informative emails, security reminders, or training modules aimed at increasing user awareness.

***

## Checklist

* [x] [Register a training domain (Optional)](../../../application-screens-reference/settings/common-system-settings/domains/)

{% hint style="success" %}
Awareness campaigns can safely be run on your admin domain, or you can register a dedicated training domain.
{% endhint %}

* [x] [Create a recipient group](../../quick-guides/create-your-first-campaign/campaign-setup/recipients.md)
* [x] Choose an awareness topic\
  For inspiration, check out our [awareness templates](../../../application-screens-reference/templates/awareness-templates.md). Don't forget you can [create your own](../awareness-template-customization.md)!
* [x] [Download the awareness template](../../../application-screens-reference/templates/download-templates.md)

***

## Create the Campaign

Go to the **Campaign Dashboard** and start the campaign [wizard](../../../application-screens-reference/campaigns/new-campaign/wizard-mode/). Select **Educate Employees** and then select **Start Awareness Training** to begin crafting your campaign.

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

***

## Select a Template

The wizard will bring you to the Awareness Template Gallery where you can view all of your installed templates and preview the email or web page for each of them. When selecting a template in the wizard you will be prompted to choose a language - if you want to add more language configurations you can do so later, so choose one language to get started.

### Template Filters

The gallery can be filtered by language, template type, intended audience for the content, difficulty, and duration. You can view templates you're already using, favorites, custom templates, or ones with responsive CSS.

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Most templates are configured by default for mobile-sized screens. If you encounter one that is not, [contact technical support](../../../when-to-contact-us/contact-technical-support.md) to request an adjustment.
{% endhint %}

***

## Training Settings

Just like an attack campaign, you'll need to configure settings for the domain, email, and tracking data.&#x20;

### Domain and Email

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

### Email Content

You can edit the email content in the wizard, but you will have more editor options once the campaign is created.

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

### Certificate

Select a [diploma](../../../application-screens-reference/templates/training-diploma.md) for the user to receive after completing the training. Diplomas are designed for landscape and portrait orientation.

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

***

## Additional Settings

### Email Settings

* **Receive Sender E-Mail Replies**: Enable this to allow recipients to reply to the sender’s email.
* **Send Plain-Text Email**: Check this option to send emails in plain-text format instead of HTML.
* **Random Email**: Randomizes the sender’s email address to avoid patterns that could be detected by spam filters.
* **DKIM Support**: Enables Domain Keys Identified Mail (DKIM) to authenticate emails and improve delivery rates.
* **Forward Email**: Input an email address where replies will be forwarded.

### Tracking

* **Track Bounced Emails**: Enable this option to monitor and track email bounce rates.
* **Interval Email Testing**: Set up periodic email testing to ensure deliverability throughout the campaign.

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

### End User Portal

Here you can configure options that control end-user access to the portal and the types of emails they will receive.

* **Enable End User Portal Access**: When toggled on, this allows end users to access the portal where they can view training modules, progress, and certificates.
* **End User Direct Login**: This option enables direct login for end users, simplifying access without needing additional authentication steps.
* **Domain**: Select the domain that will host the end user portal.
* **Send Credentials Type**: Choose how credentials are sent to users. Options include attaching the password to the email. sending a password reset link, or using OAuth 2.0 for Single Sign-On.

{% hint style="success" %}
Whichever option you choose for credentials, be sure to include the proper link in the email:

Portal Link: `%user-profile-link%`

Password Reset Link: `%user-password-reset%`

SSO: `%user-login-url%`
{% endhint %}

#### Additional email settings for end users

* **Do not send awareness emails**: Check this box if you do not want to send awareness-related emails to the end users. This means the recipients will have to access the content through the end user portal.
* **Do not send certificate emails**: Check this box if you do not want users to receive certificate completion emails after finishing training modules. This means the certificate will only be available in the end user portal.

***

## Recipients

Add the [recipient group](../../quick-guides/create-your-first-campaign/campaign-setup/recipients.md) this campaign is intended to reach. The wizard only allows you to add a single group, but you can add more once the campaign is created.

You can also create groups on-the-fly on this page, but this is only recommended if you are testing the campaign with a few users and not when you are adding recipients for the real thing.

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

***

## Review and Create

On the final page of the wizard you can review all of your settings before creating the campaign. You can go back to any step by selecting the header at the top.

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

When you're ready, select **Create Campaign** to proceed. As usual you will be presented with three options: Start Campaign, Initiate Test Run, and Go to Campaign.
