# Whitelabeling

### Introduction

LUCY's licensing model supports reselling and external testing, with options to customize the software's visual appearance.

***

### Configuration

{% hint style="info" %}
Navigate to **Settings -> Whitelabeling**
{% endhint %}

<figure><img src="../../.gitbook/assets/image (637).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Software Name" %}
Customize the software name that appears on the login page.

<figure><img src="../../.gitbook/assets/image (626).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Admin Path" %}
Modify the default admin interface path (the default is "/admin").

<figure><img src="../../.gitbook/assets/image (627).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Custom link to Manual" %}
The default LUCY WIKI is accessible to admins and view-only users. To hide the WIKI or create a custom manual with your corporate design, go to advanced settings and define your manual's link (e.g., `http://yourserver.com/manual`).
{% endtab %}

{% tab title="Commercial Contact" %}
This is the email contact information for your organization's commercial contact. It provides insights to LUCY account managers regarding communication channels.
{% endtab %}
{% endtabs %}

#### Not Found Template

Users may receive random links during phishing simulations, leading to a 404 error if they visit the domain directly. To prevent LUCY from revealing itself, define a custom error message or homepage in the settings.&#x20;

<figure><img src="../../.gitbook/assets/image (628).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
Note that if you use an IP address instead of a domain, the custom 404 page will not be displayed.
{% endhint %}

When you save a new domain in LUCY, you can set a custom 404 or homepage for that specific domain, overriding the global 404 settings. Please see our platform reference article on [Domain 404 pages](common-system-settings/domains/#enable-use-custom-not-found-template).

{% hint style="info" %}
If you want to reset the custom 404 template, select "Restore Default" to display the default 404 page.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Logo" %}
Upload your custom logo for your LUCY server. It will be displayed on the login page and in the top banner of your dashboard.

<figure><img src="../../.gitbook/assets/image (633).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Favicon" %}
A favicon, short for "favorite icon," is a small graphic associated with a website or web page. It is typically displayed in the browser's address bar, bookmarks, and tabs, helping users quickly identify the website. Favicons are usually 16x16 pixels or 32x32 pixels in size and can be in various formats such as ICO or PNG.

<figure><img src="../../.gitbook/assets/image (634).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Copyright" %}
Uploading copyright information for a LUCY server protects your intellectual property and enhances professionalism. It also informs users about ownership and legal rights, reinforcing brand identity. Copyright information will be displayed at the footer of every page.
{% endtab %}

{% tab title="Banner Settings" %}
Uploading a custom development banner will ensure it is displayed on all template editing pages.

<figure><img src="../../.gitbook/assets/image (635).png" alt=""><figcaption></figcaption></figure>

This banner will display on any template editing page:

<figure><img src="../../.gitbook/assets/image (636).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}
