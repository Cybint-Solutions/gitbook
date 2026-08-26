# Upgrading to Lucy 6.0

This section provides the upgrade procedures for **Lucy 5.7.6 to Lucy 6.0**.

Select the guide that matches your Lucy deployment:

* **Docker Deployments** — For on-premise Lucy installations running in Docker. This upgrade uses the Lucy migration script.
* **VMware Deployments** — For Lucy installations deployed as a VMware virtual machine. This upgrade uses a dedicated VMware upgrade package and requires multiple upgrade stages and reboots.
* **VPS Customers** — If Lucy is hosted by us, [contact Support](../../../contact-us.md) to schedule your upgrade.

***

## Before you begin

Before starting an upgrade:

* Confirm that you are running **Lucy 5.7.6**.
* Stop all active and scheduled campaigns.
* Make sure you have a recent backup or snapshot appropriate for your deployment.
* Ensure sufficient disk space is available.
* Plan the upgrade during a maintenance window or other suitable period of downtime.

**Do not start an upgrade until you have selected the procedure for your deployment type.**

***

## VPS Customers

If we host your Lucy server, please contact Support to request an upgrade to Lucy 6.0.

Upgrades are performed on a **first-come, first-served basis** and must be scheduled in advance.

***

## Docker Deployments

Use this guide if your Lucy server is deployed using Docker.

[**Upgrade Lucy 5.7.6 to 6.0 — Docker Deployments**](https://chatgpt.com/c/6a8eae79-0e10-83ed-924b-1788346e99a0)

The Docker migration uses an upgrade script to migrate the existing Lucy container. **Do not remove the old container until you have verified that the migration was successful.**

Lucy 6.0 uses **Ubuntu 24.04 inside the Docker container**. The host operating system can be any operating system supported by Docker.

***

## VMware Deployments

Use this guide if Lucy is deployed as a **VMware virtual machine**.

[**Upgrade Lucy 5.7.6 to 6.0 — VMware Deployments**](https://chatgpt.com/c/6a8eae79-0e10-83ed-924b-1788346e99a0)

The VMware upgrade uses a dedicated upgrade package and must be performed in multiple stages. The procedure includes upgrades to the underlying Ubuntu and PostgreSQL versions and requires the VM to be rebooted during the process.

**Do not proceed with the VMware procedure unless the required update servers are reachable from the VM.**
