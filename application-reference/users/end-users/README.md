# End Users

## Introduction

Users may not always have time to complete an awareness course immediately. While they can reschedule their training, you can also provide a login page that allows them to access their custom training links at any time without needing a new awareness email.

Through this login page, users can also view their lifetime statistics, [risk level](../risk-score.md), and [training diplomas](../../templates/awareness-training-diploma.md) from completed courses.

{% hint style="info" %}
An **end user** is a recipient who has an End User Portal account.

All end users are recipients, but not all recipients are end users.
{% endhint %}

***

## Enabling End Users

The end user portal is enabled per-campaign in the Awareness Settings.

Go to **Awareness Education > End Users** and enable the checkbox:

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
#### End User Portal URL

The End User Portal is located in the `/user` directory of your server.

For example, if your server address is `https://my.lucyserver.com`, the portal login page will be available at `https://my.lucyserver.com/user/.`
{% endhint %}

***

## Creating End Users

Lucy automatically creates end-user profiles for recipients who receive awareness training within a campaign, as long as **End User Profiles** is enabled.

End users can also be created via import through [**Active Directory**](../../settings/common-system-settings/azure-ad-settings.md) or [**LDAP**](../../settings/common-system-settings/ldap-settings.md).

***

## Portal Settings

#### User Profile Page Link

You can configure the portal URL on a per-campaign basis. However, it is recommended to use **System Defaults** and configure the URL in the [**End User Portal Settings**](../end-user-portal-settings.md) instead.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* **Lucy Support UI Domain** – Uses the same domain as your admin portal.
* **IP Address** – Uses a raw IP address. Recommended for testing only.
* **System Defaults** – Uses the URL configured in [**End User Portal Settings**](../end-user-portal-settings.md).

#### Send Credentials Type

Choose how passwords are delivered to end users.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

* **Plain Text Password** – Sends the password as a **.txt attachment** with the campaign email. Recommended for testing only.
* **Password Reset Link** – Includes a password reset link in the campaign email. If selected, the email must contain the variable **%user-password-reset%**.
* **Login with SSO** – Uses your **SSO workflow** to authenticate end users. If selected, the email must contain the variable **%user-login-url%**.

#### End User Direct Login

Enable this option to allow end users to log in directly by navigating to the **End User Portal URL**.

If you plan to disable campaign emails, this setting **must** be enabled first.

***

## Managing End Users

Existing end users can be managed from the **End Users** page.

Navigate to: **Users → End Users**

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Administrators can open an end user’s portal page by selecting the user’s **email address**. From the portal view, administrators can also update the user’s information and reset their password through the **User Settings** page.
