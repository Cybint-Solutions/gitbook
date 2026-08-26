# Docker Deployments

### Before you start

Make sure you have:

* A Docker-based deployment
* Lucy version 5.7.6
* At least 60% free storage space on the host
* A recent snapshot or backup of the host machine

***

### 1. Stop all campaigns

Stop all active and scheduled campaigns before starting the migration.

The Lucy dashboard will be unavailable for the entire migration process. We recommend performing the upgrade during a maintenance window or during off-peak hours.

### 2. Free up storage space

The migration requires at least **60% free storage space on the host** to allow the existing Lucy container to be backed up and migrated.

If additional space is required, consider removing:

* Unedited templates that are no longer needed
* Unneeded campaigns
* Old exports
* Cached data

### 3. Create a host snapshot

The migration script creates a backup of the existing Lucy container. As an additional safety measure, we strongly recommend creating a snapshot of the **entire host machine** before starting the migration.

If the host is running on a virtualization platform, create the snapshot using the platform's normal snapshot functionality.

### 4. Download the migration script

Run the following command **on the host machine, not inside the Lucy container**:

```bash
wget https://download.phishing-server.com/dl/upgrade_container6.sh
```

### 5. Run the migration script

Run the following command **on the host machine, not inside the Lucy container**:

```bash
sudo bash upgrade_container6.sh
```

The migration may take several hours depending on the amount of data stored in Lucy.

When prompted, select:

* **Autodetect Lucy container** → `YES`
* **System snapshot** → `YES`

Allow the script to complete before proceeding.

### 6. Update Lucy in the UI

Once the migration script has finished, access the Lucy UI and complete the update to **Lucy 6.0**.

### 7. Verify the migration

After upgrading to Lucy 6.0, verify that the migration was successful and that the expected data is available and functioning correctly.

Check that the expected campaigns, templates, users, settings, and other required data are present.

### 8. Remove the old container

Only after you have confirmed that the migration was successful and everything is working correctly, remove the old container:

```bash
sudo docker rm lucy_old_backup
```

{% hint style="danger" %}
Do not remove `lucy_old_backup` until you have verified the migration. Once the old container has been removed, it can no longer be used as a fallback.
{% endhint %}
