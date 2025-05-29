# System Monitoring

### Introduction

The System Monitoring tool in LUCY allows you to track hardware performance in real time, ensuring your system operates efficiently.

***

{% hint style="info" %}
Navigate to **Support -> Status -> System Monitoring**
{% endhint %}

### Components

* **Real-Time Hardware Monitoring**: Observe CPU, RAM, and other hardware metrics to ensure your system is running smoothly.

<figure><img src="../../../.gitbook/assets/image (646).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Ram Usage vs Ram Usage with Cache</summary>

The difference between "RAM Usage" and "RAM Usage Without Cache" can be explained as follows:

1. **RAM Usage**: This represents the total amount of RAM currently being used by the system. This includes all memory used by running applications, the operating system, and cached data. Cached data is data that the system keeps in memory for faster access, even if it's not actively being used by applications at the moment.
2. **RAM Usage Without Cache**: This represents the amount of RAM being used by running applications and the operating system, excluding the cached data. Cached data can be quickly freed up if an application needs more memory, so this metric can give a better idea of how much memory is available for new operations.

In the graph, the blue area represents the total RAM usage, including the cache. The green area represents the RAM usage without the cache, which is generally lower because it excludes the cache that can be freed up if needed.

This distinction is useful for understanding how much of the system's RAM is truly in use versus how much is available if the system needs to allocate more memory to active processes.

</details>

* **Data Cleanup**: Maintain optimal performance by removing unnecessary or unused data from LUCY.

<figure><img src="../../../.gitbook/assets/image (647).png" alt=""><figcaption></figcaption></figure>

**Data Cleanup Options**

* **Cleaning Templates, Campaigns, etc.**: This deletes all downloaded or created templates, campaigns, and related database records.
* **Cleaning DB-Backups**: Removes all database backups from the LUCY server.
* **Clear Database**: Deletes all campaigns and recipients marked as deleted in the LUCY panel. Although marked as deleted, the records still exist in the database until this action is performed.
* **Clear Incidents**: Removes thumbnails and attachments of reports, which take up significant disk space. The emails themselves remain in the database and appear under the Incidents tab.

These features help you maintain a clean and efficient system, ensuring your hardware can handle the demands of your campaigns effectively.
