# Risk Score

## Introduction

Each [end user](end-users.md) has their own risk score based on the number of attacks they've been sent and the number of attacks they've failed. This reputation level can be leveraged in campaigns to send recipients specific attacks and trainings based on their risk score.

The formula for determining risk score is:

```
(1 - number of attacks failed / number of attacks sent) x 100
```

This number is then displayed as a percentage in the user's portal along with their reputation level:

<figure><img src="../../.gitbook/assets/image (939).png" alt=""><figcaption></figcaption></figure>

***

## Custom ranges

Reputation level thresholds can be set by Lucy administrators under **Users > Risk Score**:

<figure><img src="../../.gitbook/assets/image (980).png" alt=""><figcaption></figcaption></figure>

The levels shown above are the default configuration. Administrators can add or remove levels as desired and define the rating and minimum number of attacks necessary to reach that level.&#x20;

{% hint style="success" %}
Up to 10 ranges can be defined.
{% endhint %}

You may also define ranges on a per-client basis:

<figure><img src="../../.gitbook/assets/image (981).png" alt=""><figcaption></figcaption></figure>
