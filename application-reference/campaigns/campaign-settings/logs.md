# Logs

Campaign logging in Lucy provides detailed records of various activities within your campaigns. There are three main types of logs: Supervisor Log, Message Log, and Error Log.

## Supervisor Log

The approval workflow is based on the 4-eyes principle for creating a new campaign. A campaign administrator creates a phishing or e-learning campaign but can only start it after a different user (the supervisor) reviews and approves it. If the supervisor rejects the campaign, a ticket with an expiry date will be created for the administrator.

#### **Campaign Launch Process**

When the campaign admin logs in under their "user" role and starts the campaign, it will be put on hold until the supervisor approves the launch. A new entry will be created in the "Supervision Log". The campaign dashboard will show a small turning wheel indicating that the campaign is waiting for approval.

***

## Message Log

The Message Log is a record of all messages that have been successfully transmitted by the campaign. The log contains the timestamp, recipient info, and message type of the email.

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

***

## Error Log

The Error Log records any issues or errors that occur during the campaign execution. This log is crucial for troubleshooting and resolving any problems that may arise.
