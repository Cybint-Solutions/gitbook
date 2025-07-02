# URL Shortener Settings

## Introduction

The **URL Shorteners Settings** page allows administrators to manage which URL shortening services are available and active within Lucy for use in phishing simulations and other messaging campaigns.

{% hint style="info" %}
Navigate to **Settings > Common System Settings > URL Shortener Settings**
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (987).png" alt=""><figcaption></figcaption></figure>

***

## Default Shorteners

Lucy comes with two shorteners pre-configured; [bit.ly](https://bitly.com/pages/landing/url-shortener) and [is.gd](https://is.gd/).

These services are ready to use and cannot be edited.

***

## Custom Shortener

Administrators can configure a custom URL shortening service for use in Lucy campaigns. This feature enables the integration of proprietary or third-party shorteners when embedded services are not suitable.

### Settings

<table data-header-hidden><thead><tr><th width="193.55560302734375"></th><th></th></tr></thead><tbody><tr><td><strong>Name</strong></td><td>Internal label for the shortener (e.g., <code>custom</code>).</td></tr><tr><td><strong>Shortener URL</strong></td><td>Endpoint to which Lucy will send requests for generating shortened URLs.</td></tr><tr><td><strong>Method</strong></td><td>HTTP method used for the request (<code>GET</code> or <code>POST</code>).</td></tr><tr><td><strong>Active</strong></td><td>Enables or disables the shortener for use in the platform.</td></tr><tr><td>Body Parameter Name</td><td>Specifies the key used in the JSON body of the request.<br>Example:<code>{ "url": "https://example.com/long/link" }</code></td></tr><tr><td>Response Type</td><td>Determines how the response is extracted (<code>JSON</code> or <code>TEXT</code>).</td></tr></tbody></table>
