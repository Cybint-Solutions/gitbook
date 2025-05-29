# Confidentiality of Campaign Data

## What Data Gets Logged?

LUCY offers different logging levels to suit your privacy and security needs:

### Logging Levels

* **Normal Logging:** All campaign data is logged in the database.
* **Anonymous Mode:** Use this mode to hide all victim data (e.g., IP addresses, login details) from statistics, reports, and the database.

### Details About Anonymous Mode

If the **Anonymous Mode** checkbox is selected within the scenario settings, all personalized data is automatically deleted. There is no way to track individual users. Only generic statistics remain visible.

***

## Questions About Confidentiality

### Is Data Shared Among Clients or Sent Back to Us?

No. All data is stored in a local PostgreSQL RDBMS that comes with LUCY. There is no centralized storage, and data is **never sent back to us**. Even if you use LUCY as a SaaS, you will have a dedicated Linux server with a separate database that is not shared with other clients.

### How Can You Delete Campaign Data?

Once you reset statistics in LUCY, delete a campaign, or remove recipients from a running campaign, the associated data is removed from the database and **cannot be restored**.

### Does LUCY Send Any Confidential Data Back to Us?

No, never.

LUCY can send us log files, but this process must be manually initiated. The log files only contain technical data about your installation (e.g., Apache logs). All possible confidential data is **deleted** before transmission. LUCY does not collect any information about your campaign settings.

When running checks during a campaign, LUCY connects to external servers to test settings (e.g., SPAM, accessibility) without sending any information about your environment, settings, or campaign.

### Is the Data in the Database Encrypted?

Yes. All data in the database is encrypted using **AES (Advanced Encryption Standard)**.
