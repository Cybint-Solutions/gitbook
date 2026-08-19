# SMS Settings

## Introduction

LUCY supports SMS integration for **smishing campaigns**. SMS messages can be sent using LUCY's default SMS provider or through an account with one of the supported third-party SMS providers.

Before configuring SMS, make sure you have a supported LUCY license, sufficient SMS credits, and an SMS provider selected.

## Requirements

The following prerequisites are required to send SMS messages from LUCY:

* A **Commercial (Pro or Elite)** Lucy license.
* Sufficient balance or credits for SMS delivery.
* An SMS provider configured in Lucy.

## Configure SMS Settings

1. Navigate to **Settings → Common System Settings → SMS Settings**.
2. Select one of the available SMS configuration options.

<figure><img src="../../../.gitbook/assets/image (1060).png" alt=""><figcaption></figcaption></figure>

#### Default

The **Default** option uses LUCY's integrated third-party SMS provider, **Vonage**.

This option is the simplest way to configure SMS delivery and does not require you to provide your own SMS provider account.

#### Custom

The **Custom** option allows you to connect LUCY to your own account with a supported SMS provider.

The following providers are supported:

* Ducont
* MessageBird
* SMSmode
* Messente
* Vonage

Select the provider you want to use and enter the credentials and configuration details required by that provider.

## Before Running a Smishing Campaign

Smishing campaigns require additional configuration because SMS delivery depends on external providers and mobile carrier networks.

### SMS Provider Whitelisting

Before sending SMS campaign traffic, you must submit the required whitelisting information to your SMS provider.

Whitelisting helps ensure that campaign traffic is permitted by the relevant carrier networks and reduces the risk of delivery issues or restrictions.

Do not schedule a smishing campaign until the required whitelisting process has been completed.

{% hint style="danger" %}
**Allow at least 4 weeks for the whitelisting process.**
{% endhint %}

### Campaign Configuration

Smishing campaigns involve configuration requirements that are specific to SMS delivery and may vary depending on the provider and target environment.

If you are setting up a smishing campaign for the first time, contact your **Solution Engineer** before starting the campaign to confirm that the required configuration is in place.

For instructions on creating a smishing campaign, see [Smishing](../../../guides/attack-simulations/attack-types/smishing.md).

***

## FAQ

#### How do I check my available balance?

Your available SMS balance depends on the SMS provider and account configuration. Check the configured provider account or the SMS balance displayed in LUCY, if available.

#### What is the cost per SMS?

SMS pricing depends on the configured provider, destination country, carrier, and message type. Contact your SMS provider for current pricing information.
