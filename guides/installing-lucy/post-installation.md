# Post Installation

## Using the setup script

Access your Lucy container and execute the setup script:

Lucy version 5.2.1 and below:

```
docker exec -it lucy python /opt/phishing/current/tools/setup/setup.py
```

Lucy version 5.3 and above:

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

### Create an Administrative user

Select **Users** (6), then select **Add User** (2).

<figure><img src="../../.gitbook/assets/image (423).png" alt=""><figcaption></figcaption></figure>

### Configure the administrative domain

Select **Base Task** (5) and enter a domain you own.

<figure><img src="../../.gitbook/assets/image (422).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Ensure all relevant [DNS records](../../application-screens-reference/settings/common-system-settings/domains/#dns-records-explained) are pointing to your Lucy server.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (426).png" alt=""><figcaption></figcaption></figure>

***

### Get your server licensed

Licensing restrictions currently limit some configuration options on your Lucy server. To start the licensing process, please contact your Account Manager and provide your Lucy [workstation ID](../../application-screens-reference/account-settings/license.md#workstation-id).

Once a license has been assigned to your workstation, you can sync the details by going to **Support -> Update** and clicking **Check Update**.

***

### Initial Lucy configuration

* [x] [Configure mail delivery.](../../application-screens-reference/settings/common-system-settings/mail-settings.md)
* [x] [Set up a domain for phishing simulations or the e-learning portal.](../../application-screens-reference/settings/common-system-settings/domains/)
* [x] [Create a trusted SSL certificate.](../../application-screens-reference/settings/common-system-settings/ssl-settings/)
* [x] [Create administrator users.](../../application-screens-reference/users/administrative-users.md)
* [x] [Download the latest templates.](../../application-screens-reference/templates/download-templates.md)
* [x] [Implement additional security layers.](../../application-screens-reference/settings/common-system-settings/firewall.md)
* [x] [Customize portal branding and 404 pages.](../../application-screens-reference/settings/whitelabeling.md)
* [x] [Set up your first campaign.](../quick-guides/create-your-first-campaign/)

***

### Uninstall LUCY

1. **Legacy Installation (Debian OS, Lucy <= v4.8.7):**
   * List installed packages:

```
 awk '/^Selecting/ {gsub(/\./,""); print $5}' /var/log/apt/term.log
```

* Remove packages accordingly.

1. **Docker Installation:**
   * Stop the container:

```
docker stop lucy
```

* Remove the container:

```
docker container rm lucy
```

***

### Support

For installation assistance, please get in touch with our [Technical Support](../../when-to-contact-us/contact-technical-support.md) team.
