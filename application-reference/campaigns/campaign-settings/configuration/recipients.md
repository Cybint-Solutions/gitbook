# Recipients

The Recipients tab allows you to add the desired [Recipient Groups](../../../users/recipient-groups.md) to your campaign.

The recipient group consists of users who will receive the attack simulation or awareness content. You can create multiple groups for a single campaign. Recipients can belong to multiple groups, and you can set up an unlimited number of groups.

{% hint style="info" %}
Navigate to Main Settings **> Recipients**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

***

## Add Group

Select **Add Group** to bind your first recipient group to the campaign, then select a group from the list or select **New Group** to create a group on-the-fly.

<figure><img src="../../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

***

## Group Settings

<figure><img src="../../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

#### Group

The currently selected recipient group. Use this list to change groups.

#### Search

Search the current group by name, email, or phone, or by the staff, location, division, and comment columns.

#### Language

Set a default language for the group. This language is used as a fallback for any recipient that does not have a language set for them within the group.

## Recipient List

By default, **no recipients are selected**. Enable the checkbox next to a recipient to add them, or enable the **Select All** checkbox to add them all at once.

<figure><img src="../../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

***

## Mapping

You can configure which email(s) the recipients will receive. Usually it is not necessary to change this setting.

<figure><img src="../../../../.gitbook/assets/image (574).png" alt="" width="538"><figcaption></figcaption></figure>

#### Campaign + Awareness

The recipients will receive both the attack and the training content (assuming they fail the attack).

#### Campaign

The recipients will receive only the attack simulation.

#### Awareness

The recipients will receive only the training content.

***

## Scenarios

The scenario association controls which group receives which attack simulation and/or training content. If you select two scenarios for a group, each user in that group will receive two emails (one from each scenario).

<figure><img src="../../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

#### Distribute Users

If enabled, this setting will randomly assign users to the selected scenarios, ensuring each user receives a unique attack and no one gets the same scenario twice.

{% hint style="info" %}
For more detailed control over distribution, create a [schedule rule](schedule/).
{% endhint %}

#### Suppress Duplicate Recipients

{% hint style="info" %}
This option is found in the **Settings** tab.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

If enabled, Lucy will remove duplicate recipients across all the recipients groups in the campaign, leaving only one copy of the recipient in the first group in the list.

This will **not** delete the recipient from the group globally, only in the campaign.

If you disable this setting after enabling it, deleted recipients will **not** be re-added.
