# Variables in Lucy

Lucy variables are useful for personalizing your content for each recipient. You can use them throughout the application to easily apply the correct value without having to know it in advance.

Variables in Lucy use the `%` character to identify themselves, like so:

```
Hello %name%, I am sending this message on %date% at %time%.
```

***

## Awareness Email Variables

<table><thead><tr><th width="258">Variable</th><th>Description</th></tr></thead><tbody><tr><td><code>%link%</code></td><td>Resolves to the base URL of the scenario (phishing page in an attack template, training content in an awareness template).</td></tr><tr><td><code>%user-password-reset%</code></td><td>Resolves to a password reset link for the recipient's end-user account.</td></tr><tr><td><code>%user-profile-link%</code></td><td>Resolves to a link to the end-user portal.</td></tr><tr><td><code>%user-login-url%</code></td><td>Resolves to a Single Sign-On (SSO) link for the end-user portal.</td></tr><tr><td><code>%name%</code></td><td>Resolves to the recipient's full name.</td></tr><tr><td><code>%firstname%</code></td><td>Resolves to the recipient's first name.</td></tr><tr><td><code>%lastname%</code></td><td>Resolves to the recipient's last name.</td></tr><tr><td><code>%email%</code></td><td>Resolves to the recipient's email address.</td></tr><tr><td><code>%client%</code></td><td>Resolves to the client name associated with the recipient's group.</td></tr><tr><td><code>%gender%</code></td><td>Used for titles (e.g., Mr., Mrs., None).</td></tr><tr><td><code>%subject%</code></td><td>Resolves to the subject line of the attack email.</td></tr><tr><td><code>%sender%</code></td><td>Resolves to the sender name of the attack email.</td></tr><tr><td><code>%sender-email%</code></td><td>Resolves to the email address that sent the attack email.</td></tr><tr><td><code>%started%</code></td><td>Resolves to the date when the related campaign was started.</td></tr><tr><td><code>%stopped%</code></td><td>Resolves to the date when the related campaign was stopped.</td></tr></tbody></table>

#### time

`%time%` inserts a timestamp into the template. If a time zone is not specified then the time of the email send is used as the basis of the offset. The offset is measures in minutes.

You can configure the variable like so: `%time("format", "offset", "zone")%`

#### Examples

```
%time("l, H:i", "0", "Europe/Zurich")% = "Monday, 09:20"
```

This time is offset 0 minutes from Europe/Zurich time.

```
%time("Y/m/d" H:i:s", "-60")% = "2024/03/12 08:30:47"
```

The time is offset 60 minutes backwards from the time of the email.

***

## Awareness Website Variables

<table><thead><tr><th width="195">Variable</th><th>Description</th></tr></thead><tbody><tr><td><code>%name%</code></td><td>Resolves to the recipient's full name.</td></tr><tr><td><code>%email%</code></td><td>Resolves to the recipient's email address.</td></tr><tr><td><code>%client%</code></td><td>Resolves to the client name associated with the recipient's group.</td></tr><tr><td><code>%subject%</code></td><td>Resolves to the subject line of the attack email.</td></tr><tr><td><code>%sender%</code></td><td>Resolves to the sender name of the attack email.</td></tr><tr><td><code>%sender-email%</code></td><td>Resolves to the email address that sent the attack email.</td></tr><tr><td><code>%started%</code></td><td>Resolves to the date when the related campaign was started.</td></tr><tr><td><code>%stopped%</code></td><td>Resolves to the date when the related campaign was stopped.</td></tr></tbody></table>

***

## Attack Email Variables

<table><thead><tr><th width="214">Variable</th><th>Description</th></tr></thead><tbody><tr><td><code>%link%</code></td><td>Resolves to the base URL of the scenario (phishing page in an attack template, training content in an awareness template).</td></tr><tr><td><code>%qr-code%</code></td><td>A QR code version of the <code>%link%</code> variable.</td></tr><tr><td><code>%link-awareness%</code></td><td>Resolves to the awareness website.</td></tr><tr><td><code>%name%</code></td><td>Resolves to the recipient's full name.</td></tr><tr><td><code>%firstname%</code></td><td>Resolves to the recipient's first name.</td></tr><tr><td><code>%lastname%</code></td><td>Resolves to the recipient's last name.</td></tr><tr><td><code>%email%</code></td><td>Resolves to the recipient's email address.</td></tr><tr><td><code>%division%</code></td><td>Resolves to the recipient's division field.</td></tr><tr><td><code>%location%</code></td><td>Resolves to the recipient's location field.</td></tr><tr><td><code>%staff-type%</code></td><td>Resolves to the recipient's staff type field.</td></tr><tr><td><code>%comment%</code></td><td>Resolves to the recipient's comment field.</td></tr></tbody></table>

***

## Attack Website Variables

<table><thead><tr><th width="219">Variable</th><th>Description</th></tr></thead><tbody><tr><td><code>%link%</code></td><td>Always resolves to the base URL of the scenario. In an attack template, this is the phishing page; in an awareness template, this is the training content.</td></tr><tr><td><code>%link-awareness%</code></td><td>Resolves to the awareness website.</td></tr><tr><td><code>%name%</code></td><td>Resolves to the recipient's full name.</td></tr><tr><td><code>%firstname%</code></td><td>Resolves to the recipient's first name.</td></tr><tr><td><code>%lastname%</code></td><td>Resolves to the recipient's last name.</td></tr><tr><td><code>%email%</code></td><td>Resolves to the recipient's email address.</td></tr><tr><td><code>%division%</code></td><td>Resolves to the recipeint's division field.</td></tr><tr><td><code>%location%</code></td><td>Resolves to the recipeint's location field.</td></tr><tr><td><code>%staff-type%</code></td><td>Resolves to the recipeint's staff type field.</td></tr><tr><td><code>%comment%</code></td><td>Resolves to the recipeint's comment field.</td></tr><tr><td><code>%gender%</code></td><td>Used for titles (e.g., Mr., Mrs., None).</td></tr><tr><td><code>%subject%</code></td><td>Resolves to the subject line of the attack email.</td></tr><tr><td><code>%sender%</code></td><td>Resolves to the sender name of the attack email.</td></tr><tr><td><code>%sender-email%</code></td><td>Resolves to the email address that sent the attack email.</td></tr></tbody></table>

#### static

The `%static%` variable refers to the static file path, which is useful for linking content.

```
<link rel=styelsheet type="text/css" href="%static%/style.css>
<script src="%static%/script.js"></script>
```

#### time("format", "offset", "zone")

`%time%` inserts a timestamp into the template. If a time zone is not specified then the time of the email send is used as the basis of the offset. The offset is measures in minutes.

```
%time("l, H:i", "0", "Europe/Zurich")% = "Monday, 09:20"
```

This time is offset 0 minutes from Europe/Zurich time.

```
%time("Y/m/d" H:i:s", "-60")% = "2024/03/12 08:30:47"
```

The time is offset 60 minutes backwards from the time of the email.

***

## Login Form Parameters

* The login form should use the `POST` method.
* Set the form's `action` attribute to either:
  * The same page (leave `action` empty).
  * `"?login"` to point to a login-specific route.
    * In Lucy, this action will automatically lead to the `account.html` page which is required in order to collect statistics for the campaign.

To validate logins and passwords using regular expressions (configured in the "Login Regexp" and "Password Regexp" fields in scenario settings):

* Set the `name` attribute of the login field to `"login"`.
* Set the `name` attribute of the password field to `"password"`.

***

## Report Template Variables

<table><thead><tr><th width="395">Variable</th><th>Description</th></tr></thead><tbody><tr><td><code>%report.createdate%</code></td><td>The date the report was created.</td></tr><tr><td><code>%report.author%</code></td><td>The author of the report.</td></tr><tr><td><code>%startdate%</code></td><td>Start date and time of the campaign.</td></tr><tr><td><code>%finishdate%</code></td><td>End date and time of the campaign.</td></tr><tr><td><code>%creator%</code></td><td>User who created the campaign.</td></tr><tr><td><code>%file.formats%</code></td><td>File formats used in file-based attack scenarios within the campaign.</td></tr><tr><td><code>%scenarios.number%</code></td><td>Total number of scenarios used in the campaign.</td></tr><tr><td><code>%scenarios.names%</code></td><td>Names of the scenarios used in the campaign.</td></tr><tr><td><code>%scenarios.types%</code></td><td>Types of scenarios used in the campaign.</td></tr><tr><td><code>%client%</code></td><td>Name of the client associated with the campaign.</td></tr><tr><td><code>%opened%</code></td><td>Percentage of recipients who opened the email.</td></tr><tr><td><code>%opened.count%</code></td><td>Number of emails that were opened.</td></tr><tr><td><code>%clicked%</code></td><td>Percentage of recipients who clicked on a link.</td></tr><tr><td><code>%clicked.count%</code></td><td>Number of emails where a link was clicked.</td></tr><tr><td><code>%sent.count%</code></td><td>Total number of emails sent in the campaign.</td></tr><tr><td><code>%reported%</code></td><td>Percentage of recipients who reported the email.</td></tr><tr><td><code>%success%</code></td><td>Percentage of emails where data was submitted by the recipient.</td></tr><tr><td><code>%success.count%</code></td><td>Number of emails where data was submitted.</td></tr><tr><td><code>%domains%</code></td><td>Domains used in the campaign's scenario settings.</td></tr><tr><td><code>%timezone%</code></td><td>Timezone setting of the product server.</td></tr><tr><td><code>%recipients.groups%</code></td><td>Names of recipient groups targeted in the campaign.</td></tr><tr><td><code>%awareness.names%</code></td><td>Name of the awareness template used.</td></tr><tr><td><code>%awareness.sent%</code></td><td>Number of awareness emails sent.</td></tr><tr><td><code>%awareness.opened%</code></td><td>Number of awareness emails opened by recipients.</td></tr><tr><td><code>%awareness.incomplete%</code></td><td>Number of users who did not complete the training.</td></tr><tr><td><code>%awareness.completed%</code></td><td>Number of users who completed the training.</td></tr><tr><td><code>%questions.number%</code></td><td>Number of questions included in the quiz.</td></tr><tr><td><code>%data.number%</code></td><td>Total and relative amount of data collected from users.</td></tr><tr><td><code>%recipient.count%</code></td><td>Number of recipients in the campaign.</td></tr><tr><td><code>%incident.count.campaign%</code></td><td>Number of incident reports related to the campaign.</td></tr><tr><td><code>%incident.count.campaignrelated%</code></td><td>Total number of reports related to all campaigns.</td></tr><tr><td><code>%incident.count.notcampaignrelated%</code></td><td>Total number of reports not related to campaigns.</td></tr><tr><td><code>%incident.count.total%</code></td><td>Total number of incident reports.</td></tr><tr><td><code>%out.of.office%</code></td><td>Percentage of "Out of Office" responses.</td></tr><tr><td><code>%bounced%</code></td><td>Percentage of bounced messages.</td></tr><tr><td><code>%responded%</code></td><td>Percentage of recipients who responded.</td></tr></tbody></table>

