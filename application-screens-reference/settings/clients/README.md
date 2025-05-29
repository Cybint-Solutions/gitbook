# Clients

### Introduction

A client in LUCY can represent your own organization or any company for which you are performing a phishing test. You can create a new client or use the built-in client.

### **Create a Client:**

{% hint style="info" %}
Navigate to **Settings -> Clients -> Clients**
{% endhint %}

Click on "New Client" to create a new client.

<figure><img src="../../../.gitbook/assets/image (417).png" alt=""><figcaption></figcaption></figure>

**Uses of Clients:**

* **Restricted Dashboard Access:** Create view-only accounts associated with specific clients.
* **Client-Specific Reports:** View reports related to specific clients.
* **Client-Specific Campaigns:** Manage campaigns for specific clients.

**Managing Branches**

Branches allow you to manage client-related administrative users, recipient groups, and campaigns. This feature was introduced in LUCY version 4.8.

**Creating and Using Branches:**

1. **Create Branches:**
   * Go to `Settings` → `Clients`.
   * Select a client and navigate to the `Branches` tab.
   * Enter the name of the new branch and click `Create`.
2. **Associating Data with Branches:**
   * **Recipient Groups:**
     * Go to `Settings` → `Recipients`.
     * Select a recipient group and go to the `Edit Group` tab.
     * Choose the client and branch from the respective drop-down menus and click `Save`.
   * **Templates:**
     * Go to `Settings` → `Templates`.
     * Select a template and click `Edit`.
     * Choose the client and branch from the respective drop-down menus and click `Save`.
   * **Administrative Users:**
     * Go to `Settings` → `Administrative Users`.
     * Click `+New User`.
     * Fill in the user details, select the role, and choose the client and branch from the drop-down menus.
     * Click `Save`.

**Branches Usage:**

* **Segmentation:** Branches can represent different tiers of management, physical locations, languages, organizational divisions, or security levels.
* **Access Control:** Only users associated with a specific branch will see data related to that branch.
* **Data Association:** Confidential data such as recipient groups, campaigns, templates, and reports can be associated with branches.

**Practical Example:**

1. **Creating a Branch:**
   * Go to `Settings` → `Clients`.
   * Select a client and open the `Branches` tab.
   * Enter the branch name (e.g., "Marketing Department") and click `Create`.
2. **Associating a Recipient Group:**
   * Go to `Settings` → `Recipients`.
   * Select a group and open the `Edit Group` tab.
   * Choose the client and the "Marketing Department" branch.
   * Click `Save`.
3. **Creating an Administrative User:**
   * Go to `Settings` → `Administrative Users`.
   * Click `+New User`.
   * Fill in the user details and select the role.
   * Choose the client and "Marketing Department" branch.
   * Click `Save`.

**Summary**

By utilizing clients and branches in LUCY, you can effectively manage access and data segmentation across different organizational levels and departments. This ensures that sensitive data is only accessible to authorized users, enhancing security and management efficiency.
