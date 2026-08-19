# Smishing

## Understanding Smishing

**Smishing** is a form of phishing that uses SMS messages to direct recipients toward a malicious or simulated website or to request information.

In Lucy, a smishing scenario can use one of two primary attack types:

* **Hyperlink attack:** The recipient receives an SMS containing a link and is tracked when they click it.
* **Data-entry attack:** The recipient is directed to a landing page where they are asked to submit information.

Smishing campaigns require additional configuration because SMS delivery is subject to requirements imposed by SMS providers, mobile carriers, and the countries where recipients are located.

If you are setting up a smishing campaign for the first time, contact your **Customer Success Manager or Solution Engineer** before starting the campaign.

## Before You Begin

Complete the following steps before launching a smishing campaign:

* [ ] [Register an attack domain](../../../application-reference/settings/common-system-settings/domains/).
* [ ] [Select an SMS provider](../../../application-reference/settings/common-system-settings/sms-settings.md).
* [ ] Create a campaign using [**Expert Mode**](../../../application-reference/campaigns/expert-mode.md).
* [ ] Add an attack scenario.
* [ ] Configure the scenario's success action:
  * **Click** for a hyperlink attack.
  * **Data Submit** for a data-entry attack.
* [ ] Enable the [**Bitly URL shortener**](../../../application-reference/settings/common-system-settings/url-shortener-settings.md) in the attack scenario settings.
* [ ] Submit the required information for SMS provider whitelisting.
* [ ] Register the SMS sender/originator.
* [ ] Confirm that provider whitelisting has been completed before launching the campaign.

{% hint style="danger" %}
SMS provider whitelisting can take several weeks. Allow a minimum of **4 weeks** for the process.
{% endhint %}

## Create the Campaign

#### 1. Register an Attack Domain

Register and configure the attack domain that will be used by the smishing scenario.

Ensure that the domain is correctly configured and accessible before creating the campaign.

#### 2. Select an SMS Provider

Select the SMS provider you intend to use for the campaign.

The available configuration depends on whether you are using Lucy's default SMS integration or a custom integration with your own provider account.

For more information, see [SMS Integration](https://chatgpt.com/sms-integration/README.md).

#### 3. Create the Campaign

Create a new campaign using **Expert Mode**.

Add the required attack scenario to the campaign.

#### 4. Configure the Attack Scenario

Configure the scenario according to the type of smishing attack you want to perform.

**Hyperlink Attack**

For a hyperlink scenario, set the **Success Action** to:

**Click**

This records the recipient's interaction with the link.

**Data-Entry Attack**

For a data-entry scenario, set the **Success Action** to:

**Data Submit**

This records when the recipient submits data through the landing page.

#### 5. Enable URL Shortening

Enable the **Bitly URL shortener** in the attack scenario settings.

URL shortening can help reduce the length of links included in SMS messages and help keep the overall message within applicable SMS character limits.

## SMS Provider Whitelisting

SMS traffic is subject to provider and carrier requirements. Before sending a campaign, you must provide the required campaign and sender information to the SMS provider.

The provider may require information about:

* The sender/originator.
* The legal entity sending the messages.
* The intended use case.
* The SMS content.
* Links included in the messages.
* The countries where recipients are located.
* The number of SMS messages to be sent.
* The campaign duration.
* Proof of authorization or consent from the organization conducting the simulation.

{% hint style="danger" %}
Do not schedule the campaign until the required provider registration and whitelisting processes have been completed.
{% endhint %}

## Register the SMS Sender

The SMS sender, also called the **originator**, identifies the sender displayed to the recipient.

The sender must be registered with the SMS provider when required by the destination country or carrier. An unregistered sender may result in messages being rejected or not delivered.

#### Originator Information

The following information may be required when registering an originator.

| Field                                | Description                                                                                                                                                               |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Originator**                       | The sender displayed to the recipient. Depending on the provider and country, this may be an alphanumeric sender ID, shortcode, or virtual/mobile number.                 |
| **Originator legal company country** | The country where the company owning the originator is legally registered.                                                                                                |
| **Originator legal company name**    | The legal name of the company that owns the originator.                                                                                                                   |
| **Originator corporate URL**         | The corporate website of the company that owns the originator.                                                                                                            |
| **Industry vertical**                | The organization's industry, such as Education, Technology, or Agriculture.                                                                                               |
| **Call to action (CTA) URL**         | A URL included in SMS messages sent using the registered originator. In Lucy, this is typically the value of the `%link%` variable.                                       |
| **Other CTA(s)**                     | Any additional URLs that may appear in the SMS message.                                                                                                                   |
| **Description of use case**          | A description of how the SMS service will be used. Explain any relationship between the registered originator and the legal company name or corporate URL if they differ. |
| **SMS template**                     | A copy of the SMS message that will be sent during the campaign.                                                                                                          |

## Additional Campaign Information

The SMS provider may also request the following information:

1. **Sender ID:** The name displayed as the sender of the SMS.
2. **Client consent:** Documentation from the organization authorizing the simulated smishing campaign and use of the specified Sender ID.
3. **Total SMS count:** The estimated number of SMS messages to be sent.
4. **SMS content:** The exact message that will be used in the campaign.
5. **Campaign duration:** The planned campaign duration, including any testing period.
6. **Locations:** The countries where campaign recipients are located.

Provider requirements can vary by country and may change over time. Always follow the requirements provided by the SMS provider for the countries targeted by the campaign.
