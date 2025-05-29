# Deploying Gmail

{% hint style="info" %}
Navigate to Incidents -> Download Plugin -> Gmail Addon
{% endhint %}

***

### 1. Download plugin files

Navigate to **Incidents** and click the **Download Plugin** button, then select the "Gmail Addon" option.

<figure><img src="../../.gitbook/assets/image (820).png" alt=""><figcaption></figcaption></figure>

The addon will be deployed as a Google App, so the download contains two files in an archive:

1. `code.js` - The plugin's runtime code.
2. `appsscript.json` - The plugin's metadata.

***

### 2. Create a new Google project

Go to [https://script.google.com/](https://script.google.com/) and create a **New Project**.

<figure><img src="../../.gitbook/assets/image (822).png" alt="" width="563"><figcaption></figcaption></figure>

***

### 3. Edit Code.gs

When the project opens, copy the contents of `code.js` into the workspace and click the **Save** icon. If there is any code in the workspace file before you paste, remove it first.

<figure><img src="../../.gitbook/assets/image (823).png" alt=""><figcaption><p>The file is named Code.gs by default</p></figcaption></figure>

***

### 4. Edit appsscript.json

Next, select the **Project Settings** icon from the options on the left and enable the option for "Show 'appsscript.json' metadata in editor". You should also select your time zone here.

<figure><img src="../../.gitbook/assets/image (824).png" alt="" width="563"><figcaption></figcaption></figure>

Return to the code editor and paste the contents of the `appscript.json` file that you downloaded into the `appscript.json` file in the editor. If there is any code in the workspace file before you paste, remove it first.

<figure><img src="../../.gitbook/assets/image (825).png" alt=""><figcaption></figcaption></figure>

#### Metadata Options

Most of the fields in this object should be left alone, but there are a few worth checking before you deploy this project.

**Name:** The name of the add-on in your mail client. This name appears when you hover the mouse over the button.

**Logo URL:** A link to the button's image. The default is an image hosted by us, but you can host your own image and link to it here.

**Primary and Secondary Color:** Customize the color scheme. This field accepts hex codes, use a [hex code tool of your choice](https://www.google.com/search?q=color+hex+code+tool) to find the colors you like.

***

### 5. Deploy the project

Click **Deploy** and select "New Deployment". Make sure the addon type is both **Add-on** and **Web App**, and the options shown below for Web App are selected. When everything looks right, click **Deploy** and then click "Done".

<figure><img src="../../.gitbook/assets/image (828).png" alt=""><figcaption></figcaption></figure>

***

### 6. Install the addon

Click **Deploy** again and this time select "Test Deployments", then select "Install".

<figure><img src="../../.gitbook/assets/image (830).png" alt=""><figcaption></figcaption></figure>
