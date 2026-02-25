# Messenger Settings

## Introduction

LUCY Awareness supports integration with WhatsApp messaging services to deliver awareness messages and campaign notifications. Three integration options are available:

* **WhatsApp (by Meta)** – Direct integration using Meta’s official WhatsApp Business Cloud API.
* **WhatsApp (via Messente)** – Integration via the third-party Messente messaging platform.
* **Microsoft Teams -** Integration via Entra ID (formerly known as Azure).

{% hint style="info" %}
Navigate to: **Settings > Common System Settings > Messenger Settings**
{% endhint %}

***

## WhatsApp (by Meta)

{% hint style="success" %}
To begin using WhatsApp with Lucy please contact your **Solution Engineer** by email.
{% endhint %}

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

## Microsoft Teams

{% hint style="info" %}
Teams messaging is currently in Beta.
{% endhint %}

To connect your Lucy workstation to your MS Teams application all you need to do is set up an app registration in Entra ID and connect it to Lucy. General instructions for this can be found [here](azure-applications.md). Keep reading for the required settings to connect an application for Microsoft Teams.

{% hint style="info" %}
If you already have a connected application, you can skip these steps and simply select the **Microsoft Teams** checkbox in the azure application's settings. Go to **Settings > Common System Settings > Azure Applications** and select the application to view and configure the settings.
{% endhint %}

### App Registration

**Support Account Types**

Accounts in this organizational directory only (Single Tenant).

**Redirect URIs:**

In the app registration menu use a **Web** URI like so: `https://yourlucyURL.tld/oauth` .

After registration, create a second **Single Page Application** redirect URI with the same URL.

**Application ID, Tenant ID, and Secret**

Create a new Secret and then copy all 3 values.

### Connect to Lucy

{% hint style="info" %}
**Note on who can send Teams messages**

It is important to note that the only account that will be authorized to send messages in your Teams application is the account that performs the app authorization.

**No other senders will be able to message your recipients in Teams.**
{% endhint %}

Go to **Settings > Common System Settings > Azure Applications** and create a new application. Give it a name and a Client, then select the **Microsoft Teams** checkbox. Paste the application ID, tenant ID, and secret, then click **Save**.

{% hint style="info" %}
**Note on who can send Teams messages**

It is important to note that the only account that will be authorized to send messages in your Teams application is the account that performs the app authorization at the end of this step. **No other senders will be able to message your recipients in Teams.**
{% endhint %}

Here is a brief overview of the permissions required by the application:

<table><thead><tr><th width="175">Permission</th><th width="112.00006103515625">Type</th><th>Description</th></tr></thead><tbody><tr><td>User.Read</td><td>Delegated</td><td>Allows the app to sign in and read the profile of the signed-in user.</td></tr><tr><td>Chat.Create</td><td>Delegated</td><td>Allows the app to create new one-on-one or group chats on behalf of the signed-in user.</td></tr><tr><td>ChatMessage.Send</td><td>Delegated</td><td>Allows the app to send messages in any chat that the signed-in user has access to.</td></tr><tr><td>Chat.ReadWrite</td><td>Delegated</td><td>Allows the app to read and write all chats the signed-in user can access, including sending messages, editing, and deleting messages.</td></tr><tr><td>openid</td><td>Delegated</td><td>Required for OpenID Connect authentication to identify the signed-in user.</td></tr></tbody></table>

### Set Microsoft Teams as your message provider

After saving and authorizing the app, go to **Settings > Common System Settings > Messenger Settings**. Select Microsoft Teams as the provider and select the azure application you configured in the last step.

Click **Save** and you are now ready to use Microsoft Teams in your campaigns. For assistance designing and executing Teams campaigns please contact your Solution Engineer.
