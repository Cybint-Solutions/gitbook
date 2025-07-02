# Logs

### Introduction

Campaign logging in LUCY provides detailed records of various activities within your campaigns. There are three main types of logs: Supervisor Log, Message Log, and Error Log. Each log type serves a distinct purpose in managing and auditing your campaign activities.

### Supervisor Log

The approval workflow is based on the 4-eyes principle for creating a new campaign. A campaign administrator creates a phishing or e-learning campaign but can only start it after a different user (the supervisor) reviews and approves it. If the supervisor rejects the campaign, a ticket with an expiry date will be created for the administrator.

#### Configuration

{% hint style="info" %}
Navigate to **Campaign -> Logs -> Supervision Log**
{% endhint %}

**Create Users**:

* [Create a user](../../users/administrative-users.md) with the "user" role. No special rights are needed.
* [Create a supervisor](../../users/administrative-users.md) with the "supervisor" role and assign the "user" as a supervised user.

**Assign Users to Campaign**:

* [Add both "user" and "supervisor" to the same campaign.](advanced-settings/user-settings.md)
* The "user" should have at least "start/stop campaign" permissions. If the user needs to configure the campaign, they also need configuration access.
* The "supervisor" should have full permissions for the campaign.

**Campaign Launch Process**:

When the campaign admin logs in under their "user" role and starts the campaign, it will be put on hold until the supervisor approves the launch. A new entry will be created in the "Supervision Log". The campaign dashboard will show a small turning wheel indicating that the campaign is waiting for approval.

**Supervisor Approval**:

* The supervisor logs in under their "supervisor" role and navigates to the same campaign. They can either reject or approve the campaign by clicking the corresponding buttons.
* If the supervisor rejects the campaign, they can create a ticket with an end date and severity, communicating the required changes.
* The campaign admin, with their "user" role, will see the desired changes in the supervision log.

**Repeat Until Approval**:

* Once the changes are made, the above step can be repeated until the supervisor approves the campaign.

This structured approval workflow ensures that campaigns are thoroughly reviewed before launch, maintaining high standards of security and oversight.

***

### Message Log

The Message Log in LUCY is a comprehensive record of all messages that have been successfully transmitted by the system. This feature is essential for tracking the delivery and status of emails sent as part of your phishing or awareness campaigns.

#### Configuration

{% hint style="info" %}
Navigate to **Campaign -> Logs -> Message Log**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (577).png" alt=""><figcaption></figcaption></figure>

**Purpose of the Message Log**

* **Track Delivery:** Ensure that all intended recipients have received the campaign messages..
* **Audit Trail:** Maintain a detailed log for auditing and compliance purposes.

**Message Details**

* **Recipient Email:** The email address of the recipient.
* **Time Sent:** The exact time the email was sent.

***

### Error Log

The Error Log records any issues or errors that occur during the campaign execution. This log is crucial for troubleshooting and resolving any problems that may arise.

**Configuration**:

{% hint style="info" %}
Navigate to **Campaign -> Logs -> Error Log**
{% endhint %}

**Purpose of the Error Log**:

* **Identify Issues**: Detect any errors in the campaign execution process.
* **Resolve Problems**: Provide detailed information to help resolve issues promptly.
