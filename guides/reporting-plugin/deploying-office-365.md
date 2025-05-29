# Deploying Office 365

### Introduction

The Office 365 plugin is dynamic - the plugin reads the settings from your Lucy server, so if you update those settings you do not need to re-deploy the plugin.

***

### Azure (Entra ID) settings

1. Login to your [Azure portal](https://portal.azure.com) and navigate to Microsoft Entra ID (formerly Azure AD).
2. Navigate to **App Registrations** and create a **New Registration**.
3. Give the application a name.
4. For the organization type select **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant)**.
5. Define a **Web** redirect URI like so: `https://<yourURL>.<tld>/oauth`
6. Click **Register**.

<figure><img src="../../.gitbook/assets/image (817).png" alt=""><figcaption></figcaption></figure>

*   In the application overview, click the **Redirect URIs** option then select **Add a platform**.\


    <figure><img src="../../.gitbook/assets/image (818).png" alt=""><figcaption></figcaption></figure>
* Select the **Single-page Application** option and add the following two redirects:
  1. `https://<yourLucyURL>.<tld>/login/login.html`
  2. `https://<yourLucyURL>.<tld>/new-o365/dist/index.html`
* Navigate to **Certificates & secrets** and create a **new client secret**. Give the secret a name and expiration date, then click **Add**.
* Copy the **Secret Value**. Then navigate to the **Overview** and copy the **Application (client) ID** and **Directory (tenant) ID** as well. You will need all three values for the next steps.

{% hint style="warning" %}
Be sure to copy the secret value, once you navigate away from the page you will not be able to see or copy it again.
{% endhint %}

### Deploying the plugin

{% tabs %}
{% tab title="For an individual" %}
1. [Configure and download the plugin.](./)
2. Sign in to your Office 365 account: [https://outlook.live.com/owa/](https://outlook.live.com/owa/)
3.  Select an email from your inbox and click the "Apps" button. Then, select "Get add-ins":

    <figure><img src="../../.gitbook/assets/image (882).png" alt=""><figcaption></figcaption></figure>
4.  Select **My add-ins** and scroll to "Custom Add-ins", then click "Add a custom add-in" and "Add from file..."\


    <figure><img src="../../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>
5. Upload the XML file from Step 1 and refresh the page. Now when you click the "Apps" button the Lucy plugin should be present:

<figure><img src="../../.gitbook/assets/image (886).png" alt=""><figcaption></figcaption></figure>

6. The first time you use the plugin you must authorize it:

<figure><img src="../../.gitbook/assets/image (889).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="For an organization" %}
{% hint style="info" %}
This type of deployment requires administrator privileges in your O365 environment.
{% endhint %}

1. [Configure and download the plugin.](./)
2. Go to your [Office 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).
3. Navigate to **Settings > Integrated Apps**.
4. Select "Upload custom apps" to open the wizard.
5. Choose "Office Add-in" for the **App type** and then "Upload manifest file (.xml) from device". Select the XML file you downloaded from Step 1, then click **Next**.
6. Under **Assign users** select "Entire Organization", then click **Next**.
7.  Accept the required permissions for the plugin and click **Next**, then click **Finish Deployment**.\


    <figure><img src="../../.gitbook/assets/image (791).png" alt="" width="563"><figcaption></figcaption></figure>
8. Once the plugin finishes deployment click **Done.**

<figure><img src="../../.gitbook/assets/image (976).png" alt="" width="563"><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

***

### Mac and mobile compatibility

The organization-wide deployment is compatible with Mac and mobile devices. Mobile devices that are part of the organization should require no additional setup. For Apple computers, the user must be logged in through Microsoft's [Office for Mac](https://www.microsoft.com/en-us/microsoft-365/mac/microsoft-365-for-mac) product.
