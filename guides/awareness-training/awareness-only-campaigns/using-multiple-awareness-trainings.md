# Using Multiple Awareness Trainings

## Use Cases

* You want to send specific training content based on the recipient's department, skill level, or other natural grouping, and these recipients are already grouped accordingly (e.g. a recipient group for each department has already been created).
* You want to send specific training content to each recipient based on their [risk level](../../../application-screens-reference/campaigns/campaign-settings/configuration/awareness-settings.md#awareness-template-base-settings), and these recipients are all in the same group.

***

## Using Awareness Groups

In this method we will add multiple recipient groups to a campaign and send them all different trainings by binding each recipient group to an awareness group.

### Add Trainings

Add each awareness training to the campaign:

<figure><img src="../../../.gitbook/assets/image (896).png" alt=""><figcaption></figcaption></figure>

### Create Awareness Groups

Select **Awareness Groups** from the campaign configuration menu and create one group per training:

<figure><img src="../../../.gitbook/assets/image (897).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
By default a group called **Default Group** already exists. You cannot delete the only awareness group in a campaign, so you must create at least one other group first and then delete the default.
{% endhint %}

### Assign Awareness Groups

Return to the **Awareness Settings** and select a training. Go to the **Awareness Groups** tab and assign the awareness group you created for that training:

<figure><img src="../../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
To assign an awareness group select it from the menu and click **Bind**.
{% endhint %}

Repeat this step for every training scenario, until each one is bound to a different group:

<figure><img src="../../../.gitbook/assets/image (899).png" alt=""><figcaption></figcaption></figure>

### Add Recipients

Go the **Recipients** page and select **Add Group**. Select your recipients and at the bottom of the page select an awareness group to bind it to those recipients:

<figure><img src="../../../.gitbook/assets/image (901).png" alt=""><figcaption></figcaption></figure>

**Save** to continue and repeat this step for each awareness group.

<figure><img src="../../../.gitbook/assets/image (903).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You can use the same group multiple times and bind recipients to multiple awareness groups. If a recipient is bound to multiple awareness groups they will receive each training bound to them.
{% endhint %}

***

## Using Risk Levels

In this method we will add one recipient group to a campaign and send the users in that group different trainings depending on their [reputation level](../../../application-screens-reference/users/risk-score.md) (also called risk score or risk level).

### Add Trainings

Add each awareness training to the campaign:

<figure><img src="../../../.gitbook/assets/image (900).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Note the auto-incrementing **Risk Level** for each training.\
You can adjust these levels by using the `+` and `-` buttons.
{% endhint %}

{% hint style="warning" %}
Trainings may not have the same Risk Level.
{% endhint %}

#### Rename the Awareness Group

By default, the lone awareness group is named after the first training that was added. For clarity's sake you should rename the group to something like "Default" or another descriptive name. Whatever you name the Awareness Group, just make sure you have only one - we will use this group in the next step when we add recipients.

### Add Recipients

Add all of your recipients and select the lone awareness group under **Scenarios**.

<figure><img src="../../../.gitbook/assets/image (908).png" alt=""><figcaption></figcaption></figure>

Once complete, your awareness settings should look like this:

<figure><img src="../../../.gitbook/assets/image (909).png" alt=""><figcaption></figcaption></figure>





