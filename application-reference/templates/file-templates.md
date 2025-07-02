# File Templates

### Introduction

This section focuses on how you can utilize our diverse range of customizable File-based templates to conduct simulated phishing campaigns. By incorporating these templates into your training modules, users are exposed to realistic scenarios involving phishing emails with malicious attachments or downloadable links.&#x20;

The goal is to educate and test users on how to identify and react appropriately to potential security threats. Each template here is tailored to mimic various types of File-based attacks, providing a practical and effective approach to enhancing your organization’s security posture.

***

### Configuration

{% hint style="info" %}
Navigate to **Templates -> File Templates**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (615).png" alt=""><figcaption><p>\</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (617).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Delete" %}
This button allows you to remove the selected file from your server.
{% endtab %}

{% tab title="Copy" %}
This option enables you to create a duplicate of the selected file.&#x20;

{% hint style="info" %}
Creating duplicates is a good practice to always have the original as a reference. If you lose the original, you can use the "Download" option to search for and re-download the template.
{% endhint %}
{% endtab %}

{% tab title="Backup" %}
The backup option is used to save a copy of the selected file. This is useful for safeguarding data against potential loss or corruption. Additionally, it allows you to move a customized file-based template to another LUCY instance. You can then use the "Restore" option to import the template.
{% endtab %}

{% tab title="Restore" %}
This feature is used to bring a file back to a previous state from a backup. It's particularly useful if you need to revert changes or recover from a template from another Lucy instance.
{% endtab %}

{% tab title="Download" %}
This option is used to access the [Downloads page](download-templates.md), where you can re-download file-based templates from the central template repository.
{% endtab %}

{% tab title="New" %}
Typically represented by a "+" icon, this button is used to create a new File-based attack template within the application.
{% endtab %}
{% endtabs %}

***

### New File-based Template

Select "New" to create a newly created File-based template.

<figure><img src="../../.gitbook/assets/image (616).png" alt=""><figcaption></figcaption></figure>

When creating a new file-based attack template in LUCY, several fields and options need to be configured. Here’s a detailed explanation of each option, along with the dropdown selections provided:

<details>

<summary>General options for a new File-based temaplate</summary>

**Name**:

* Enter a unique name for the new template. This is a required field.

**Client**:

* Select the [client](../settings/clients/) for whom this template is being created from the dropdown list.

**Description**:

* Optional to provide a detailed description of the template. This helps in understanding the template's purpose and contents.

**Scenario Type**:

* **Web Based**: Templates designed for web-based phishing scenarios.
* **Hyperlink**: Templates that involve malicious hyperlinks.
* **File-Based**: Templates focusing on file-based attacks (e.g., malicious attachments).
* **Mixed**: Templates combining multiple types of attacks.
* **Technical Malware Test**: Templates designed for testing malware resilience.
* **Portable Media Attack**: Templates involving attacks via portable media (e.g., USB drives).
* **Awareness Only**: Templates aimed at raising awareness without actual malicious payloads.
* **Mail & Web Test**: Combined email and web-based attack simulations.

**Convert HTML to PDF**

* **Description**: If checked, this option converts the provided HTML content into a PDF file, allowing you to create more polished and standardized attachments for your campaign.

**Add Attachment**:

* Attach a file or payload that will be included in the template. Click "Choose File" to upload the file.

**Configurations**:

* Additional configurations for the template can be added here.

**Variables**:

* Define variables that will be used in the template. You can add multiple variables with the following fields:
  * **Name**: The variable name.
  * **Internal Name**: The name used internally in the template.
  * **Type**: The type of input for the variable (Text, Checkbox, Selectbox).
  * **Value**: The default value for the variable.

</details>

#### Practical Example:

When creating a file-based attack template in LUCY, such as the "Ransomware (Screen Locker)" template, you simulate a ransomware attack by locking the user's PC. You can define this template's variables in the settings as follows:

<figure><img src="../../.gitbook/assets/image (618).png" alt=""><figcaption></figcaption></figure>

The above example prompts the user to enter a password, as defined in the first variable line. This line allows you to set the actual password needed to unlock the screen, which in this case is "123".

Additionally, in the second variable, you can define the message the user will see when they execute the file. In this case, the message is "YOUR PC IS LOCKED WITH RAN$OMWARE - CALL IT SUPPORT FOR HELP."

{% hint style="info" %}
See our Ransomware File-based attack in action [here](attack-templates.md#file-based).
{% endhint %}

***

### **FILE-BASED ATTACK SIMULATION TEMPLATES**&#x20;

LUCY allows for the customization of various malware simulations:

| Setting Name                   | Description                                                                                                                                                                      | Success Action                  | Preferable Delivery Method  |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | --------------------------- |
| **Console Interactive**        | Establishes a reverse HTTP/HTTPS channel to LUCY upon file execution, visible under “Sessions”. This tool operates solely in memory and supports commands via the Windows shell. | File download                   | Landing page                |
| **Console Outlook**            | Executes commands and sends results back via Outlook using MAPI, including retrieving the subject line from the last received email.                                             | File download                   | Landing page                |
| **Console post**               | Executes limited command set within the Windows shell and sends output to LUCY. Direct command line access is available for built-in commands.                                   | File download                   | Landing page                |
| **Console (POST-only)**        | Pings back to Lucy upon file opening without data collection.                                                                                                                    | File download/File open         | Landing page                |
| **Excel Macros (Various)**     | Various macros templates that ping back to Lucy without data transfer. Note: For campaign settings, select "Click" as the Success Action for accurate metrics.                   | Click/File download/File open   | Email/Landing page          |
| **Keylogger**                  | Records keystrokes.                                                                                                                                                              | File download/Data submit       | Email/Landing page          |
| **Macros (Various)**           | Various macros templates either ping back to Lucy or run specific commands. Supports scenarios with or without data collection.                                                  | File download/File open         | Email/Landing page          |
| **Malware Testing Toolkit**    | Checks if the system is susceptible to various malware techniques.                                                                                                               | File download/File open         | Email/Portable device (USB) |
| **Microphone**                 | Captures audio via the microphone.                                                                                                                                               | File download/Data submit       | Portable device (USB)       |
| **Ransomware (Screen Locker)** | Locks the PC screen, requiring a backend-set password for unlocking to simulate a real ransomware attack scenario.                                                               | File download/Data submit       | Email/Portable device (USB) |
| **Recent Documents**           | Retrieves a set number of documents from the recent document cache.                                                                                                              | File download/Data submit       | Email/Portable device (USB) |
| **Screen Recorder**            | Captures screenshots and webcam footage as proof of concept.                                                                                                                     | File download/Data submit       | Email/Portable device (USB) |
| **SVG (Redirect)**             | Redirects to a phishing website when the SVG file is opened, without data transfer.                                                                                              | File download/Click/Data submit | Email/Portable device (USB) |

{% hint style="warning" %}
There is a high likelihood of email-delivered files being blocked by mail server security policies. Admins should adjust filters to ensure delivery.
{% endhint %}
