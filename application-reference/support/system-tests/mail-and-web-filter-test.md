# Mail and Web Filter Test

### Introduction

The Mail and Web Filter Test provides valuable insights into how effectively your mail server and web proxy handle various types of test files. This test helps you evaluate whether your filters can detect and block potential malicious content, such as Java files, backdoors, scripts, and embedded Office objects. By understanding your current protection level, you can refine your security measures and conduct more targeted phishing simulations to enhance your overall defense strategy.

{% hint style="info" %}
Navigate to **Support -> System Tests -> Mail & Web Filter Test**
{% endhint %}

***

### Required templates

The mail and web filter test is a special type of campaign that requires a specific attack template.\
Be sure to download the template before creating the test:

<figure><img src="../../../.gitbook/assets/image (860).png" alt=""><figcaption></figcaption></figure>

***

### How to run the test

#### Campaign settings

First give the test campaign a name and client. Leave the **Setup Mode** set to **Mail & Web Test**, and optionally pin the campaign or enable delete-protection. When you're ready, click **Save.**

<figure><img src="../../../.gitbook/assets/image (862).png" alt=""><figcaption></figcaption></figure>

#### Mail settings

After saving the campaign settings the page refreshes automatically, and you are now within the mail and web filter campaign settings. Configure the mail delivery settings for the test and click **Save** again.

{% hint style="warning" %}
Your sender email domain **must** point to your Lucy server in order for the test to work.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (864).png" alt=""><figcaption></figcaption></figure>

#### Scenario settings

Once again the page will refresh after saving the mail settings.\
Click **Edit Scenario Settings** for the test scenario to edit your test configuration:

<figure><img src="../../../.gitbook/assets/image (865).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Scenario settings" %}
Select a domain to host the test files, optionally using a single subdomain. Just like with other attack scenarios, be sure to select a domain other than your Lucy admin domain. Click **Save** again.

{% hint style="info" %}
To ensure email delivery it's best to select the same domain here that you entered for the sender email above.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (868).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Mail settings" %}
For this test your system settings should be sufficient. However, if you want to test some other mail delivery system that is not your default system setting you can change it here.

<figure><img src="../../../.gitbook/assets/image (869).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="SSL settings" %}
Since we are (hopefully) not running this test off the admin domain we need to ensure the hosting domain has proper SSL applied. This will be especially relevant when you need to download the files off the hosting domain.

[If your domain doesn't have SSL be sure to generate or upload a certificate on the SSL page.](../../settings/common-system-settings/ssl-settings/)

Select or generate your SSL certificate and click **Save** to apply.

<figure><img src="../../../.gitbook/assets/image (871).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="undefined" %}
Here you can select from an extensive list of file types that simulate various malicious behaviors. Each category can be enabled/disabled globally, or you can enable/disable each file individually within a category. By default every category and file is enabled.

{% hint style="info" %}
Click a category to expand it and view the files, plus an overview of the category.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (872).png" alt=""><figcaption></figcaption></figure>

When you've selected the files you wish to enable click **Save** to apply your choices.
{% endtab %}
{% endtabs %}

### Customizing the test template

The Mail & Web Test template can be edited like a file template - navigate to **Templates > Attack Templates** and search for "Mail & Web Test", then select **Edit Template.** Switch to the **File List** page to see the classes and files included in the template.

<figure><img src="../../../.gitbook/assets/image (873).png" alt=""><figcaption></figcaption></figure>

Here you can create and organize the different classifications for your files. You can also edit each file individually - click any file to download it. You can then upload the file with your changes, or even upload a totally custom file. To remove a file, simply click the green **X** symbol on the file's row.

Be sure to **Save** all changes when you're done!
