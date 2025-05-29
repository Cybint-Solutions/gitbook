# Architecture

### Overview

This document outlines the key structural elements and settings of Lucy.

<figure><img src="../../.gitbook/assets/image (435).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
"LUST" is the central licensing and content server managed by Lucy Security.
{% endhint %}

### Operating System

* **Ubuntu 20.04.4 LTS**: Lucy operates on a 64-bit Ubuntu 20.04.4 LTS system, without any additional patches or hardening. Updates are managed through a self-hosted repository mirror.

### Web Server

* **Apache 2.4.41**: Utilizes "mod-security" and "mod-headers" for enhanced security.

### Database

* **PostgreSQL 14.8**: Stores all related data with AES-256-CBC encryption at the column level.

### Intermediary Storage

* **Redis 5.0.7**: Used as a task queue for passing data between users and system workers.

### Application

* **PHP v8.1.18 and Python 3.8.10**: Lucy is primarily a PHP application using the Yii Framework, with some background scripts in Python.

### Security

* **OWASP Top 10 / 2017**: Adheres to OWASP security standards.
* **Firewall and SSL**: Custom [firewall rules](../../application-screens-reference/settings/common-system-settings/firewall.md) and [SSL configurations](../../application-screens-reference/settings/common-system-settings/ssl-settings/).
* **User Accounts**: "phishing" and "support" accounts for specific functions and support purposes.

### Folders

* **/opt/phishing**: Main directory containing system code, user files, and settings.

### Logs

* **Apache Logs**: Located in `/var/logs/apache2`.
* **Application Logs**: Located in `/opt/phishing/runtime`.

### Critical Services

* **Services**: Apache2, PostgreSQL, Redis-server, and Supervisor are critical services.

### Installation and Updates

Docker-based installation with seamless updates via APT within the container.

* Containers share the host OS kernel, enabling rapid startup and efficient RAM usage.
* Uses layered filesystems for efficient disk usage and image downloads.
* Ensures application isolation, running as a separate process in userspace.
* Not bound to specific infrastructure, allowing operation on any computer, infrastructure, or cloud.

### Network Communication

* **Outbound Communication**: Required by LUCY for license server updates, vulnerability checks, and various optional services.
  * **License Server (LUST)**: Updates and templates over HTTPS.
  * **Vulnerability Checks**: Port 80 connection to static.nvd.nist.gov for NIST CVE database.
  * **Update Servers**: Access to update.phishing-server.com and update1.phishing-server.com on ports 80 and 443.
  * **Optional Services**: DNS, URL shortening
* **Inbound Communication**: Requires ports 80 and 443 for web access and port 25 for email replies.
* **Malware Simulation Communication**: Uses HTTP/HTTPS for data collection during simulations.

