# End Users

## Introduction

Users might not have time to finish an awareness course right away. They have the ability to [re-schedule](../campaigns/campaign-settings/configuration/base-settings.md#awareness-re-scheduling) the training, but you can also create a login page for your end users where they can access their custom training links at any time without needing to re-send an awareness email. They can also view their lifetime statistics, [risk level](risk-score.md), and [training diplomas](../templates/training-diploma.md) from completed courses.

{% hint style="info" %}
An end user is a recipient with an end user portal account.\
All end users are recipients, but not all recipients are end users.
{% endhint %}

***

## Enabling the Portal

You can enable the portal under [**Base Settings**](../campaigns/campaign-settings/configuration/base-settings.md#end-user-profiles-enabled) within a campaign. Once the campaign is started Lucy automatically creates an End User account for each recipient (unless they already have one from a previous campaign).

<figure><img src="../../.gitbook/assets/image (470).png" alt=""><figcaption></figcaption></figure>

Once the campaign is started the training scenarios will be added to each End User's page.

### Portal URL

The portal page is created under the `/user` directory, so if your server address is `https://my.lucyserver.com`, the portal login will be `https://my.lucyserver.com/user/`.

***

## Creating End Users

Lucy automatically creates end-user profiles for each recipient who receives an awareness training within a campaign, provided that the campaign has **End-User Profiles Enabled** in the [Base Settings](../campaigns/campaign-settings/configuration/base-settings.md#end-user-profiles-enabled).

End Users can also be created by importing recipients through [Active Directory](../settings/common-system-settings/azure-ad-settings.md) or [LDAP](../settings/common-system-settings/ldap-settings.md).

### Login Methods

After enabling the end user portal in the base settings you will be able to select your preferred method of providing credentials to the recipients.

There are three options for granting access to the end-user portal:

1. Attach the password to the email in a .txt file.
2. Send a password reset link (link variable: `%user-password-reset%`).
3. Use SSO (link variable: `%user-login-url%`).

{% tabs %}
{% tab title="Password" %}
#### **Requirements:**

* Enable "End-User Profiles" in [Base Settings](../campaigns/campaign-settings/configuration/base-settings.md#end-user-profiles-enabled).
* On the Base Settings, set "Send Credentials Type" to "**Plain text Password**"
* Ensure the [Awareness Campaign](../campaigns/campaign-settings/configuration/awareness-settings.md) is configured to send emails.

In this example, the user is informed of the Training Portal and the link variable (`%user-profile-link%`) to the portal is injected for the "Log in" word:

<figure><img src="../../.gitbook/assets/image (474).png" alt=""><figcaption></figcaption></figure>

#### Key Considerations

* The password attachment is sent only once, with the first awareness campaign when End-User Profiles are enabled. Users will not receive credentials as an attachment again.
* If a user needs to change their password, they can select "Forgot Password" on the End-User login page.
{% endtab %}

{% tab title="Reset Link" %}
#### **Requirements:**

* Enable "End-User Profiles" in [Base Settings](../campaigns/campaign-settings/configuration/base-settings.md#end-user-profiles-enabled).
* On the Base Settings, set "Send Credentials Type" to "**Password Reset Link**"
* Ensure the [Awareness Campaign](../campaigns/campaign-settings/configuration/awareness-settings.md) is configured to send emails.
* Ensure you have a [system notification email set in the Advanced Settings](../settings/advanced-system-settings/advanced-settings.md#system-notification-email).

In this example, the user is informed of the Training Portal and to reset their password at the provided link (`%user-password-reset%`) :

<figure><img src="../../.gitbook/assets/image (467).png" alt=""><figcaption></figcaption></figure>

#### Key Considerations

* The password reset is sent only once, with the first awareness campaign when End-User Profiles are enabled.
* If a user needs to change their password, they can select "Forgot Password" on the End-User login page.

{% hint style="success" %}
To successfully send password credentials from your Lucy server, ensure you have a [system notification email set in the Advanced Settings](../settings/advanced-system-settings/advanced-settings.md#system-notification-email). This email address must have the relevant [DNS records (SPF/MX)](../settings/common-system-settings/domains/#dns-records-explained) set up and pointed to your Lucy server.
{% endhint %}
{% endtab %}

{% tab title="SSO" %}
#### **Requirements:**

* Enable "End-User Profiles" in [Base Settings](../campaigns/campaign-settings/configuration/base-settings.md#end-user-profiles-enabled).
* On the Base Settings, set "Send Credentials Type" to "**Login With SSO**"
* On the Base Settings, "[Enable SSO for Awareness Websites](../campaigns/campaign-settings/configuration/base-settings.md#enable-sso-for-awareness-websites)"
* Ensure the [Awareness Campaign](../campaigns/campaign-settings/configuration/awareness-settings.md) is configured to send emails.
* Ensure [SSO Authentication](../settings/common-system-settings/sso-configuration.md) was configured and tested.

In this example, the user is informed of the Training Portal and to access the training via SSO at the provided link (`%user-login-url%`) :&#x20;

<figure><img src="../../.gitbook/assets/image (462).png" alt=""><figcaption></figcaption></figure>

#### Key Considerations

* SSO authentication for End-Users can only be configured for one IdP in [SSO Settings](../settings/common-system-settings/sso-configuration.md)
* To ensure the user does not land on the default Lucy login page, it is important to use the correct link variable in your email (`%user-login-url%`)
* Test [SSO authentication](../settings/common-system-settings/sso-configuration.md) before sending out the Awareness campaigns
{% endtab %}
{% endtabs %}

***

## Managing End Users

Existing End Users can be managed from the **Users -> End Users** page.

<figure><img src="../../.gitbook/assets/image (942).png" alt=""><figcaption></figcaption></figure>

Administrators can view the portal page of any end user by selecting their email address. They can also update an end user's information and password by going to that user's **User Settings** page in the portal view.

***

## End User Portal View

The portal is divided in to three pages:

1. Overall Statistics
2. Courses
3. Account Settings

### Overall Statistics

The main page of the portal displays the end user's [risk level](risk-score.md) and training scores, overall statistics, and a summary of their training courses and earned [diplomas](../templates/training-diploma.md).

<figure><img src="../../.gitbook/assets/image (943).png" alt=""><figcaption></figcaption></figure>

### Courses

The courses page shows a user all of their courses organized by status:

<figure><img src="../../.gitbook/assets/image (944).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can switch to a card or list view using the buttons in the top-right.\
Filters on the left-hand side let you view courses by type.
{% endhint %}

***

### Account Settings

On the account settings page a user can update their phone number and default language, reset their password, and enable two-factor authentication.

<figure><img src="../../.gitbook/assets/image (947).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
End users cannot change their email address. If a user's email must be updated they should contact their Lucy administrator who can edit their [recipient entry](../../guides/quick-guides/create-your-first-campaign/campaign-setup/recipients.md).
{% endhint %}
