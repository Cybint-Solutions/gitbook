# Messenger Settings

## Introduction

LUCY Awareness supports integration with WhatsApp messaging services to deliver awareness messages and campaign notifications. Two integration options are available:

* **WhatsApp (by Meta)** – Direct integration using Meta’s official WhatsApp Business Cloud API.
* **WhatsApp (via Messente)** – Integration via the third-party Messente messaging platform.

{% hint style="info" %}
Navigate to: **Settings > Common System Settings > Messenger Settings**
{% endhint %}

***

## Creating a WhatsApp Campaign

{% hint style="success" %}
To begin using WhatsApp with Lucy please contact your **Solution Engineer** by email.
{% endhint %}

## WhatsApp (by Meta)

Direct API integration with Meta’s WhatsApp Business platform.

### Prerequisites

* A Meta Developer account with a registered app
* A verified WhatsApp Business number
* Admin access to generate tokens and configure webhooks

### Configuration Steps

**1. Create a Permanent Token**

* Go to the [Meta App Dashboard](https://developers.facebook.com/)
* Navigate to **Business Settings → System Users**
* Generate a token and assign the following permissions:
  * `whatsapp_business_messaging`
  * `whatsapp_business_management`
  * `whatsapp_business_manage_events`

**2. Get Your Sender ID**

* In the **API Setup** section, locate and copy your **Phone Number ID**

**3. Configure in LUCY**

* Go to **Settings → Common System Settings → Messenger Settings**
* Select provider: **WhatsApp (by Meta)**
* Paste the **token** into the **Secret Key** field
* Paste the **Phone Number ID** into the **Sender** field
* Set a **Webhook Token** (any secure string)
* Click **Save**

<figure><img src="../../../.gitbook/assets/image (997).png" alt=""><figcaption></figcaption></figure>

**4. Webhook Setup in Meta**

* In the Meta App Dashboard, go to **Webhooks**
* Select **WhatsApp Business Account**
* Set the **Callback URL** to: `https://update1.phishing-server.com`
* Use the same **Webhook Token** as set in LUCY
* Enable the **messages** event

***

## WhatsApp (via Messente)

Integration using Messente’s cloud-based messaging services.

### Prerequisites

* A registered [Messente account](https://messente.com)
* An approved sender name

### Configuration Steps

**1. Get Messente Credentials**

* Sign up or log in at [messente.com](https://messente.com)
* Navigate to the **API Settings** section
* Copy your **Username** and **API Password**

**2. Approve a Sender Name**

* In the Messente dashboard, go to **Sender Settings**
* Click **Add New Sender Name**
* Enter your sender name (e.g., company name)
* Submit for approval (typically 1–3 business days)

**3. Configure in LUCY**

* Go to **Messenger Settings** (under Templates)
* Select provider: **WhatsApp (via Messente)**
* Enter your **Username**, **Password**, and approved **Sender**
* Click **Save**

<figure><img src="../../../.gitbook/assets/image (999).png" alt=""><figcaption></figcaption></figure>

***

## WhatsApp Custom Messages

LUCY supports sending **custom WhatsApp messages** via Meta's API.\
This feature requires additional configuration and relies on user interaction.

### Message Flow

Custom messages can only be delivered **after a recipient replies** to an initial Meta-approved lure message. LUCY automatically handles this by first sending the predefined template. Once the recipient replies, your custom message is sent.

***

### Setup Steps

**1. Configure Webhook in Meta Dashboard**

* Go to [Meta App Dashboard](https://developers.facebook.com/apps/)
* Select your LUCY app
* Navigate to **Webhooks** (in the sidebar)
* Choose **WhatsApp Business Account** from the product list
* Set:
  * **Callback URL**: `https://update1.phishing-server.com`
  * **Verify Token**: Same value as used in LUCY
* Click **Save**
* Enable the **messages** event toggle

***

### Using a Custom Message

1. Create a new campaign using [expert mode](../../campaigns/expert-mode.md).
2. Go to **Scenario Settings** and click "New Scenario".
3. In the **Message Template** tab set the **Type** to "Messenger".
4. Enable **Custom Message** and enter your message text.
5. Click **Save**.

{% hint style="info" %}
Custom messages are only sent **after** a recipient responds to the initial message. Some delay may occur between the reply and message delivery.
{% endhint %}

***

### Using WhatsApp Templates

If you prefer to use a template from Meta you can simply enter the name of the template in the **Messate Template** settings:

<figure><img src="../../../.gitbook/assets/image (1000).png" alt=""><figcaption></figcaption></figure>
