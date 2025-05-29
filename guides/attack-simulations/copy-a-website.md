# Copy a Website

Real phishing content often attempts to copy the appearance of a legitimate web page, and you may want to do the same with your simulated attacks. To assist with this, attack templates have a copy feature for quickly inserting existing web content into your template.

{% hint style="info" %}
Navigate to **Attack Templates -> Edit Template -> Landing Page Template**
{% endhint %}

{% hint style="success" %}
This feature works best with a blank template.
{% endhint %}

***

## Preparing the template

Since we are copying a whole webpage, starting with a blank template is best.

Make a copy of one of the blank templates:

<figure><img src="../../.gitbook/assets/image (910).png" alt=""><figcaption></figcaption></figure>

Now select the copy and make the necessary changes to the template details like name, description, languages, etc. When you're ready go to the **Landing Page Template** for the next steps.

***

## Copying index.html

In this example we'll be copying the Lucy login page:

```
https://<lucy_domain>.com/admin/login
```

Switch the **Language** field to your desired language, then select **Copy Webpage**.

<figure><img src="../../.gitbook/assets/image (913).png" alt=""><figcaption></figcaption></figure>

Fill out the details of your target web page, select `index.html` as the file, and click **Start** when ready.

<figure><img src="../../.gitbook/assets/image (954).png" alt=""><figcaption></figcaption></figure>

Once the copy is finished you can return to the template editor to see your content loaded in to the file.

{% hint style="info" %}
You can also click **Preview** to check the appearance in your browser.
{% endhint %}

***

## Copying other pages

To copy a webpage to a new file follow the same steps as above and select **New File** instead of `index.html`. Let's copy the password reset page to go along with our login page.

<figure><img src="../../.gitbook/assets/image (957).png" alt=""><figcaption></figcaption></figure>

### Configuring links and other elements

Since we're copying these pages from their source, links and other elements on the page still point to the real URLs from the website we copied. For example, the **Forgot Password?** button will still take the user to the real password recovery page. These links need to be adjusted to work with your template.

If you are linking to another page in your template, simply use the filename as the URL:

<figure><img src="../../.gitbook/assets/image (956).png" alt=""><figcaption></figcaption></figure>

Similarly, the login form will need to be adjusted to work with a Lucy simulation by setting the form action to `?login`. Be sure to create a file named `account.html` with a simple error message or other content for the user.

{% hint style="info" %}
Since this is an attack template it makes sense to just set every link to the `%link%` variable.
{% endhint %}
