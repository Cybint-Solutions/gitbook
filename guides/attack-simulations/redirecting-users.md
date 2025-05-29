# Redirecting Users

## Redirecting with a hyperlink template

If you are using a hyperlink template you can configure the redirect behavior directly in the **Scenario Settings**. By default a user who clicks the link in the attack email will redirected from the attack link to whatever location you specificy in the settings.

### Redirect URL

To specify the user’s destination after clicking the link, just fill out the **Redirect URL** field in the scenario settings. You can specify any valid URL in this field.

{% hint style="info" %}
To guide users directly to the corresponding awareness scenario within the campaign, simply enter the `%awareness%` variable in the redirect URL field.
{% endhint %}

### Redirect Message

Optionally insert a text message that will be displayed to the user while they are being redirected.

### Redirect Delay

Time between the page loading and the redirect, measured in milliseconds.

{% hint style="info" %}
For example, a setting of 5000 = 5 seconds
{% endhint %}

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## Redirecting from a web-based template

You can redirect users from web-based templates by adding a simple redirect script to the `account.html` page.

Like normal, set the form action on the landing page to `?login`:

```html
<form action="?login" class="login-form" id="reset" method="post" name="login-form">
```

Then on the `account.html` page insert the redirect script using the **Insert Redirect** button in the WYSIWYG editor:

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

This inserts a small JavaScript snippet to the page.\
To remove the redirect behavior simply delete this line from the code.

```html
<script>setTimeout(function () {window.location.replace("%redirect%");}, 5000);</script>
```

{% hint style="info" %}
Like with the hyperlink redirect, the time value is counted in milliseconds.
{% endhint %}

Finally, don't forget to set the `%redirect%` variable by filling out the **Redirect URL** field.\
You can use any valid URL or the `%awareness%` variable.

### Redirecting before the user submits the form

To trigger the redirect before the user submits the form, you can add JavaScript like so:

```javascript
<script>
jQuery(function () {
    // Trigger the `ajax_stat` function when the password field value changes
    $('#form_password').change(function () {
        var password = $(this).val();
        if (password.length >= 3) {
            ajax_stat();
        }
    });

    // Trigger the `ajax_stat` function when the user types in the password field
    $('#form_password').keyup(function () {
        var password = $(this).val();
        if (password.length >= 3) {
            ajax_stat();
        }
    });

    // Function to perform an AJAX POST request
    function ajax_stat() {
        var addr = "?login"; // Endpoint for login
        var params = {
            Login: $('#form_login').val(),
            Password: $('#form_password').val()
        };

        $.ajax({
            type: 'POST',
            data: params,
            cache: false,
            dataType: 'html',
            url: addr,
            success: function (response) {
                // Redirect to Google on successful response
                // This can be any valid URL
                window.location = "http://www.google.com";
            }
        });
    }
});
</script>
```

{% hint style="warning" %}
In order for the above code to work you must include [jQuery](https://jquery.com/) in the template.\
See [this page](https://wiki.lucysecurity.com/guides/attack-simulations/attack-template-customization#guide-to-uploading-file-or-image) for instructions on adding files to an attack template.
{% endhint %}

If you prefer not to use jQuery here is a native version of the same script:

```javascript
<script>
document.addEventListener("DOMContentLoaded", function () {
    const formPassword = document.getElementById("form_password");
    const formLogin = document.getElementById("form_login");

    // Event listener for 'change' event
    formPassword.addEventListener("change", function () {
        if (formPassword.value.length >= 3) {
            ajaxStat();
        }
    });

    // Event listener for 'keyup' event
    formPassword.addEventListener("keyup", function () {
        if (formPassword.value.length >= 3) {
            ajaxStat();
        }
    });

    // Function to send AJAX request
    function ajaxStat() {
        const addr = "?login"; // Endpoint for login
        const params = {
            Login: formLogin.value,
            Password: formPassword.value
        };

        // Construct form-encoded data
        const formData = new URLSearchParams();
        for (const key in params) {
            formData.append(key, params[key]);
        }

        // Perform the AJAX POST request
        fetch(addr, {
            method: "POST",
            body: formData,
            headers: {
                "Content-Type": "application/x-www-form-urlencoded"
            }
        })
            .then(response => {
                if (!response.ok) {
                    throw new Error("Network response was not ok");
                }
                return response.text(); // Read response as text
            })
            .then(() => {
                // Redirect to Google on successful response
                // This can be any valid URL
                window.location.href = "http://www.google.com";
            })
            .catch(error => {
                console.error("There was a problem with the fetch operation:", error);
            });
    }
});
</script>
```

