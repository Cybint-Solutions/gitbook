# SSH Password

### Introduction

The "phishing" account on LUCY serves a specific function: managing file permissions and initiating the setup program upon SSH login. It's not intended for regular SSH use; instead, it provides automated setup tasks with the necessary privileges. Removing or altering the "phishing" account is not recommended, as it is vital for LUCY's proper operation.\
\
**Objective**: Configure inbound SSH access for direct system administration by launching the setup tool ([setup.py](../../../guides/installing-lucy/installing-lucy.md#installation-tutorial)).\
\
**Audience:** Self-hosted / on-premise customers.

{% hint style="danger" %}
For customers utilizing publicly hosted VPS solutions provided by Lucy, please note that access to the "phishing" account is disabled by default, and this restriction remains in place even if password changes are made via the user interface.
{% endhint %}

