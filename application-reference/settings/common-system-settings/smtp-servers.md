# SMTP Servers

## **Introduction**

Lucy provides a dependable method for delivering emails during security awareness training campaigns by utilizing a known SMTP relay. This feature allows organizations to route emails through their own SMTP server, ensuring high deliverability and maintaining trust as emails are sent from a recognized company domain.

**Key Considerations for Using SMTP with Lucy:**

* **Trust and Deliverability:** By using the company’s SMTP server, Lucy helps overcome common deliverability issues associated with external email services and enhances trust, as the emails are sent from familiar domains.
* **Caution with Simulated Attacks:** While it is possible to send simulated phishing attacks through the SMTP server, it is advisable to use a controlled, dedicated SMTP server for such activities. This prevents any risks associated with blacklisting, which could disrupt daily operations if the same server is used for regular business communications.
* **Configuration Requirements:** Ensure that emails sent through the SMTP option originate strictly from the email address associated with the SMTP server. This alignment is crucial for the success of email delivery in your campaigns.

***

## **Configuration**

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> SMTP Servers**
{% endhint %}

Select **"Add Server"**

<figure><img src="../../../.gitbook/assets/image (198).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Lucy enables administrators to set up multiple SMTP server configurations, making it an ideal solution for managing email delivery across various customers in a multi-tenant environment.
{% endhint %}

Next, you will define the SMTP Mail Server parameters:

{% tabs %}
{% tab title="Name" %}
The Name of this specific SMTP Server.\
This name will appear elsewhere in Lucy when selecting the server.
{% endtab %}

{% tab title="Client" %}
This feature supports data segregation, allowing you to make the SMTP server available to either all clients or restrict it to a specific client on your list.
{% endtab %}

{% tab title="Host" %}
This is the SMTP Host for your mail server; for example Microsoft Office is _**smtp.office365.com**_ or NameCheap is _**mail.privateemail.com**_
{% endtab %}

{% tab title="Port" %}
This depends on your mail server, generally speaking, the most common ports for SMTP are:

**25**: Traditionally used for SMTP to transfer emails between servers. However, due to its vulnerability to spam and misuse, many ISPs block it for outgoing mail.

**587**: Recommended for submitting emails to be sent by a mail server, supporting encryption (STARTTLS). It's the preferred port for client-to-server communication.

**465**: Initially used for SMTPS (SMTP over SSL), it was deprecated but later revived for SMTP submissions over SSL encryption directly. Some servers still support this port for secure submissions.
{% endtab %}

{% tab title="Encryption" %}
#### SSL/TLS

* **Usage**: When an SMTP server uses SSL/TLS, it usually listens on a dedicated port (default is port 465) for secure connections.
* **Behavior**: As soon as the connection is established, the server begins the SSL/TLS handshake to negotiate the encryption before any SMTP communication starts.
* **Security**: The entire session is encrypted, meaning that no part of the email (including headers, body, or attachments) is sent in plain text.
* **Client Expectation**: The email client must be configured explicitly to connect using SSL/TLS and to use the appropriate port.

#### STARTTLS

* **Usage**: STARTTLS is an SMTP command that tells the server to switch from an unencrypted connection to a secure connection using SSL/TLS encryption.
* **Behavior**: The SMTP server starts by listening on a non-encrypted port (usually port 25 or 587), and after the initial plaintext communication, either the client or server can issue the STARTTLS command to upgrade to a secure connection.
* **Security**: The session starts unencrypted, but after the STARTTLS command is issued and the subsequent handshake, the communication is encrypted.
* **Client Expectation**: The email client can begin communication on a standard SMTP port and then switch to an encrypted connection without needing to reconnect.
{% endtab %}

{% tab title="Authentication" %}
Choose "OAuth2" (e.g., Azure) if your mail server supports this authorization framework. Alternatively, you can select "Password authentication," which requires the administrative username and password for authentication.
{% endtab %}
{% endtabs %}

For example, I would like to authenticate to my NameCheap SMTP server. The Hostname for all NameCheap SMTP servers is - **mail.privateemail.com**; the port is **587**; and I will be authenticating with my administrative username and password:

<figure><img src="../../../.gitbook/assets/image (521).png" alt=""><figcaption></figcaption></figure>

Once completed, click **Save** to commit your SMTP server settings.

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
