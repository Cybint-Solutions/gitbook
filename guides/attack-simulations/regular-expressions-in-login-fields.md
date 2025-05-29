# Regular Expressions in Login Fields

### Introduction

Lucy can create phishing scenarios where users are prompted to [login on a landing web page](attack-types/data-entry-attack.md). To ensure that only valid logins are counted as successful attacks, Lucy allows you to define regular expressions within the login field, which serve as filters for login criteria. These criteria can include requirements such as:

* Passwords containing at least two alphanumeric characters.
* Usernames containing a specific domain name, among others.

### Configuration

For Lucy to apply regular expressions in a login field, the login form must use a POST method with the login action set to "**?login**". Additionally, the name of the login field should be "**login**" and the name of the password field should be "**password**". A valid login field in Lucy might resemble the following HTML snippet:

```html
<form action="?login" class="login-form" method="post" name="login-form">
  <div class="content">
    <input class="input username" name="login" placeholder="Username" type="text" /> 
    <input class="input password" name="password" placeholder="Password" type="password" />
    <div class="footer">
      <input class="button" name="submit" type="submit" value="Login" />
    </div>
  </div>
</form>
```

You can configure login filters [under scenario settings](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#regexp) once you've set up the login fields with the correct naming convention. Lucy will then be able to apply the filter mechanism. You can choose from a list of existing filter examples in the dropdown menu, or apply any POSIX regular expression filter within the input fields.

<figure><img src="../../.gitbook/assets/image (549).png" alt=""><figcaption></figcaption></figure>

Additionally, Lucy supports JavaScript-based login filters. An example of such a function verifies if the username starts with certain letters and checks if the password is complex. If both conditions are met, the script sends fake login data to Lucy for admin verification.

```html
<html>
<body>
  <form action="?login" method="post">
    <div><input id="inp_user" maxlength="127" name="login" size="30" title="Enter user name" type="text" width="180px" /></div>
    <div class="right"><input id="passwd" maxlength="127" name="password" size="30" type="password" width="180px" /></div>
    <div class="right"><input id="Log_On" onclick="return checkPwd();" type="submit" value="Submit" /></div>
  </form>
  <script type="text/javascript" src="/public/campaign/XXX/jquery-1.11.3.min.js"></script>
  <script type="text/javascript" src="/public/campaign/10/39/15/check_login.js"></script>
</body>
</html>
```

Make sure to download the corresponding JavaScript libraries and include them in your campaign template (landing page).

{% file src="../../.gitbook/assets/scripts.zip" %}
