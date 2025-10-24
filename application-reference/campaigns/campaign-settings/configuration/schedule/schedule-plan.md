# Schedule Plan

## Details

The schedule plan is the output of all rules configured for your campaign.&#x20;

<figure><img src="../../../../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

#### Time

When the email is scheduled to be sent.

#### Email

The Email address of the recipient (not supported for anonymous campaigns).

#### Scenario

The specific attack or awareness scenario associated with the email.

#### Processed

The status email; pending, sent, or error.

***

## Rebuild Plan

This button is necessary if any modifications are made to an existing rule. Rebuilding the schedule plan ensures that all changes are reflected accurately, updating the schedule to align with the new configurations.

{% hint style="info" %}
Rebuilding a plan will not send emails to already processed recipients, ensuring that modifications can be made to a rule without compromising the integrity of the campaign.
{% endhint %}

***

## FAQ

<details>

<summary>What is the best practice for adding rules and validating the Schedule Plan?</summary>

Start with a controlled or small recipient group to familiarize yourself with the rule outputs. Add only one rule at a time, then validate the Plan to ensure the emails will be sent according to your goals.&#x20;

Once you are confident, simply adjust the rule by adding all additional recipient groups and rebuild the scheduling plan. This approach allows for careful testing and refinement before scaling up to the full campaign.

</details>

<details>

<summary>No emails are sent after the Schedule Rule is saved</summary>

* Did you start the campaign after setting the scheduler? Please note that configuring the scheduler alone won't initiate email delivery. The campaign needs to be explicitly started to begin sending emails. Ensure that you have activated the campaign after setting up the scheduler to initiate the mail delivery.

- Did you start the campaign after the Schedule Rule Start time? Schedule Rules can not be initiated if the start time is in the past.

* If you are using the scheduler to trigger smishing campaigns, make sure your license has enough credits and is not outdated. You can check your license status and credits in the [License tab](../../../../account-settings/).

- Make sure your Lucy server [**time** & **time zone**](../../../../settings/advanced-system-settings/advanced-settings.md#date-time-settings) are both correct.

* Apply the latest patches by [updating your Lucy server to the latest version](../../../../support/update.md).

</details>
