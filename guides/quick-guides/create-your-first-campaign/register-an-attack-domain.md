# Register an Attack Domain

<details>

<summary>Why do you need to register an Attack Domain?</summary>



Registering an attack domain serves two key purposes:

1. Enables creating domains resembling the targeted organization, enhancing realism (e.g., "mirconsoft.com" instead of "microsoft.com").
2. Prevents blacklisting of the Lucy system domain, safeguarding your server and ensuring effective future campaigns.

</details>

Configuring an attack domain in Lucy is simplified with our GoDaddy API integration, which automatically sets up DNS records for email sending and landing page hosting.

{% hint style="info" %}
Navigate to **Settings -> Common System Settings -> Domains**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

Select "Register"\
\
Enter the modified "spoofed" domain you would like to use and check whether it is available for registration. When the check is complete you will be taken to the registration page.

<figure><img src="../../../.gitbook/assets/image (228).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Provide a valid email address for WHOIS validation, domain expiration alerts, and DNS management access. Ensure accurate details when registering your domain as it is linked to your organization.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (229).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
After registering your domain, the automatic DNS configuration typically completes within minutes. However, in very rare cases, it may take 4 to 8 hours for all DNS servers to fully propagate.
{% endhint %}
