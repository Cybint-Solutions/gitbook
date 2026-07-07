# Upgrading to Lucy 6.0

{% hint style="info" %}
Lucy 6.0 is currently available only to Early Adopters. To join the program, contact your account manager.
{% endhint %}

## VPS Customers

If we are hosting your Lucy server for you, [contact support](../../../contact-us.md) to request an upgrade to 6.0.

***

## On-Premise Customers

This guide walks you through migrating from Lucy 5.7.6 to Lucy 6.0. The migration is handled by a script — follow the steps below in order.

### Before you start

Make sure you have:

* A Docker-based deployment
  * If you deployed with a vritual machine image this script will not work for you - [download a fresh 6.0 image instead](../).
* Lucy version 5.7.6
* At least 60% free storage space on the host

## Steps

### Stop all campaigns

{% hint style="warning" %}
The Lucy dashboard will be unavailable for the entire migration process. We recommend running this during a maintenance window or off-peak hours.
{% endhint %}

### Free up space

You'll need at least 60% free space in the container before backing up and migrating:

* Remove unedited templates
* Delete unneeded campaigns
* Delete old exports
* Clear the cache

### Create a snapshot of the host

The migration script will create a backup of the Lucy container, for safety you should create a snapshot of the entire host machine before you begin.

### Download the migration script

Run this on the host (not inside the container):

```bash
wget https://download.phishing-server.com/dl/upgrade_container6.sh
```

### Run the migration script

```bash
sudo bash upgrade_container6.sh
```

This can take several hours depending on how much data you have.

When prompted:

* **Autodetect Lucy container** → `YES`
* **System snapshot** → `YES`

### Update Lucy in the UI

Once the script finishes, [go to the Lucy UI to complete the update](../../../application-reference/support/update.md).
