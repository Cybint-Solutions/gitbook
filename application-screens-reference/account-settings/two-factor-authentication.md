# Two Factor Authentication

Lucy provides **Email** and **SMS-based** two-factor authentication.&#x20;

{% hint style="info" %}
Navigate to **Account -> 2FA Configuration**

<img src="../../.gitbook/assets/image (745).png" alt="" data-size="original">
{% endhint %}

{% hint style="danger" %}
SMS-based 2FA has been deprecated by Twilio. Please use Email-based authentication which is available on all Lucy servers from version 5.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Email" %}
### **Overview**

Email-based authentication will generate secret codes directly from your Lucy server and send them to the registered email address of your administrative user.

This method is advantageous as it does not require any external third-party services.

{% hint style="info" %}
Please note, your delivery method determines how your Lucy server will send the 2FA verification code. This delivery method is defined in the [Mail Settings](../settings/common-system-settings/mail-settings.md) of the platform.
{% endhint %}

### Setup Steps

1. Select Email as your 2FA Method.

<figure><img src="../../.gitbook/assets/image (685).png" alt="" width="440"><figcaption></figcaption></figure>

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
{% endtab %}

{% tab title="SMS" %}
{% hint style="danger" %}
SMS-based 2FA has been deprecated by Twilio. Please use Email-based authentication which is available on all Lucy servers from version 5.&#x20;
{% endhint %}

### **Overview**

Lucy utilizes the Authy service for 2-factor authentication (2FA), enabling login via a security token from a mobile app or SMS.

### **Setup Steps**

1. **Create a Twilio Account:**
   * Sign up for a free Twilio account [here](https://www.twilio.com/try-twilio).
   * Log in to the [Authy dashboard](https://dashboard.authy.com/signin).
2. **Set Up Application:**
   * In the dashboard, navigate to "Authy" → "Applications" → "Get Started."
   * Verify your phone number by entering it and the received code.
   * Name your application (e.g., Lucy) and create it.
3. **Add User and Retrieve API Key:**
   * Add your first user's email and phone number.
   * Select "App Token" and enter the generated token from the Authy app on your phone.
   * Choose your created application, go to "Settings," and view your unique API key by clicking the eye icon next to "Production API KEY."
   * Copy this API key for use in Lucy.

**Configure Lucy:**

1. Open Lucy's interface.
2. Go to **Settings → Advanced System Settings -> Advanced Settings**
3. Paste the API key into the ["2FA" field](../settings/advanced-system-settings/advanced-settings.md#id-2fa-key) and save.

**Setup 2FA for User Accounts:**

1. Each user should go to the "Account" page.
2. Enter their phone number in the corresponding fields and save.
3. Press "Configure 2FA" and follow the on-screen instructions.

After configuring 2FA, users will be logged out and will need a 2FA token for the next login, obtainable via the Authy mobile application or SMS.

**Important Notes:**

* Email-based authentication is beneficial for air-gapped environments as it doesn’t rely on external services.
{% endtab %}
{% endtabs %}

