# Network Communication

LUCY may initiate or require certain communication channels to servers on the internet.\
Below is an overview of these requirements.

***

## Outbound Communication

### General Communication Types

1. **First-Time Use**: During the first installation, LUCY connects via HTTP to obtain the workstation key and ID. No data beyond the current build version is transmitted.
2. **Updates**: LUCY connects to our update server and Ubuntu repository mirror.
3. **SSH**: When SSH is enabled via the Help menu, LUCY initiates an outbound SSH connection to our SSH Jump Host. This feature is disabled by default.
4. **Campaign Checks**: LUCY connects to fixed servers to test campaign settings and internet reachability via HTTP/HTTPS. No data is transmitted during these tests.
5. **Campaign Execution**: LUCY may communicate via SMTP (Port 25 or 465) when sending emails over the internet.
6. **Vulnerability Detection**: To enable this feature, allow Port 80 access to `static.nvd.nist.gov` (129.6.13.177) for downloading the NIST CVE database.

### Outbound Ports & IPs

| IP Address/Domain                           | Function                             | Port   | Protocol |
| ------------------------------------------- | ------------------------------------ | ------ | -------- |
| 162.55.130.83 (update.phishing-server.com)  | Update/License Server, HTTP Proxy    | 80/443 | TCP      |
| 162.55.130.83 (update.phishing-server.com)  | Linux Repository                     | 80     | TCP      |
| 8.8.8.8 (or any DNS server)                 | DNS Server                           | 53     | UDP      |
| nvd.nist.gov                                | NIST CVE Database (Optional)         | 443    | TCP      |
| 0.0.0.0 (Any)                               | Mail Communication (Optional)        | 25     | TCP      |
| 116.203.185.12 (changelog.lucysecurity.com) | Fetch Update News (Optional)         | 80     | TCP      |
| is.gd                                       | URL Shortening Service (Optional)    | 443    | TCP      |
| api-ssl.bitly.com                           | URL Shortening Service (Optional)    | 443    | TCP      |
| api.authy.com                               | Two-Factor Authentication (Optional) | 443    | TCP      |

{% hint style="warning" %}
LUCY version ≥ 5.0 requires dynamic IP access to `update1.phishing-server.com`.\
Create an allow rule for the domain name.
{% endhint %}

***

## Inbound Communication

To access LUCY from the internet, specific ports must be open:

| Source IP | Destination         | Port                | Protocol | Comment                                                            |
| --------- | ------------------- | ------------------- | -------- | ------------------------------------------------------------------ |
| ANY       | Your LUCY Server IP | 80/443 (HTTP/HTTPS) | TCP      | Required for accessing landing pages and certificate verification. |
| ANY       | Your LUCY Server IP | 25 (SMTP)           | TCP      | Only needed for catching email replies.                            |

***

## Malware Simulation Communication

The malware simulation tool uses the default browser (in hidden mode) to send collected data to LUCY via HTTP or HTTPS. For SSL-enabled campaigns, HTTPS is used automatically. The tool is compatible with environments requiring proxy authentication for internet access.
