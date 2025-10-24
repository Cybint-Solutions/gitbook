# Starting a Campaign

## How to Start a Campaign

Once you have finished configuring the campaign, select **START** to initiate the campaign checks.

<figure><img src="../../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

### Start Options

#### Start

This option initiates the attack or awareness campaign. After pressing "START," LUCY will send emails to your recipient group(s).

#### Restart

This option resets the campaign statistics and resends the emails to the recipient group.&#x20;

{% hint style="danger" %}
Note that all data will be lost and cannot be restored. Use "START" to resume an existing campaign without losing data.
{% endhint %}

#### Resume

Use this option for a campaign that has been started and stopped before. Emails won't be resent; only the webpage will restart, and the same distributed links will become available again. To resend all the emails, use the "RESTART" button.&#x20;

If new scenarios are added to an existing campaign and you click "START," only the emails for the new scenarios will be sent, and the initial scenario will resume.&#x20;

{% hint style="info" %}
During the time a campaign is stopped, the landing pages will be inaccessible, displaying a customizable error message. Once resumed, all links will work again.
{% endhint %}

#### Test Run

This option runs a live campaign in test mode using the admin user's email address for the test run. After the test run is stopped, all test data is removed from the system.

***

## Campaign Checks

{% hint style="success" %}
Always perform a test run with a few users before launching a campaign.&#x20;
{% endhint %}

Lucy runs various checks before starting the campaign to ensure the configuration works as expected. The test may take a few minutes. Examples of these tests include:

* **DNS**: Query SPF entry, query MX entry
* **SMTP**: Send a test email to a random Mailinator account with an anonymous hash value that is deleted via API after the test
* **HTTP/S**: Make an HTTP/HTTPS GET request to the configured IP/DNS name to verify if the URL is reachable from the internet

<figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Lucy will attempt to connect to the internet during these tests.
{% endhint %}

### Errors and Warnings

If any of the checks identify a critical error, the check will highlight in red and the campaign will not be allowed to start. Warnings are highlighted in yellow. For any error or warning, select the text of the campaign check to view more information about the issue.

<figure><img src="../../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

***

## How do I Edit a Running Campaign?

Campaigns in LUCY are dynamic. If you need to make changes to a landing page, you can do so while the campaign is running. All recipient links will remain valid, and the content will be updated for all recipients accessing the links.\
\
If you select **STOP**, the awareness or phishing website will not be reachable while the campaign is stopped. When you **RESUME** the campaign again, LUCY will resume it from where it was stopped, and all statistics will remain the same.
