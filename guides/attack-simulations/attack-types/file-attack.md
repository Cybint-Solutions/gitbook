# File Attack

### **Understanding the Attack**

**Definition**

A file attack is a type of cyber attack where malicious files are sent via email as attachments or links to web pages hosting the files. These files come in various formats, such as .exe, .SVG, Word macros, and Excel macros. The attack is successful if the user downloads, opens, and executes the file, with the executed data sent to Lucy.

<figure><img src="../../../.gitbook/assets/vmware_E95sSt8DtR.gif" alt=""><figcaption><p>This is an example of a File Attack, using a downloaded SVG to redirect to a malicious site</p></figcaption></figure>

***

### **Checklist**

* [x] [Register an Attack Domain](../../../application-screens-reference/settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard)
* [x] [Add a File Attack to your Campaign](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md)
* [x] [Choose a success action: File Download; File Data Received or File Opened](../../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#success-action)
* [x] [Ensure the File is excluded from Anti-Virus scanning in your infrastructure](../../whitelisting-a-lucy-server/file-attack-whitelisting.md)
* [x] [Ensure the sending Domain is whitelisted](../../whitelisting-a-lucy-server/)

***

### **Real-world Examples**

* An employee in the finance department receives an email appearing to be from HR, prompting them to download and fill out a timesheet attached as a Word document with a macro. Upon enabling and executing the macro, the malicious payload is delivered.
* An employee receives an email with a link to an .SVG file purportedly containing new branding materials. When the file is downloaded and opened, it executes a script that compromises the user's system.
* A finance executive receives an urgent email seemingly from the CEO, with an attached .exe file labeled as critical software for an emergency task. When the file is downloaded and executed, it installs malware, and the executed data is sent to the attacker.

{% hint style="success" %}
Ready to set up your File Attack? See our platform reference article on [Adding an Attack to your campaign](../../../application-screens-reference/templates/attack-templates.md).
{% endhint %}

***

### **File Attack Simulation Templates**

#### Lucy can compile different custom Malware Simulations:

Each file type can be modified (layout, filetype, name) before using it in a campaign. Currently, Lucy comes with the following file types:

{% hint style="success" %}
Want to start adapting your File Attack template? Navigate to **Templates -> File Templates**
{% endhint %}

| **Setting Name**           | **Description**                                                                                                                                                  | **Success Action**         | **Preferable Delivery Method** |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- | ------------------------------ |
| Console Interactive        | Establishes a reverse HTTP/HTTPS channel to Lucy. Runs in memory and allows command execution in Windows shell. Only works with Windows 7/8 with IE and Firefox. | File download              | Landing page                   |
| Console Outlook            | Executes commands and sends the output back via Outlook to a predefined email address.                                                                           | File download              | Landing page                   |
| Console post               | Executes commands within Windows shell and sends output to Lucy. Allows a limited set of commands.                                                               | File download              | Landing page                   |
| Console (POST-only)        | Pings back to Lucy when the user opens the executable file, without collecting any data.                                                                         | File download/open         | Landing page                   |
| Excel Macros (GET-only)    | Pings back to Lucy when the document is opened, without sending any data.                                                                                        | Click/download/open        | Email/Landing page             |
| GoggleDocs                 | Pings back to Lucy when the document is opened, without collecting any data.                                                                                     | File download              | Email/Portable device (USB)    |
| HTML (Redirect)            | Redirects to the phishing website when opened, without transferring any data.                                                                                    | File download              | Landing page                   |
| Keylogger                  | Records keys pressed on the keyboard.                                                                                                                            | File download/submit       | Email/Landing page             |
| Macros                     | Runs console commands through an Office file that contains a Macro.                                                                                              | File download/open         | Email/Landing page             |
| Malware Testing Toolkit    | Tests if the target system is vulnerable to miscellaneous malware technologies.                                                                                  | File download/open         | Email/Portable device (USB)    |
| Microphone                 | Gets audio recordings from the microphone.                                                                                                                       | File download/submit       | Portable device (USB)          |
| Ransomware (Screen Locker) | Locks the PC screen and asks the user to enter a password. Intended to prompt user to call helpdesk for password, enhancing learning effect.                     | File download/submit       | Email/Portable device (USB)    |
| Recent Documents           | Sends back a predefined number of documents listed in the recent doc cache to Lucy.                                                                              | File download/submit       | Email/Portable device (USB)    |
| Screen Recorder            | Records screenshots and attempts to access the webcam to record a few seconds.                                                                                   | File download/submit       | Email/Portable device (USB)    |
| SVG (Redirect)             | Redirects to the phishing website when opened, without transferring any data.                                                                                    | File download/click/submit | Email/Portable device (USB)    |

{% hint style="danger" %}
Email file attacks might be blocked by server security policies. Admins should ensure that such emails aren't filtered out before running the campaign. This can involve excluding the file by path using[ GPO or whitelisting the file name](../../whitelisting-a-lucy-server/file-attack-whitelisting.md).
{% endhint %}

***

### **User Detection Methods**

To help employees recognize and respond to file-based phishing attempts effectively, the following user detection methods can be incorporated into training programs:

#### Email Analysis

**Check Sender Details:** Verify the sender's email address and domain to ensure they match the legitimate source.

**Look for Red Flags:** Be wary of emails with poor grammar, spelling errors, or unusual formatting.

#### File Inspection

**Verify Attachments:** Be cautious of unsolicited attachments, especially those with executable or macro-enabled formats.

#### Content Verification

**Suspicious Attachments:** Avoid opening unexpected attachments or downloading files from unknown sources.

**Urgency and Threats:** Be cautious of emails that create a sense of urgency, pressure to act quickly, or threaten negative consequences.

#### Execution Verification

**Disable Macros:** By default, keep macros disabled in Office documents and only enable them if absolutely necessary and from a trusted source.

**Manual File Type Checks:** Instead of clicking on attachments, manually verify the file type and source before opening.

#### Communication Verification

**Cross-Check Requests:** If an email or message asks to download or execute a file, verify the request through a separate communication channel, such as a phone call to the supposed sender.

#### Incident Reporting

**Report Suspicious Files:** Immediately report any suspicious files or download links to the IT or security department for further analysis.

**Use Reporting Tools:** Deploy the [Lucy Phish Button](../../../application-screens-reference/settings/submitted-email-settings/) for all users to use as a reporting tool.

***
