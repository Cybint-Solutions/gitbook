# Using Awareness Groups

## Use Cases

* You want to send specific training content based on the recipient's department, skill level, or other natural grouping, and these recipients are already grouped accordingly (e.g. a recipient group for each department has already been created).
* You want to send specific training content to each recipient based on their [risk level](../../../application-reference/campaigns/campaign-settings/main-settings/awareness-education/#awareness-template-base-settings), and these recipients are all in the same group.

***

## Using Awareness Groups

In this method we will add multiple recipient groups to a campaign and send them all different trainings by binding each recipient group to an awareness group.

### Add Trainings

Add each awareness training to the campaign:

<figure><img src="../../../.gitbook/assets/image (1046).png" alt=""><figcaption></figcaption></figure>

### Create Awareness Groups

Select **Awareness Groups** and create a group for each Awareness training:

<figure><img src="../../../.gitbook/assets/image (1047).png" alt=""><figcaption></figcaption></figure>

To create a new Awareness Group type the name into the text box at the bottom and select **Add**.

<figure><img src="../../../.gitbook/assets/image (1048).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
By default, one group already exists named after the first awareness added to the campaign.\
You can rename this group.

Every Awareness campaign requires at least one Awareness group.
{% endhint %}

### Assign Awareness Groups

To assign an Awareness Group, select one of the Awareness scenarios and go to the **Awareness Groups** tab:

<figure><img src="../../../.gitbook/assets/image (1049).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
To assign an awareness group select it from the menu and click **Bind**.
{% endhint %}

Repeat this step for every Awareness scenario until each one is bound to a different group:

<figure><img src="../../../.gitbook/assets/image (1050).png" alt=""><figcaption></figcaption></figure>

### Add Recipients

Go the **Recipients** page and select **Add Group**. Select your recipients and at the bottom of the page select an awareness group to bind it to those recipients:

<figure><img src="../../../.gitbook/assets/image (1051).png" alt=""><figcaption></figcaption></figure>

Select **Save** to continue, and repeat this step for each awareness group.

{% hint style="info" %}
You can use the same group multiple times and bind recipients to multiple awareness groups. If a recipient is bound to multiple awareness groups they will receive each training bound to them.
{% endhint %}

***

## Using Risk Levels

In this method we will add one recipient group to a campaign and send the users in that group different trainings depending on their [reputation level](../../../application-reference/users/risk-score.md) (also called risk score or risk level).

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





