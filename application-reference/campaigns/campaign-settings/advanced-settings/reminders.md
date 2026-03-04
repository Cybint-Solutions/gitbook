# Reminders

LUCY allows administrators to configure reminders within a campaign to ensure recipients engage with the content. This feature is particularly useful for reminding users who have not interacted with the campaign as expected.

{% hint style="info" %}
Starting in Lucy version 5.1, campaign reminder settings are included in [campaign templates.](../../../templates/campaign-templates.md)
{% endhint %}

***

## Configuration

Reminder emails can be sent once or repetetively. You can configure a custom reminder message (ideal for attacks) or simply resend the original email (ideal for awareness).

#### Single Message

Select this option to send one reminder email N days after the original email.

#### Repetetive Message

Select this option to send a reminder email every N days after the original email.

#### Use Scenario or Awareness Email

Select this option to resend the original template email, rather than a custom reminder message.

{% hint style="success" %}
If you are using a custom reminder email, select **Edit Template** to customize it.
{% endhint %}

## Awareness Reminders

{% hint style="info" %}
Navitgate to **Awareness Education > Reminders**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
In order to use the **Send Immediately** button you must save the reminder settings first.
{% endhint %}

### **Remind Users Who Did Not Start a Training**

Enable this option to send a reminder to users who did not start the training after receiving the awareness email. Lucy will send a reminder to anyone who did not click the training link.

### **Remind Users Who Did Not Finish a Training**

Enable this option to send a reminder to users who started but did not finish the training. Lucy will send a reminder to anyone who is not trained in the statistics.

## Attack Simulation Reminders

{% hint style="info" %}
Navigate to **Attack Simulation > Reminders**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
In order to use the **Send Immediately** button you must save the reminder settings first.
{% endhint %}

### **Remind Users Who Did Not Click a Phishing Scenario Link**

Enable this option to send a reminder to users who did not click on the link in the phishing email.

***

## Reminder Template Customization

To customize a reminder email, select **Edit Template** for the desired reminder type:

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Select your language and configure the reminder email for the chosen language.

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Reminder templates are not automatically translated; each adaptation needs to be copied and translated into the relevant language.
{% endhint %}

Click **Save** to commit your reminder template.

<details>

<summary>Reminder Email Variables</summary>

You may use the following variables in the template:

* `%link%` — Unique page URL for the recipient.
* `%link-awareness%` — Link to the awareness website. You should configure and enable the awareness website in campaign settings for this feature to work.
* `%name%` — Recipient full name.
* `%firstname%` — Recipient first name.
* `%lastname%` — Recipient last name.
* `%email%` — Recipient email address.
* `%division%`, `%location%`, `%staff-type%`, `%comment%` — Recipient-related information.
* `%gender("MALE ADDRESSING", "FEMALE ADDRESSING", "NO GENDER")%` — Recipient gender.
* `%subject%` — Subject of the phishing email.
* `%sender%` — Sender name of the phishing email.
* `%sender-email%` — Email address of the phishing email.
* `%time(FORMAT, OFFSET, ZONE)%` — Time-based variables.
  * **FORMAT**: Date/time format.
  * **OFFSET**: Date/time offset in minutes, can be negative (e.g., "-60" means 60 minutes prior to email submission time, "20160" means 20160 minutes = 14 days).
  * **ZONE**: Time zone name (e.g., US/Central).

Examples:

* `%time("l, H:i", "0", "Europe/Zurich")%` — Outputs "Monday, 09:20" (exact time of email submission in Europe/Zurich zone).
* `%time("Y/m/d H:i:s", "60")%` — Outputs "2016/12/12 10:20:30" (1 hour ahead of email submission time).

Please note that these variables are not available in CSS and JavaScript files.

</details>
