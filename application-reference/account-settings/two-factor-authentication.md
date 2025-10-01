# Two Factor Authentication

{% hint style="info" %}
Navigate to **Account -> 2FA Configuration**

<img src="../../.gitbook/assets/image (745).png" alt="" data-size="original">
{% endhint %}

### **Overview**

Email-based authentication will generate secret codes directly from your Lucy server and send them to the registered email address of your administrative user.

{% hint style="info" %}
Please note, your delivery method determines how your Lucy server will send the 2FA verification code.\
This delivery method is defined in the [Mail Settings](../settings/common-system-settings/mail-settings.md) of the platform.
{% endhint %}

### Setup

1. Select Email as your 2FA Method.

<figure><img src="../../.gitbook/assets/image (685).png" alt="" width="440"><figcaption></figcaption></figure>

{% hint style="danger" %}
SMS-based 2FA is no longer supported.
{% endhint %}

2. Click Save to commit your 2FA method
3. Click "Configure 2FA"

The following screen will prompt you to enter the token that was sent to your defined administrator email address. This token will remain active for 20 minutes.

<figure><img src="../../.gitbook/assets/image (686).png" alt=""><figcaption></figcaption></figure>

The email received will be displayed as such:

<figure><img src="../../.gitbook/assets/image (687).png" alt=""><figcaption></figcaption></figure>

Once the code has been entered, you have successfully integrated and authenticated your user using email-based two-factor authentication.

{% hint style="info" %}
If you do not receive the code, please check your spam folder and ensure you have defined a system notification email in the [Advanced System Settings](../settings/advanced-system-settings/advanced-settings.md#system-notification-email).
{% endhint %}
