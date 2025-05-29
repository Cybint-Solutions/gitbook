# Installing Lucy

## Time Required

Installation takes approximately 30-60 minutes, depending on your internet speed.

***

## Installing with Docker

Install the host OS, see our list of supported operating systems [here](hardware-requirements.md).

Download the installation file:

**For Ubuntu 20.04:**

```
wget https://download.phishing-server.com/dl/lucy-latest/install-20.04.sh
```

**For Ubuntu 22.04:**

```
wget https://download.phishing-server.com/dl/lucy-latest/install-22.04.sh
```

<figure><img src="../../.gitbook/assets/image (434).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Overview of install_script.sh</summary>

This script is a comprehensive Bash installation and management script for deploying a Lucy server, which uses Docker containers.

#### High-Level Overview

1. **Pre-Installation Checks**:
   * Verifies system prerequisites like kernel version, system architecture, and necessary ports availability. The script uses `set -e` to exit on any error.
2. **Docker Installation and Configuration**:
   * Checks for existing Docker installation and installs it if absent.
   * Handles specific configurations like storage types and network ports.
   * Manages and configures Docker containers specifically for Lucy, setting up necessary volumes and ports.
3. **Lucy Installation**:
   * Checks for sufficient disk space.
   * Pulls the Lucy Docker image and runs it with necessary parameters.
   * Configures system settings within the Docker container to integrate Lucy effectively.

#### Notes

* This script is highly specific to systems compatible with Docker and expects certain Linux kernel versions and architectures.
* It provides extensive error handling and user prompts to ensure that installations and changes are made explicitly with user consent and awareness.

</details>

Make the file executable:&#x20;

```
sudo chmod +x install.sh
```

Execute the file:

```
sudo ./install.sh
```

<figure><img src="../../.gitbook/assets/image (428).png" alt=""><figcaption></figcaption></figure>

Installation completed successfully:

<figure><img src="../../.gitbook/assets/image (418).png" alt=""><figcaption></figcaption></figure>

Verify if your Lucy container is running:

```
docker ps
```

<figure><img src="../../.gitbook/assets/image (419).png" alt=""><figcaption></figcaption></figure>

## Installing with VMware or Virtualbox

We supply preconfigured virtual images for VMware and VirtualBox.\
Simply download the image and deploy it in your preferred solution.

### VMware

ESXi: [https://download.phishing-server.com/dl/phishing-4.14/esxi.ova](https://download.phishing-server.com/dl/phishing-4.14/esxi.ova)\
OVF: [https://download.phishing-server.com/dl/lucy-latest/esxi\_ovf.zip](https://download.phishing-server.com/dl/lucy-latest/esxi_ovf.zip)

### VirtualBox

[https://download.phishing-server.com/dl/lucy-latest/virtualbox.zip](https://download.phishing-server.com/dl/lucy-latest/virtualbox.zip)

{% hint style="info" %}
Be sure to set the network mode to "Bridged" for all of the above VM solutions.
{% endhint %}

