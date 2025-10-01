# Awareness Settings

## Add an Awareness Template

Select "Add Awareness Training":

<figure><img src="../../../../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You will be redirected to the Awareness Template Gallery, where you can search for, dynamically preview, and select the Awareness Template that elaborates on the attack scenario.
{% endhint %}

## Awareness Settings

Next, you will define the Awareness domain and email settings, this section is expanded below the Attack email template editor.

<figure><img src="../../../../.gitbook/assets/image (257).png" alt="" width="563"><figcaption></figcaption></figure>

### Domain

You can either use the default system domain or send the awareness from a trusted domain.

{% hint style="info" %}
We strongly recommend using the Lucy admin domain for awareness content. This way your SSL is already created and your users see a domain they know and trust when being sent training materials.
{% endhint %}

### SSL

If you are using your Lucy admin domain for awareness content, it is sufficient to use the existing SSL.

{% hint style="danger" %}
Without an SSL certificate, your recipients will encounter a big <mark style="color:red;">red</mark> warning page, signaling that the site they're trying to access isn't secure. This could deter your users from completing the training material.
{% endhint %}

## Select a Certificate

{% hint style="info" %}
See [here](../../../templates/awareness-training-diploma.md) for a guide on editing awareness diplomas.
{% endhint %}

If you wish to send your users a diploma after they complete the training content, select the diploma here.

## Enable End User Portal

Enable this option to create End User accounts for your recipients and enable the End User portal.

{% hint style="info" %}
[End User](../../../users/end-users.md) accounts give your recipients access to a dashboard where they can view their stats and training materials.

See [here](../../../users/end-user-portal-settings.md) for a guide on setting up the end user portal.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Domain

We recommend selecting **System Defaults** for this option and configuring the portal by following the instructions linked above.

#### Send Credentials Type

**Plaintext Passsword:** Add the user's password to the awareness email as an attachement.

**Password Reset Link:** Provide a password reset link the user can click on. Be sure to use the `%user-password-reset%` variable in the email message!

**Login with SSO:** Only use this if you have [configured SSO](../../../settings/common-system-settings/sso-configuration.md) (using OAuth) for your Lucy portal.
