# Upgrading to Lucy 6.0

## VPS Customers

If we are hosting your Lucy server for you, please [contact support](../../../contact-us.md) to request an upgrade to 6.0.

Upgrades are on a first-come, first-served basis and need to be scheduled in advance.

***

## On-Premise Customers

This guide walks you through the migration from **Lucy 5.7.6 to Lucy 6.0**.

The migration is performed using an upgrade script. Follow the steps below **in order** and do not remove the old Lucy container until you have verified that the migration was successful.

{% hint style="success" %}
Lucy 6.0 uses Ubuntu 24.04 inside the Docker container.\
The host machine itself can run any operating system supported by Docker.
{% endhint %}

#### Before you start

Make sure you have:

* A Docker-based deployment
* Lucy version 5.7.6
* At least 60% free storage space on the host
* A recent **snapshot or backup of the host machine**

{% hint style="danger" %}
If Lucy was deployed using a virtual machine image, this migration script cannot be used.\
[Contact Support](../../../contact-us.md) for assistance with the upgrade.
{% endhint %}

#### 1. Stop all campaigns

Stop all active and scheduled campaigns before starting the migration.

{% hint style="warning" %}
The Lucy dashboard will be unavailable for the entire migration process. We recommend performing the upgrade during a maintenance window or during off-peak hours.
{% endhint %}

#### 2. Free up storage space

The migration requires at least **60% free storage space on the host** to allow the existing Lucy container to be backed up and migrated.

Before starting, consider removing:

* Unedited templates that are no longer needed
* Unneeded campaigns
* Old exports
* Cached data

#### 3. Create a host snapshot

The migration script creates a backup of the existing Lucy container. As an additional safety measure, we strongly recommend creating a snapshot of the **entire host machine** before starting the migration.

{% hint style="info" %}
If the host is running on a virtualization platform, create the snapshot using the platform's normal snapshot functionality.
{% endhint %}

#### 4. Download the migration script

Run the following command **on the host machine, not inside the Lucy container**:

```bash
wget https://download.phishing-server.com/dl/upgrade_container6.sh
```

#### 5. Run the migration script

Run the following command **on the host machine, not inside the Lucy container**:

```bash
sudo bash upgrade_container6.sh
```

{% hint style="info" %}
The migration can take several hours depending on the amount of data stored in Lucy.
{% endhint %}

When prompted, select:

* **Autodetect Lucy container** → `YES`
* **System snapshot** → `YES`

Allow the script to complete before proceeding.

#### 6. Update Lucy in the UI

Once the migration script has finished, access the Lucy UI and complete the [update to Lucy 6.0](../../../application-reference/support/update.md).

#### 7. Verify the Migration

After upgrading to Lucy 6.0, review the workstation and verify that your data has been migrated successfully.

Check that the expected campaigns, templates, users, settings, and other required data are available and functioning correctly.

#### 8. Remove the old container

Once you have confirmed that the migration was successful and everything is working correctly, remove the old container:

```
sudo docker rm lucy_old_backup
```

{% hint style="danger" %}
**Important:** Only remove `lucy_old_backup` after verifying the migration. Once the old container has been removed, it can no longer be used as a fallback.
{% endhint %}
