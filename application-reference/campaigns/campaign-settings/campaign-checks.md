# Campaign Checks

#### How to Start a Campaign Test

Once you have finished configuring the campaign, press "START" to initiate the website and send out the emails after a quick check.

<figure><img src="../../../.gitbook/assets/image (438).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Start" %}
This option initiates the attack or awareness campaign. After pressing "START," LUCY will send emails to your recipient group(s).
{% endtab %}

{% tab title="Restart" %}
This option resets the campaign statistics and resends the emails to the recipient group.&#x20;

{% hint style="danger" %}
Note that all data will be lost and cannot be restored. Use "START" to resume an existing campaign without losing data.
{% endhint %}
{% endtab %}

{% tab title="Resume" %}
Use this option for a campaign that has been started and stopped before. Emails won't be resent; only the webpage will restart, and the same distributed links will become available again. To resend all the emails, use the "RESTART" button.&#x20;

If new scenarios are added to an existing campaign and you click "START," only the emails for the new scenarios will be sent, and the initial scenario will resume.&#x20;

{% hint style="info" %}
During the time a campaign is stopped, the landing pages will be inaccessible, displaying a customizable error message. Once resumed, all links will work again.
{% endhint %}
{% endtab %}

{% tab title="Test Run" %}
This option runs a live campaign in test mode using the admin user's email address for the test run. After the test run is stopped, all test data is removed from the system.
{% endtab %}
{% endtabs %}

### How do I Edit a Running Campaign?

Campaigns in LUCY are dynamic. If you need to make changes to a landing page, you can do so while the campaign is running. All recipient links will remain valid, and the content will be updated for all recipients accessing the links.\
\
If you press "STOP," the awareness or phishing website will not be reachable while the campaign is stopped. When you "RESUME" the campaign again, LUCY will resume it from where it was stopped, and all statistics will remain the same.

### Checks Performed When Starting a Campaign

LUCY runs various checks before starting the campaign to ensure the configuration works as expected. The test may take a few minutes.&#x20;

Always perform a test run with a few users before launching a company-wide attack. LUCY performs tests such as verifying MX settings, looking up the host from the internet, and sending a test email. Examples of these tests include:

* **DNS**: Query SPF entry, query MX entry
* **SMTP**: Send a test email to a random Mailinator account with an anonymous hash value that is deleted via API after the test
* **HTTP/S**: Make an HTTP/HTTPS GET request to the configured IP/DNS name to verify if the URL is reachable from the internet

<figure><img src="../../../.gitbook/assets/image (436).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
LUCY connects to the internet during these tests, but no campaign settings data is transferred. If a test fails, you can click on the corresponding test to see details. Even if tests fail, you can start the campaign by pressing the "Start Anyway" button.
{% endhint %}
