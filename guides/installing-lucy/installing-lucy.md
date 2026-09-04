# Installing Lucy

Lucy can be deployed using one of the following methods:

* **Docker** installation on a supported operating system
* **Preconfigured virtual machines** for VMware or VirtualBox

For a full list of supported operating systems, see [**Supported Operating Systems**](system-requirements.md#supported-operating-system-for-docker-installation).

***

## Docker

#### Lucy 6

**Supported host OS:** Ubuntu 22.04 or higher

**Bash installer**

```bash
wget https://download.phishing-server.com/dl/lucy-latest/Install_lucy_6.0.sh
sudo bash Install_lucy_6.0.sh
```

#### Lucy 5

**Supported host OS:** Ubuntu 22.04 or higher

**Bash installer**

```bash
wget https://download.phishing-server.com/dl/lucy-latest/Install_lucy_5.7.2.sh
sudo bash Install_lucy_5.7.2
```

**C++ installer**

```bash
wget https://download.phishing-server.com/dl/lucy-latest/Install_lucy_5.7.2
sudo ./Install_lucy_5.7.2
```

#### Verify the installation

After installation, confirm that the Lucy container is running:

```bash
docker ps
```

You should see the **Lucy container** in the output..

***

### Legacy Docker Installers

{% hint style="warning" %}
These installers deploy a Docker container running **Ubuntu 20.04**, which is no longer supported.

Use them only if required for compatibility with an existing deployment.
{% endhint %}

| Host OS      | Installer                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------ |
| Ubuntu 20.04 | [Download installer](https://download.phishing-server.com/dl/lucy-latest/install-20.04.sh) |
| Ubuntu 22.04 | [Download installer](https://download.phishing-server.com/dl/lucy-latest/install-22.04.sh) |

***

## Virtual Machines

Lucy is also available as a preconfigured virtual machine.

{% hint style="info" %}
**Network configuration:** Set the VM network adapter to **Bridged** mode.
{% endhint %}

### VMware

| Version      | Format | Download                                                                                  |
| ------------ | ------ | ----------------------------------------------------------------------------------------- |
| **Lucy 6**   | ESXi   | [Download ESXi OVA](https://download.phishing-server.com/dl/phishing-6.0/esxi.ova)        |
| **Lucy 6**   | OVF    | [Download OVF package](https://download.phishing-server.com/dl/phishing-6.0/esxi_ovf.zip) |
| **Lucy 5.7** | ESXi   | [Download ESXi OVA](https://download.phishing-server.com/dl/phishing-5.7/esxi.ova)        |
| **Lucy 5.7** | OVF    | [Download OVF package](https://download.phishing-server.com/dl/phishing-5.7/esxi_ovf.zip) |

### VirtualBox

[**Download VirtualBox image**](https://download.phishing-server.com/dl/lucy-latest/virtualbox.zip)
