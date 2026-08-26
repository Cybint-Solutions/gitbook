# VMware Deployments

This guide covers the upgrade of **Lucy 5.7.6 VMware deployments to Lucy 6.0**.

The VMware upgrade requires three executions of the upgrade script and two reboots. Follow the steps in order and do not interrupt the upgrade while it is running.

## Before you start

Make sure you have:

* A Lucy VMware VM
* SSH or VMware console access
* Sufficient disk space
* A recent backup or VMware snapshot according to your organization's backup procedure

#### Check connectivity to the update servers

Run the following commands from the Lucy VM:

```
ping -c 4 update.phishing-server.com
curl -I https://update.phishing-server.com

ping -c 4 update1.phishing-server.com
curl -I https://update1.phishing-server.com
```

Confirm that both update servers are reachable.

{% hint style="danger" %}
If either update server is unreachable, **do not proceed**.
{% endhint %}

***

## 1. Verify the current system

Confirm that the VM is running the expected starting versions:

```bash
lsb_release -a
psql --version
pg_lsclusters
```

Expected:

* Ubuntu 20.04
* PostgreSQL 11
* PostgreSQL 11 cluster present and running

Check for held packages:

```bash
apt-mark showhold
```

If `nodejs` is held, remove the hold:

```bash
sudo apt-mark unhold nodejs
```

{% hint style="danger" %}
Do not remove holds from other packages unless specifically required.
{% endhint %}

***

## 2. Download the upgrade package

On the the Lucy VM, download and extract the upgrade package:

```bash
wget https://download.phishing-server.com/dl/lucy-v6-upgrade-vmware.zip
unzip lucy-v6-upgrade-vmware.zip
cd lucy-v6-upgrade-vmware
chmod +x main-upgrade.sh
```

{% hint style="success" %}
Verify that `main-upgrade.sh` is present before continuing.
{% endhint %}

***

## 3. Upgrade Ubuntu 20.04 to 22.04

Run:

```bash
sudo ./main-upgrade.sh --yes
```

The first execution upgrades:

* PostgreSQL 11 → 14
* Ubuntu 20.04 → 22.04

Allow the script to complete. When prompted, select **Y** to reboot the VM.

After the VM comes back online, reconnect and verify:

```bash
lsb_release -a
```

{% hint style="success" %}
Confirm that the system is running **Ubuntu 22.04** before continuing.
{% endhint %}

***

## 4. Upgrade Ubuntu 22.04 to 24.04

Return to the upgrade directory and run the script again:

```bash
cd lucy-v6-upgrade-vmware
sudo ./main-upgrade.sh --yes
```

This upgrades **Ubuntu 22.04 → 24.04**.

Allow the script to complete and select **Y** when prompted to reboot.

After the VM comes back online, verify:

```bash
lsb_release -a
```

{% hint style="success" %}
Confirm that the system is running **Ubuntu 24.04** before continuing.
{% endhint %}

***

## 5. Complete Post-Upgrade Configuration

Run the script for the third and final time:

```bash
cd lucy-v6-upgrade-vmware
sudo ./main-upgrade.sh --yes
```

This performs the remaining post-upgrade configuration, including:

* PostgreSQL 14 → 16
* Python update to 3.8
* Required post-upgrade configuration

Allow the script to complete fully.

***

## 6. Verify the final system state

Confirm the following:

```bash
lsb_release -a
psql --version
pg_lsclusters
python3 --version
```

Expected:

* Ubuntu 24.04
* PostgreSQL 16, with the expected cluster running
* Python 3.8.x

Then hold `nodejs` again:

```bash
sudo apt-mark hold nodejs
apt-mark showhold
```

{% hint style="success" %}
Confirm that `nodejs` is listed as held.
{% endhint %}

***

## 7. Update Lucy to 6.0

Only after all server-side checks have passed:

1. Open the Lucy UI.
2. Log in with an administrator account.
3. Navigate to the **Update** section.
4. Start the update and wait for it to complete.
5. Confirm that the Lucy UI reports version **6.0**.

***

## Final state

The upgrade is complete when all of the following are confirmed:

* Ubuntu 24.04
* PostgreSQL 16
* Python 3.8.x
* `nodejs` held
* Lucy 6.0
