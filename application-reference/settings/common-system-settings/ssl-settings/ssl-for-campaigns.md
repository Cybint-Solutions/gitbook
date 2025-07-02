# SSL for Campaigns

When setting up SSL for attack simulations or awareness training, you have several options: you can generate a new certificate, upload an existing one, or select one that's already been generated. To ensure the certificate is trusted and to avoid SSL error messages, it's recommended to choose "Let's Encrypt". Here's how to configure it:

1. Navigate to the scenario settings within your campaign, and then click on "SSL settings".
2. If you opt for Let's Encrypt, the system will automatically use the domain you've configured within the scenario settings.
3. Remember, Let's Encrypt requires a publicly accessible domain name to issue a certificate. Make sure your domain is not only accessible but also points to your Lucy server to facilitate this process. For more information, please see our [domain configuration guide.](../domains/#dns-records-explained)

<figure><img src="../../../../.gitbook/assets/image (195).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
When you activate SSL in your campaign scenario on LUCY, the system automatically updates the `%link%` variable within your message template to use "https://" instead of "http://".
{% endhint %}
