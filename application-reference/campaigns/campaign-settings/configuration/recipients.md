# Recipients

### Introduction

The Recipients tab allows you to add the desired [Recipient Groups](../../../users/recipient-groups.md) to your campaign.&#x20;

Every campaign needs a recipient group to function. The recipient group consists of users who will receive the attack simulation or awareness content. You can create multiple groups for a single campaign. Groups can be used within LUCY to target users with specific phishing or training campaigns. Many organizations start by grouping users by department, location (if you have multiple office locations), or even domains (if there are multiple domains). Recipients can belong to multiple groups, and you can set up an unlimited number of groups.

{% hint style="info" %}
Navigate to **Campaign -> Configuration-> Recipients**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (505).png" alt=""><figcaption></figcaption></figure>

***

### Add Group

Select the "Add Group" button to bind your first recipient group to the campaign.

<figure><img src="../../../../.gitbook/assets/image (507).png" alt="" width="466"><figcaption></figcaption></figure>

Select the Group to be bound to the campaign from the drop-down menu.

<figure><img src="../../../../.gitbook/assets/image (508).png" alt=""><figcaption></figcaption></figure>

***

### Group Configuration:

{% tabs %}
{% tab title="Group" %}
The name of the pre-selected group. You can use this drop-down to select an alternative group.
{% endtab %}

{% tab title="Search" %}
Search by recipient name, email, phone, staff type, location, division, or comment.

{% hint style="info" %}
The search filter is advantageous for finding specific individuals within the group to be bound to the campaign.
{% endhint %}

For example, only add the recipients in "Management" from this group to the campaign.

<figure><img src="../../../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Language" %}
Save the default language for the Group. This language will only be used if the recipient does not have a language defined in their [Recipient Group](../../../users/recipient-groups.md).
{% endtab %}
{% endtabs %}

<figure><img src="../../../../.gitbook/assets/image (573).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
By default, no recipients will be selected. Ensure to "Select All" or select the filtered results before saving.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (572).png" alt=""><figcaption></figcaption></figure>

***

### Mapping:

The default mapping is "campaign and awareness," meaning the user group receives both the phishing simulation and e-learning content if configured. You can limit the mapping to "awareness only" or "campaign only." For example, "campaign only" means the group gets only the attack simulation, with no e-learning

<figure><img src="../../../../.gitbook/assets/image (574).png" alt="" width="538"><figcaption></figcaption></figure>

***

### Scenarios:

The scenario association controls which group receives which attack scenario. If you select two scenarios for a specific group, each user in that group will receive two emails (one from each scenario).&#x20;

To avoid sending multiple emails to users, enable the "Distribute users over selected scenarios" checkbox. This will randomly assign users to the selected scenarios, ensuring each user receives a unique attack and no one gets the same scenario twice.&#x20;

<figure><img src="../../../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
For more detailed control over distribution, create a [schedule rule](schedule/).
{% endhint %}

***

### Language Considerations <a href="#language_considerations" id="language_considerations"></a>

LUCY can handle multiple languages within the same recipient group. There is no need to define different groups for each language.

***
