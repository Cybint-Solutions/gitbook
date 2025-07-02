# Domains

**Introduction:** LUCY supports multiple domain names for campaigns on virtualized servers. Users can add domains via the registration wizard or request assistance from our [support department](../../../../when-to-contact-us/contact-technical-support.md).\
\
**What type of domains can be configured?**\


<details>

<summary>Administrative Domain </summary>

This is the domain used for hosting your Lucy Administrative panel.\
\
![](<../../../../.gitbook/assets/image (208).png>)\
\
**VPS customers** will receive a server with a generic domain, for example -> access.cloudserver123.com - If you would like to host your Lucy VPS with a custom domain, please send a request to our [support department](../../../../when-to-contact-us/contact-technical-support.md) for assistance.\
\
**On-premise / Self-hosted** customers will be able to configure a custom domain in the setup script phase of the [installation process](../../../../guides/installing-lucy/installing-lucy.md).

</details>

<details>

<summary>Phishing Simulation Domains</summary>

These domains are used to spoof legitimate domains to assess the attentiveness of the user interacting with the simulated attack.\
\
These domains can be registered via the domain wizard or by pointing a pre-owned domain to your Lucy server.

</details>

<details>

<summary>Awareness Training Domains</summary>



</details>

### **Register a domain via the Domain Registration Wizard:**

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> Domains**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (202).png" alt="" width="375"><figcaption></figcaption></figure>

On the Domain page, you have two options to add a domain, **Register** and **Add**:

<details>

<summary>Why do you need to register an Attack Domain?</summary>

Registering an attack domain serves two key purposes. \
\
Firstly, it enables the creation of domains resembling the targeted organization in simulations, such as using "mirconsoft.com" instead of "microsoft.com," enhancing the realism of the simulation. \
\
Secondly, it prevents blacklisting of the Lucy system domain. Since domains can be blacklisted for low reputation or short existence, using a separate attack domain safeguards your Lucy server's System domain and ensures the effectiveness of future campaigns.

</details>

### **Register**

Registering a domain through the Domain Registration Wizard is both fast and streamlined. The wizard will initiate an API call to GoDaddy, the domain registrar, to configure all relevant DNS records. This setup enables hosting of landing pages, sending emails from the Postfix server on behalf of the domain, and receiving replies directed to the domain.

<figure><img src="../../../../.gitbook/assets/image (203).png" alt=""><figcaption></figcaption></figure>

This option will allow you to submit a domain name to check for availability, if the domain is available you will be redirected to the domain registration page.&#x20;

{% hint style="danger" %}
Please ensure the information provided on the registration form is accurate, especially the email address. This is crucial because all communications from the registrar and access to the domain's DNS portal will be limited to the email address submitted in the registration process.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (204).png" alt=""><figcaption></figcaption></figure>

### **Add a Domain**

To add a domain you already own, simply click the "Add" button and enter your domain name:

<figure><img src="../../../../.gitbook/assets/image (205).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (206).png" alt=""><figcaption></figcaption></figure>

### **Prerequisites for Adding a Custom Domain**

Please be aware that when adding a domain to Lucy, you are required to manually create all relevant DNS entries in the registrar's administration panel. This step is necessary for the domain to properly point to the Lucy server, enabling it to send and receive emails associated with this domain.\
\
For Example, to point all relevant DNS records of the domain "lucysecurity.help" to my Lucy server, with the server's IP address being 65.109.169.227, the following DNS records will be added (_replace the IP address with your Lucy server IP address_):\


| Type       | Host | Value                           | TTL               | Priority |
| ---------- | ---- | ------------------------------- | ----------------- | -------- |
| A Record   | @    | 65.109.169.227                  | Automatic/Default |          |
| A Record   | \*   | 65.109.169.227                  | Automatic/Default |          |
| TXT Record | @    | v=spf1 ip4:65.109.169.227 \~all | Automatic/Default |          |
| TXT Record | \*   | v=spf1 ip4:65.109.169.227 \~all | Automatic/Default |          |
| MX Record  | @    | mail.lucysecurity.help          |                   | 10       |

<details>

<summary>DNS records explained</summary>

* **A Record with "@"**: This record connects your main domain (like "lucysecurity.help") directly to an IP address, which is the unique number assigned to your Lucy server on the internet. Think of it as telling the internet where your website's home is.
* **A Record with "\*" (Wildcard)**: This is similar to the above, but it's for all subdomains of your website. A subdomain is anything that comes before your main domain, like "blog.lucysecurity.help" or "shop.lucysecurity.help". This record means that no matter what subdomain someone types in, they'll be directed to your Lucy server.
* **TXT Record with "@"**: This is a note attached to your domain that helps with email delivery. It specifies which servers are allowed to send emails from your domain, helping to prevent spammers from using your domain to send fake emails.
* **TXT Record with "\*" (Wildcard)**: This applies the same email delivery rules as the previous record, but for all subdomains of your domain.
* **MX Record with "@"**: This tells the internet where to deliver emails for your domain. It points to an address that handles all your email messages, ensuring that when someone sends an email to "@lucysecurity.help", it goes to the right place.

The "Priority" number for MX records tells the internet which server to try first; lower numbers are tried before higher ones.

</details>

### Custom 404 page for Domain

Users may receive random links during phishing simulations, leading to a 404 error if they visit the domain directly. To prevent LUCY from revealing itself, define a custom error message or homepage.&#x20;

{% hint style="warning" %}
Note that if you use an IP address instead of a domain, the custom 404 page will not be displayed.
{% endhint %}

#### Enable "Use custom not found template"

<figure><img src="../../../../.gitbook/assets/image (629).png" alt=""><figcaption></figcaption></figure>

Select the tab for "Not found template"

<figure><img src="../../../../.gitbook/assets/image (630).png" alt=""><figcaption></figcaption></figure>

Use the editor to create your not-found template:

<figure><img src="../../../../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>
