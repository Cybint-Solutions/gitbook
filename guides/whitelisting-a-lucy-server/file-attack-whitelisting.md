---
cover: ../../.gitbook/assets/grouppolicy.png
coverY: 0
---

# File Attack Whitelisting

### **Introduction**

To simulate file-based malware attacks with Microsoft Defender, you need to configure Active Directory (AD) Group Policy Object (GPO) settings to exclude specific files from being scanned. This guide provides step-by-step instructions for whitelisting files by path using GPOs.

***

### **Important Considerations**

**Whitelisting Lucy IP:**

* Ensure that Lucy's IP is whitelisted at the mail gateway level to guarantee email delivery.
* Refer to the following links for detailed instructions:
  * [O365 Whitelisting](microsoft-o365-whitelisting.md)
  * [Google Workspace Whitelisting](google-workspace-whitelisting.md)

***

**Additional Security Measures:**

* This guide covers GPO settings for AD. If your organization uses additional antivirus software or firewall protection, equivalent whitelisting must be configured accordingly.

**Macro-Related Attacks:**

* For macro-related attacks, users will still need to enable editing and macros in Office documents. Design the attack scenario to prompt users to perform these actions.

***

### **Scenario Example**

**Scenario:**

* Successful Attack = Data Submit / File Data Received
* Attack Vector: Mixed Attack (Harvest credentials via user login on a web-hosted page + download and execute payload).

**Idea:**

* The user receives an email from the CEO with a link to a list of top clients.
* The user logs in to a landing page, completing phase 1 (credential harvesting).
* The user downloads an Excel file, which is excluded from virus scanning.
* Upon opening the file and enabling editing and macros, the script runs, completing phase 2 (data submission).

***

Below is the process for adding a file to the exclusion list at the machine level:

1. **Open Windows Security:**
   * Go to Start -> Settings -> Update & Security -> Windows Security -> Virus & Threat Protection.

<figure><img src="../../.gitbook/assets/image (757).png" alt="" width="547"><figcaption></figcaption></figure>

**Add Exclusion:**

* Under Virus & Threat Protection settings, select Manage Settings.
* Scroll down to Exclusions and select Add or Remove Exclusions.
* Click Add an Exclusion and choose File.
* Select the file to be excluded.

<figure><img src="../../.gitbook/assets/image (758).png" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (759).png" alt="" width="563"><figcaption></figcaption></figure>

This workflow demonstrates the process at an individual level, but for organizational-scale implementation, the Network Administrator will perform these steps via AD GPO.

***

### **Excluding a File Path in Active Directory via GPO:**

**Open Group Policy Management:**

* Navigate to Tools -> Group Policy Management.

<figure><img src="../../.gitbook/assets/image (760).png" alt=""><figcaption></figcaption></figure>

**Create or Edit a GPO:**

* Select the domain associated with the end users.
* Right-click on the policy and select Edit.

<figure><img src="../../.gitbook/assets/image (761).png" alt=""><figcaption></figcaption></figure>

**Navigate to Windows Defender Settings:**

* Go to Policies > Administrative Templates.

<figure><img src="../../.gitbook/assets/image (762).png" alt=""><figcaption></figcaption></figure>

* Click on Windows Components.

<figure><img src="../../.gitbook/assets/image (763).png" alt=""><figcaption></figcaption></figure>

* Scroll down to Microsoft Defender Antivirus.

<figure><img src="../../.gitbook/assets/image (764).png" alt=""><figcaption></figcaption></figure>

* Click on Exclusions.

<figure><img src="../../.gitbook/assets/image (765).png" alt=""><figcaption></figcaption></figure>

**Define Path Exclusion:**

* Select Path Exclusions.

<figure><img src="../../.gitbook/assets/image (766).png" alt=""><figcaption></figcaption></figure>

* Click Enable and then Show.

<figure><img src="../../.gitbook/assets/image (767).png" alt="" width="497"><figcaption></figcaption></figure>

* Enter the file path, e.g., `C:\Users\local.user\Downloads\List of Top clients V2.xls`.
* Set the value to 0.
* Click OK and Apply.

<figure><img src="../../.gitbook/assets/image (768).png" alt="" width="563"><figcaption></figcaption></figure>

**Enforce the Policy:**

* Right-click on the policy in Group Policy Management and select Enforce.

<figure><img src="../../.gitbook/assets/image (769).png" alt=""><figcaption></figcaption></figure>

* Run `gpupdate /force` to update the policy for all users.

<figure><img src="../../.gitbook/assets/image (770).png" alt=""><figcaption></figcaption></figure>

***

### **Enabling Editing and Content in Excel:**

**Enable Editing:**

* When the file is opened, click Enable Editing.

<figure><img src="../../.gitbook/assets/image (771).png" alt=""><figcaption></figcaption></figure>

**Enable Content:**

* Click Enable Content to allow macros to run.

<figure><img src="../../.gitbook/assets/image (772).png" alt=""><figcaption></figcaption></figure>

By following these steps, you can ensure that Defender does not block the file download and execution, allowing the simulation to proceed as intended.

**References**

* [Configure Extension File Exclusions in Microsoft Defender Antivirus](https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/configure-extension-file-exclusions-microsoft-defender-antivirus?view=o365-worldwide)

