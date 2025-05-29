# Incident Autoresponder

{% hint style="info" %}
Navigate to **Settings > Submitted Email Settings > Autoresponder**
{% endhint %}

### Introduction

The Incident Autoresponder feature in LUCY allows administrators to automatically respond to emails submitted via the reporting plugin. The response can include the risk score calculated by LUCY and you can define separate responses for real incidents and simulations.

<figure><img src="../../../.gitbook/assets/image (720).png" alt=""><figcaption><p><strong>%score%</strong> - The email's calculated <a href="https://app.gitbook.com/o/gJ3JHRuHpkD1JGxoFnyo/s/VYPsDfg76rUuy4DWfSsJ/~/changes/568/platform-reference/navigation-bar/settings/submitted-email-settings/scoring">risk score</a>.</p></figcaption></figure>

***

### Autoresponse Detection

{% hint style="info" %}
Navigate to **Settings > Submitted Email Settings > Auto Response Detection**
{% endhint %}

Sometimes the reply that LUCY receives is not a report but an out-of-office message or some other automatic reply. In order to avoid a situation where two autoresponders are talking to each other, you can define various phrases that LUCY can check for in its messages to determine if the response came from an autoresponder.

<figure><img src="../../../.gitbook/assets/image (721).png" alt=""><figcaption><p>You can create a list of phrases by separating each phrase with a comma.</p></figcaption></figure>

**Timeout** - Any reply within this number of seconds will be considered an autoresponse and LUCY will treat it accordingly.

**Out of Office Delay** - Time (in days) before LUCY re-sends the message that triggered the autoresponse.

**Out of Office Phrases** - Provide a list of text patterns here and LUCY will scan incoming messages for these phrases. If any are found, LUCY will treat the message as an autoresponse.

**Bounced Phrases** - Similar to Out of Office, any message that contains a phrase from this list will be treated as a bounced message. LUCY will attempt to re-send bounced messages until the message returns a different status.
