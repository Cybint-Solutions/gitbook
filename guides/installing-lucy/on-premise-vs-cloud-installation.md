# On-Premise vs Cloud Installation

### Introduction

This article explores Lucy's adaptable architecture for on-premise and cloud-hosted setups.

### **Cloud Installation Advantages:**

<details>

<summary>VPS and Dedicated Root Server Hosting with LUCY Security AG</summary>

LUCY provides clients with the option to rent Virtual Private Servers (VPS) or dedicated physical servers, mainly located in Europe. There is also the flexibility to establish servers in other countries upon request. For services in Switzerland, LUCY partners with Hosttech.

**EU Data Centers**

LUCY Security uses Hetzner Online's data centers, a trusted provider since 1997. With data centers in Germany and Finland, Hetzner boasts DIN ISO/IEC 27001 certification for its ISMS. Their cloud servers feature AMD EPYC 2nd Gen and Intel® Xeon® Gold processors with fast NVMe SSDs.

Standard Virtualized Private Server configurations include 8 vCPUs, 16 GB RAM, 240 GB SSD, and 20 TB Traffic.

**US Data Center**

Through Hetzner Online, LUCY Security extends its hosting services to the US, specifically to Ashburn, Virginia, within the Data Center Alley. Clients can request a VPS in this region by specifying a preference for the US zone.

**High Availability**

Despite efforts to maintain uninterrupted service, potential downtime risks include DDoS attacks, power failures, and compromised client servers. LUCY's infrastructure is monitored 24/7 from multiple global locations, ensuring rapid response to issues. The VPS services have a 99.9% annual availability guarantee, allowing for up to 9 hours of potential downtime per year.

**Advantages of LUCY's VPS/Dedicated Servers**

Opting for LUCY's VPS or dedicated server hosting provides several benefits:

* **Bandwidth**: A guaranteed bandwidth of 1 Gbyte.
* **Public IP Address**: Reduces the risk of your infrastructure being blacklisted.
* **Dedicated Full Root Access**: With an optimized operating system for peak performance.
* **DNS Management**: Creation of necessary DNS entries to mitigate SPAM issues.
* **Direct Access**: Ensures servers are not blocked by pre-existing security solutions.
* **Application Checks**: Comprehensive testing to ensure seamless LUCY operation.

</details>

* **Reduced Attack Surface**: Placing LUCY on the internet eliminates the need to modify internal firewall settings, aligning with secure zone principles and minimizing attack vectors.
* **Simplified Integration**: Cloud-based LUCY servers are quicker to set up, facing fewer integration challenges with existing email, DNS, and firewall configurations.
* **Direct Access**: Hosting servers in the cloud bypasses internal security obstacles, ensuring uninterrupted access.
* **Public IP Address**: A cloud server provides a public IP address outside your network range, reducing the risk of having your infrastructure blacklisted.

### **On-Premise Installation Advantages:**

* **Enhanced Security**: Hosting LUCY internally utilizes the existing security infrastructure (IDS, firewalls, etc.) to protect sensitive data (login credentials, usernames, emails) from unauthorized access.
* **Integration with Backend Systems**: LUCY seamlessly integrates with various APIs (LDAP, REST, etc.) that are secured within the internal network and not exposed to the internet.
* **Compliance with Legal Requirements**: Regulations like GDPR in Europe may restrict storing sensitive data on external servers, making on-premise installations necessary.

### **Placement in an On-Premise Installation:**

For on-premise setups, LUCY can be deployed within the intranet or a secured zone (DMZ). However, granting secure access for external users (e.g., mobile devices accessing phishing simulations or e-learning modules) directly from the intranet poses security risks. A web server exposed to the internet could serve as an entry point for attackers if vulnerabilities are exploited.

### **Recommended Configuration for On-Premise Deployment**:

* **Reverse Proxy Setup**: Use a LUCY instance as a reverse proxy in the DMZ, with the main application hosted securely within the intranet as the "master instance". This setup provides an extra layer of security by managing external access while keeping the core application protected inside the internal network.
* **DMZ Installation**: For better security, install LUCY in a separate, secure zone within the DMZ. This configuration reduces direct exposure to the intranet.

{% hint style="info" %}
See our platform reference article on [Master/Slave deployment](../../application-screens-reference/settings/common-system-settings/web-proxy.md)
{% endhint %}
