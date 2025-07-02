# Summary

### Campaign **Dashboard Overview**

The Campaign Dashboard provides a comprehensive overview of campaign statistics and actions, offering administrators immediate access to essential information and metrics.&#x20;

### **Status and Controls**

<figure><img src="../../../../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

At the top, the dashboard displays the current status of the campaign (e.g., Running), the total running time, and the campaign creator's details. Administrators have the option to perform actions or export data from this area.



<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Actions</strong></td><td></td><td>Global campaign actions to reset all statistics, generate an <a href="reports.md">exucitive report</a> and saving the <a href="../../../templates/campaign-templates.md">campaign as a template</a>.</td></tr><tr><td><strong>Export</strong></td><td></td><td><a href="exports.md">Exports</a> encompass all recipient statistics, offering an in-depth look at campaign-related interactions and behaviors.</td></tr><tr><td><strong>Start</strong></td><td></td><td>This feature allows you to start, stop, restart, resume, or conduct a trial execution of your campaign. All relevant <a href="../campaign-checks.md">campaign checks</a> are done prior to the launch of the cmapaign. </td></tr></tbody></table>

### **Campaign Overview**

The campaign dashboard dynamically adjusts to display relevant metrics for Attack only, combined Attack and Awareness, or exclusive Awareness campaigns, reflecting the specific statistics related to the campaign type.

{% tabs %}
{% tab title="Attack Only" %}
<figure><img src="../../../../.gitbook/assets/image (125).png" alt="" width="563"><figcaption></figcaption></figure>

**Attack Overview Section**:

* **Sent**: Shows the total number of emails sent and the percentage delivered.
* **Clicked**: Displays the count and percentage of recipients who clicked on a link in the email.
* **Successful Attacks**: Indicates the number and percentage of recipients who fell for the phishing attack.
* **Vulnerable Victims**: Reflects the count and percentage of recipients who are considered to have vulnerabilities for their browser version.
* **Errors**: Notes any errors that occurred during the Attack email distribution.

**Click and Report Action Summary**:

* **Total Emails**: The total number of emails involved in the campaign.
* **Clicked and Reported**: The number of recipients who both clicked the phishing link and reported the email.
* **No Click and Reported**: The number of recipients who did not click on any link but reported the email.
* **Message Bounced**: Indicates how many emails were not delivered successfully.
* **Clicked and Not Reported**: The number of recipients who clicked but did not report the phishing email.
* **No Click and No Report**: The number of recipients who neither clicked on the phishing link nor reported the email.

**Timeline Section**:

<figure><img src="../../../../.gitbook/assets/image (121).png" alt=""><figcaption></figcaption></figure>

* **Campaign Creation**: The exact date and time when the campaign was created.
* **Scenario Added**: Shows when a scenario was added to the campaign, with date and time.
* **Awareness Added**: Indicates the date and time when awareness training content was added to the campaign.
* **Recipient Group Added**: Displays the addition of recipient groups to the campaign, along with the timestamp.
* **Campaign Sent**: Reflects when the campaign was initiated, with the corresponding date and time.
{% endtab %}

{% tab title="Awareness Only" %}
<figure><img src="../../../../.gitbook/assets/image (122).png" alt="" width="563"><figcaption></figcaption></figure>

**TRAINING OVERVIEW**:

* **Sent**: Tracks the number of training emails sent and their delivery success rate.
* **Clicked**: Monitors recipient engagement by recording clicks on the link in the training email.
* **Errors**: Notes any errors that occurred during the training email distribution.
* **Template Feedback Score**: Reflects recipient feedback on the training content, this allows the administrator to short list training or make modifications based on recipient feedback.

{% hint style="info" %}
Template feedback can be disabled in [Advanced Settings](../../../settings/advanced-system-settings/advanced-settings.md#template-rating)
{% endhint %}

**AWARENESS**:

<figure><img src="../../../../.gitbook/assets/image (118).png" alt="" width="465"><figcaption></figcaption></figure>

This section features a concentric circle graph indicating the percentage of training completion, emails opened, and training content sent.

* **Training Score**: The average score recipients achieved in the awareness training.
* **Opened**: The percentage of recipients who opened the awareness emails.
* **Sent**: The delivery rate of the awareness emails to recipients.

**CLICK AND REPORT ACTION SUMMARY**:

<figure><img src="../../../../.gitbook/assets/image (119).png" alt="" width="563"><figcaption></figcaption></figure>

* **Total Emails**: The total count of emails distributed in the campaign.
* **Clicked and Reported**: Number of recipients who clicked on the training content and reported it.
* **No Click and Reported**: Tracks recipients who did not click but still reported the email.
* **Message Bounced**: Counts undelivered emails that bounced back.
* **Clicked and Not Reported**: Indicates how many recipients clicked on the content but did not report it.
* **No Click and No Report**: Notes recipients who neither clicked on the link nor reported the email.

**TIMELINE**:

<figure><img src="../../../../.gitbook/assets/image (120).png" alt="" width="563"><figcaption></figcaption></figure>

* Displays a chronological list of key campaign actions including when the campaign was created, scenarios added, awareness content added, recipient groups added, and when the campaign was sent out.
* Each entry in the timeline includes the date, time, and user responsible for the action.
{% endtab %}

{% tab title="Attack and Awareness" %}
<figure><img src="../../../../.gitbook/assets/image (367).png" alt="" width="461"><figcaption></figcaption></figure>

**ATTACK OVERVIEW**:

* **Sent**: Displays the number and percentage of emails sent in the campaign.
* **Clicked**: Shows the number and percentage of recipients who clicked on the email link.
* **Successful Attacks**: Indicates the number and percentage of recipients who completed the desired action in the attack.
* **Vulnerable Victims**: Reflects the number and percentage of recipients identified as susceptible.
* **Errors**: Records the number and percentage of any errors encountered during the attack phase.

**AWARENESS**:

<figure><img src="../../../../.gitbook/assets/image (117).png" alt="" width="465"><figcaption></figcaption></figure>

* The circular graph depicts the percentage of awareness emails sent, opened, and the training score.
* **Training Score**: Percentage of how well recipients performed in awareness training.
* **Opened**: The percentage of recipients who opened the awareness emails.
* **Sent**: The success rate of awareness emails reaching the recipients.



**CLICK AND REPORT ACTION SUMMARY**:

<figure><img src="../../../../.gitbook/assets/image (368).png" alt="" width="563"><figcaption></figcaption></figure>

* **Total Emails**: The count of emails involved in the campaign.
* **Clicked and Reported**: The number of recipients who both clicked on the link and reported the email.
* **Clicked and Not Reported**: Tracks recipients who clicked the link but did not report the email.
* **No Click and No Report**: Counts recipients who neither clicked on any links nor reported the email.
* **Message Bounced**: The number of emails that failed to deliver.

**TIMELINE**:

<figure><img src="../../../../.gitbook/assets/image (115).png" alt="" width="563"><figcaption></figcaption></figure>

* A chronological display of campaign milestones such as campaign creation, scenario addition, awareness content addition, recipient group inclusion, and campaign launch, complete with timestamps and responsible user IDs.
{% endtab %}
{% endtabs %}
