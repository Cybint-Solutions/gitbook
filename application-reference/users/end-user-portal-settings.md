# End User Portal Settings

## Introduction

End User Portal Settings apply to recipients who can access and view their training exercises through the [**End User Portal**](end-users/end-user-portal-overview.md).

This section explains how to configure the settings that control the portal used by end users to log in and review their training activity.

{% hint style="info" %}
For more information about end users, see our reference article on [End Users](end-users/).
{% endhint %}

***

## Portal Settings

{% hint style="info" %}
Navigate to **Users > End User Portal Settings**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Domain" %}
Controls which domain is used to access the End User Portal.

Available options:

* **System Domain** – Uses the same domain as the Lucy admin interface.
* **Custom Domain** – Uses the domain specified in the **Custom Domain** field.
* **Local IP** – Uses the server's internal IP address.
* **External IP** – Uses the server's external IP address.
* **Registered Domains** – Any [domains configured in the system](../settings/common-system-settings/domains/) will appear in this list.
* **Register New Domain** – Opens the option to [register a new domain](../settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard).

**Custom Domain**

Specifies the custom domain used when **Custom Domain** is selected.

If you use a subdomain, only **one subdomain level** is supported.

Example:

* **my.lucyserver.com** – supported
* **my.awesome.lucyserver.com** – not supported

{% hint style="info" %}
#### SSO Warning

If you plan to use **SSO** to authenticate end users, the **System Domain** must be used.
{% endhint %}
{% endtab %}

{% tab title="Portal Name" %}
This name appears in the portal header.
{% endtab %}

{% tab title="Widgets" %}
Controls which information sections are visible in the [End User Portal dashboard](end-users/end-user-portal-overview.md).

Available widgets:

* User Profile
* Attack Simulation Stats
* Personal Reputation Profile
* Reputation Historical Stats
* Awareness Stats
* Available Trainings
* Trainings History
* Training Diplomas
{% endtab %}

{% tab title="Layout" %}
Determines how training courses are displayed in the portal.
{% endtab %}

{% tab title="Language" %}
Sets the default language for the End User Portal.

If you enable the checkbox, Lucy will detect and apply the user's browser language.
{% endtab %}

{% tab title="Logo" %}
You can upload a custom logo for the End User Portal.

This logo appears in the top-left corner.
{% endtab %}
{% endtabs %}

***

## SSL Settings

If the portal is hosted on a **different domain** than the admin portal, or on a **separate subdomain with its own SSL certificate**, you can configure SSL for the portal in this section.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Before applying SSL here, you must first **generate or upload the SSL certificate** in the [**SSL Settings**](../settings/common-system-settings/ssl-settings/).
{% endhint %}
