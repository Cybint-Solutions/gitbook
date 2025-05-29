# End User Portal Settings

## Introduction

Enduser portal settings pertain to recipients with access to view their training exercises in a dedicated portal. This article focuses on configuring the parameters of the portal that end users log into.

{% hint style="info" %}
See our reference article on [End Users](end-users.md).
{% endhint %}

***

## Configuration

{% hint style="info" %}
Navigate to **Users -> Enduser Portal Settings**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (790).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Networking" %}
#### Domain

By default, your end-user portal will be hosted on the same domain as your administrative domain. For example if your server address is `https://lucyserver.com`, the portal login will be `https://lucyserver.com/user/`.

You can change the domain to any domain added to your Lucy server. Ensure all relevant [DNS records](../settings/common-system-settings/domains/#dns-records-explained) are set up for custom domains.

#### Subdomain

Lucy offers the optional configuration of a subdomain, often used with custom domains. This allows you to point DNS records at the subdomain level to the IP address of the Lucy server. For example:\
\
`https://training.lucyserver.com/user/`

{% hint style="warning" %}
Only single-level subdomains are allowed.
{% endhint %}

#### SSO Considerations

End-user portal SSO (SAML 2.0) authentication will not work if you change the domain to anything other than the system domain.

#### Port

Hosting the end-user portal at a custom port might be done for several reasons:

* **Security**: Using a non-standard port can reduce the likelihood of automated attacks targeting common ports.
* **Compliance**: Some organizational policies or regulatory requirements might mandate the use of specific ports for certain services.
* **Load Balancing**: Distributing traffic across multiple ports can help manage load and ensure better performance.
{% endtab %}

{% tab title="Name" %}
Give your End User portal a company-specific name.\
This name will appear on the login page in the "Welcome to..." banner.
{% endtab %}

{% tab title="Widgets" %}
Control what the end-user sees in their portal; each section is known as a "Widget."\
This option allows an administrator to deactivate certain sections.

<figure><img src="../../.gitbook/assets/image (611).png" alt="" width="377"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Layout" %}
### Text-based Layout

<figure><img src="../../.gitbook/assets/image (613).png" alt=""><figcaption></figcaption></figure>

### Thumbnails Layout

<figure><img src="../../.gitbook/assets/image (614).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Language" %}
Specify the default language of the portal:

<figure><img src="../../.gitbook/assets/image (445).png" alt="" width="552"><figcaption></figcaption></figure>

Additionally, the end-user can select their preferred language from the dropdown menu:

<figure><img src="../../.gitbook/assets/image (446).png" alt="" width="563"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Logo" %}
Upload a custom logo for your end-user portal.\
This logo will appear in the top-left corner of the portal pages.
{% endtab %}
{% endtabs %}

## SSL

If you are hosting the portal on a different domain than your admin domain, or you are hosting on a different subdomain and have specific SSL for each subdomain, you can apply SSL here:

<figure><img src="../../.gitbook/assets/image (948).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
You must first generate or upload the SSL certificate in the [SSL Settings](../settings/common-system-settings/ssl-settings/).
{% endhint %}
