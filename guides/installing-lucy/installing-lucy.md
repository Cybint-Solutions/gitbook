# Installing Lucy

Lucy can be deployed using one of the following methods:

* **Docker installation on a supported OS**
* **Prebuilt virtual machines (VMware / VirtualBox)**

For a full list of supported operating systems, see the [**Supported Operating Systems**](hardware-requirements.md).

## Docker Installation (Recommended)

{% hint style="info" %}
Supported Systems: Ubuntu 22.04 or higher
{% endhint %}

#### **C++ Installer**

```
wget https://download.phishing-server.com/dl/lucy-latest/Install_lucy_5.7.2
```

#### **Bash Installer**

```
wget https://download.phishing-server.com/dl/lucy-latest/Install_lucy_5.7.2.sh
```

#### Make the installer exectuable

```
sudo chmod +x install.sh
```

#### Run the installer

```
sudo ./install.sh
```

#### Verify the Installation

Once installation is complete, confirm the Lucy container is running:

```
docker ps
```

You should see the **Lucy container** listed in the output.

***

#### Legacy Docker Installers

{% hint style="info" %}
⚠ **Warning**

The legacy installation scripts deploy a **Docker container running Ubuntu 20.04**, which is **no longer supported**.

Use these installers **only if you have a specific compatibility requirement**.
{% endhint %}

**Ubuntu 20.04 Host**

```
wget https://download.phishing-server.com/dl/lucy-latest/install-20.04.sh
```

**Ubuntu 22.04 Host**

```
wget https://download.phishing-server.com/dl/lucy-latest/install-22.04.sh
```

***

## Virtual Machine Installations

Lucy is also available as a **preconfigured virtual machine**.

{% hint style="info" %}
For all VM deployments, configure the network adapter as:

Network Mode: `Bridged`
{% endhint %}

#### VMware

**ESXi**

```
https://download.phishing-server.com/dl/phishing-5.7/esxi.ova
```

**OVF**

```
https://download.phishing-server.com/dl/phishing-5.7/esxi_ovf.zip
```

#### Legacy VMware Images

**ESXi**

```
https://download.phishing-server.com/dl/phishing-5.6/esxi.ova
```

**OVF**

```
https://download.phishing-server.com/dl/phishing-5.6/esxi_ovf.zip
```

***

#### VirtualBox

```
https://download.phishing-server.com/dl/lucy-latest/virtualbox.zip
```
