# Post Installation Setup

## Using the setup script

Access your Lucy container and execute the setup script:

**Lucy version 5.2.1 and below**

```
docker exec -it lucy python /opt/phishing/current/tools/setup/setup.py
```

**Lucy version 5.3 and above**

```
docker exec -it lucy python3 /opt/phishing/current/tools/setup/setup.py
```

{% hint style="success" %}
The default name for the container is `lucy`.\
If you named it something else, use that name in the command above.
{% endhint %}

You can also run the setup script at any time from within the container using:

```
sudo python /opt/phishing/current/tools/setup/setup.py
OR
sudo python3 /opt/phishing/current/tools/setup/setup.py
```

The script starts with this menu:

<figure><img src="../../.gitbook/assets/image (974).png" alt=""><figcaption></figcaption></figure>

## Create an administrative user

Select **Users** (6), then select **Add User** (2).

<figure><img src="../../.gitbook/assets/image (423).png" alt=""><figcaption></figcaption></figure>

## Configure the administrative domain

Select **Base Task** (5) and enter a domain you own.

<figure><img src="../../.gitbook/assets/image (422).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Ensure all relevant [DNS records](../../application-reference/settings/common-system-settings/domains/#dns-records-explained) are pointing to your Lucy server.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (426).png" alt=""><figcaption></figcaption></figure>

***

## Get a license

Licensing restrictions currently limit some configuration options on your Lucy server. To start the licensing process, please contact your Account Manager and provide your Lucy [workstation ID](../../application-reference/account-settings/license.md#workstation-id).

Once a license has been assigned to your workstation, you can sync the details by going to **Support > Update** and clicking **Check Update**.

***

## Initial Lucy Configuration

* [x] [Configure mail delivery.](../../application-reference/settings/common-system-settings/mail-settings.md)
* [x] [Set up a domain for phishing simulations or the e-learning portal.](../../application-reference/settings/common-system-settings/domains/)
* [x] [Create a trusted SSL certificate.](../../application-reference/settings/common-system-settings/ssl-settings/)
* [x] [Create administrator users.](../../application-reference/users/administrative-users.md)
* [x] [Download the latest templates.](../../application-reference/templates/download-templates.md)
* [x] [Implement additional security layers.](../../application-reference/settings/common-system-settings/firewall.md)
* [x] [Customize portal branding and 404 pages.](../../application-reference/settings/whitelabeling.md)
* [x] [Set up your first campaign.](../quick-guides/create-your-first-campaign/)
