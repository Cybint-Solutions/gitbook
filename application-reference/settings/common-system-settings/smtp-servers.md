# SMTP Servers

## **Introduction**

Lucy supports sending campaign emails through an external SMTP relay—either via credentials or OAuth2 (Azure). Using a familiar company domain improves email deliverability and trust.

***

## Setup

{% hint style="info" %}
Navigate to **Settings > Common System Settings > SMTP Servers**
{% endhint %}

Select **"+ Add Server"**

<figure><img src="../../../.gitbook/assets/image (1002).png" alt=""><figcaption></figcaption></figure>

Next, you will define the SMTP Mail Server parameters:

| Field              | Description                                        |
| ------------------ | -------------------------------------------------- |
| **Name**           | Friendly identifier for selection in Lucy          |
| **Client**         | Optional—restricts server to a specific client     |
| **Host & Port**    | Example: `smtp.office365.com`, port `587`          |
| **Encryption**     | `STARTTLS` (recommended), or `SSL/TLS` on port 465 |
| **Authentication** | Choose between **Password** or **OAuth2 (Azure)**  |

<details>

<summary>Authentication Methods</summary>

#### **Password Authentication**

* Requires SMTP admin credentials
* Works with most standard SMTP servers
* Avoid using a shared corporate relay that could be blacklisted during phishing tests

#### **OAuth2 (Azure) – for Office 365 & Microsoft Entra ID**

**Azure App Registration:**

1. In Azure Portal, register a new app.
2. Under _Authentication_, add the redirect URI:\
   `https://<your‑lucy‑url>/smtp/oauth` (no trailing slash).
3. Record the **Tenant ID**, **Client ID**, and **Client Secret**.

**In Settings > Common System Settings > SMTP Servers:**

* Select **Authentication Method = OAuth2**, **Provider = Office 365**
* Enter the Azure **Client ID**, **Client Secret**, and **Tenant ID**
* Test the connection via Lucy’s "Test Connection" tool—check console logs for success or errors.

{% hint style="warning" %}
The **Lucy user account** you are logged in with during authentication is the only account that will be able to send emails through this SMTP connection.\
To allow multiple Lucy users to send emails via this SMTP server, you must create separate SMTP entries in Lucy for each user, all connecting to the same Azure application.
{% endhint %}

</details>

Once completed, click **Save** to commit your SMTP server settings.

{% hint style="success" %}
If these settings are ever updated, click **Authorize** to reconnect Lucy to the SMTP server.
{% endhint %}

***

## Test Connection

To test your SMTP server settings, simply enter the sender email address (which must be the exact email address associated with your SMTP server) and a recipient email address you have access to. Then, click or select "Test" to initiate the testing process.

<figure><img src="../../../.gitbook/assets/image (523).png" alt="" width="375"><figcaption></figcaption></figure>

The response is logged just below the test input:

<figure><img src="../../../.gitbook/assets/image (196).png" alt="" width="281"><figcaption></figcaption></figure>

<details>

<summary>SMTP Error Status Codes</summary>



**connect**

* 220 domain Service ready
* 421 domain Service not available, closing transmission channel

**HELO**

* 250 Requested mail action okay, completed
* 500 Syntax error, command unrecognised
* 501 Syntax error in parameters or arguments
* 504 Command parameter not implemented
* 521 \<domain> does not accept mail \[rfc1846]
* 421 \<domain> Service not available, closing transmission channel

**EHLO**

* 250 Requested mail action okay, completed
* 550 Not implemented
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 504 Command parameter not implemented
* 421 \<domain> Service not available, closing transmission channel

**MAIL**

* 250 Requested mail action okay, completed
* 552 Requested mail action aborted: exceeded storage allocation
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 421 \<domain> Service not available, closing transmission channel

**RCPT**

* 250 Requested mail action okay, completed
* 251 User not local; will forward to \<forward-path>
* 550 Requested action not taken: mailbox unavailable
* 551 User not local; please try \<forward-path>
* 552 Requested mail action aborted: exceeded storage allocation
* 553 Requested action not taken: mailbox name not allowed
* 450 Requested mail action not taken: mailbox unavailable
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 503 Bad sequence of commands
* 521 \<domain> does not accept mail \[rfc1846]
* 421 \<domain> Service not available, closing transmission channel

**DATA**

* 354 Start mail input; end with \<CRLF>.\<CRLF>
* 451 Requested action aborted: local error in processing
* 554 Transaction failed
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 503 Bad sequence of commands
* 421 \<domain> Service not available, closing transmission channel

**received data**

* 250 Requested mail action okay, completed
* 552 Requested mail action aborted: exceeded storage allocation
* 554 Transaction failed
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage

**RSET**

* 200 (nonstandard success response, see rfc876)
* 250 Requested mail action okay, completed
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 504 Command parameter not implemented
* 421 \<domain> Service not available, closing transmission channel

**SEND**

* 250 Requested mail action okay, completed
* 552 Requested mail action aborted: exceeded storage allocation
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 421 \<domain> Service not available, closing transmission channel

**SOML**

* 250 Requested mail action okay, completed
* 552 Requested mail action aborted: exceeded storage allocation
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 421 \<domain> Service not available, closing transmission channel

**SAML**

* 250 Requested mail action okay, completed
* 552 Requested mail action aborted: exceeded storage allocation
* 451 Requested action aborted: local error in processing
* 452 Requested action not taken: insufficient system storage
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 421 \<domain> Service not available, closing transmission channel

**VRFY**

* 250 Requested mail action okay, completed
* 251 User not local; will forward to \<forward-path>
* 550 Requested action not taken: mailbox unavailable
* 551 User not local; please try \<forward-path>
* 553 Requested action not taken: mailbox name not allowed
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 504 Command parameter not implemented
* 421 \<domain> Service not available, closing transmission channel

**EXPN**

* 250 Requested mail action okay, completed
* 550 Requested action not taken: mailbox unavailable
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 504 Command parameter not implemented
* 421 \<domain> Service not available, closing transmission channel

**HELP**

* 211 System status, or system help reply
* 214 Help message
* 500 Syntax error, command unrecognized
* 501 Syntax error in parameters or arguments
* 502 Command not implemented
* 504 Command parameter not implemented
* 421 \<domain> Service not available, closing transmission channel

**NOOP**

* 200 (nonstandard success response, see rfc876)
* 250 Requested mail action okay, completed
* 500 Syntax error, command unrecognized
* 421 \<domain> Service not available, closing transmission channel
*

**QUIT**

* 221 \<domain> Service closing transmission channel
* 500 Syntax error, command unrecognized

**TURN**

* 250 Requested mail action okay, completed
* 502 Command not implemented
* 500 Syntax error, command unrecognized
* 503 Bad sequence of commands

</details>
