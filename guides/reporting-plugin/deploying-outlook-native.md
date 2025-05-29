# Deploying Outlook Native

### Introduction

The native Outlook plugin supports these versions of the desktop application:

* Outlook 2016
* Outlook 2019
* Office 365 Desktop

The Outlook plugin is static, it cannot read changes from the Lucy server like the Office 365 version can. If you want to change settings, you must re-download the plugin and redeploy.

***

### Azure (Entra ID) settings

1. Login to your [Azure portal](https://portal.azure.com) and navigate to Microsoft Entra ID (formerly Azure AD).
2. Navigate to **App Registrations** and create a **New Registration**.
3. Give the application a name.
4. For the organization type select **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)**.
5. Define a **Web** redirect URI like so: \
   `https://<yourLucyURL>.<tld>/oauth`
6. Click **Register**.

<figure><img src="../../.gitbook/assets/image (810).png" alt=""><figcaption></figcaption></figure>

*   In the application overview, click the **Redirect URIs** option then select **Add a platform**.\


    <figure><img src="../../.gitbook/assets/image (807).png" alt=""><figcaption></figcaption></figure>
*   Select the **Mobile and Desktop Applications** option, enable all three of the pre-defined URIs, then click **Configure**.\


    <figure><img src="../../.gitbook/assets/image (808).png" alt=""><figcaption></figcaption></figure>
*   Scroll to the bottom of the **Authentication** page and enable **Live SDK Support** and **Allow Public Client Flows**, then click **Save**.\


    <figure><img src="../../.gitbook/assets/image (809).png" alt=""><figcaption></figcaption></figure>
* Navigate to **Certificates & secrets** and create a **new client secret**. Give the secret a name and expiration date, then click **Add**.
* Copy the **Secret Value**. Then navigate to the **Overview** and copy the **Application (client) ID** and **Directory (tenant) ID** as well. You will need all three values for the next steps.

## Download the plugin

Whether you are deploying the plugin manually on a single computer or globally via GPO, step one is to [Configure and download the plugin.](./)&#x20;

## Individual deployment

Local installation is simple, just run the MSI and allow it to install the plugin for you.

## Deploying via GPO

#### **1. Prepare the Plugin Package**

Ensure the plugin installer is accessible on a network share that all target computers can access. Set permissions to allow **read** access for authenticated users.

#### **2. Open Group Policy Management Console (GPMC)**

On the Domain Controller, open the Group Policy Management Console (`gpmc.msc`).

#### **3. Create a New GPO**

Right-click on the **Organizational Unit (OU)** where you want to deploy the plugin, and select **Create a GPO in this domain, and link it here**.

Name the GPO (e.g., _Deploy Lucy Plugin_).

#### **4. Edit the GPO for Software Installation**

Right-click the newly created GPO and select **Edit**.

In the Group Policy Management Editor, navigate to **Computer Configuration > Policies > Software Settings > Software Installation**.

#### **5. Add the Plugin for Deployment**

Right-click **Software Installation**, select **New > Package**.

Browse to the network share where the plugin installer is stored, select it, and choose **Assigned** to ensure it’s installed automatically on all targeted machines.

#### **6. Update Group Policy on Target Computers**

Either wait for the next Group Policy update cycle or force an update manually by running\
`gpupdate /force`.

## Technical Information

* The MSI logs operations under `C:\ProgramData\LucySecurity`
* Upon installation a temporary `config.dat` file is created, but all settings are written in the registry. The plugin may be installed in the user context (HKCU) or machine context (HKLM).
* The Plugin is available in 32 and 64-bit versions, so make sure you're downloading the correct one.
