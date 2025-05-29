# Smishing

## Understanding the attack

SMS-based attacks involve deceptive messages that appear to come from legitimate sources, such as banks, delivery services, or trusted institutions, to trick recipients into providing sensitive information or clicking on malicious links. In the context of Lucy, a smishing attack can be a [hyperlink](hyperlink-attack.md) or [data-entry](data-entry-attack.md) attack.

{% hint style="info" %}
Smishing campaigns are more complex to set up, as they involve variables beyond what Lucy handles directly. We recommend reaching out to your Customer Success Manager or Solution Engineer before starting a campaign to ensure everything is properly configured.
{% endhint %}

{% hint style="danger" %}
Before initiating any SMS campaigns, it's essential to submit whitelisting information to the SMS providers. This step ensures that your campaign's traffic is permitted across all relevant carrier networks, preventing potential delivery issues or restrictions.

Ensure to allocate a minimum of <mark style="color:red;">4 weeks</mark> for the completion of the whitelisting process.
{% endhint %}

## Checklist

* [x] [Register an attack domain](../../quick-guides/create-your-first-campaign/register-an-attack-domain.md)
* [x] [Select an SMS carrier](../../../application-screens-reference/settings/common-system-settings/sms-settings.md)
* [x] [Create a campaign using Expert Mode](../../../application-screens-reference/campaigns/new-campaign/expert-mode.md)
* [x] [Add an attack scenario](../../quick-guides/create-your-first-campaign/campaign-setup/attack-settings.md)
  * [x] If your scenario is a hyperlink, set the success action to C**lick**
  * [x] If it's a data-entry scenario, set it to **Data Submit**
* [x] Enable the bit.ly URL shortener in the attack scenario settings
* [x] [Contact Support for SMS Whitelisting](../../../when-to-contact-us/contact-technical-support.md)

{% hint style="success" %}
Shortening the URL helps keep your SMS under the character limit.
{% endhint %}

## Register a sender

SMS are more strictly controlled than emails. Carriers will reject your messages unless you use a registered sender. The process for each SMS provider is as follows:

{% tabs %}
{% tab title="Message Bird" %}
1. Choose your country to see the specific [requirements for SMS campaigns](https://docs.bird.com/connectivity-platform/country-restrictions-and-regulations).
2. Provide all necessary information to our [technical support team](../../../when-to-contact-us/contact-technical-support.md) so they can register an **originator** (sender) for you. See below for details.
3. Once your information has been successfully whitelisted you will then be able to initiate your smishing campaign. This can take as little as 4 days or as long as 4 weeks, it depends on the country or countries in question and their response time to the request.

{% hint style="info" %}
If you opt for the Custom integration using your own MessageBird account, you will need to directly submit your whitelisting information to MessageBird Support.
{% endhint %}

***

### Registered originator (sender) information

{% hint style="danger" %}
Your SMS **will not be delivered** without a registered sender.
{% endhint %}

#### Originator

The originator can be an Alphanumeric string (ex BrandName), Shortcodes (ex 1234), or Mobile virtual numbers.

#### Originator legal company country

The country where the company owning the originator is registered.

#### Originator legal company name

The Legal Name of the company owning the originator

#### Originator corporate URL

The corporate URL of the company owning the originator.

#### Industry vertical

Agriculture, Education, Technology, etc.

#### Call to action (CTA) URL

Any URL that may be contained in the SMS specifically sent with the Originator you are registering. In Lucy, this will be the value of the `%link%` variable.&#x20;

#### Other CTA(s)

Any other URLs present in the message.

#### Description of use case

How SMS is used in your service. If you need to clarify any answer provided in any other fields, you can do so here. If the originator / brand you are registering differs from the legal company name or URL please explain why it is so in the description. The lack of relationship between registering companies and originator is the most common cause for rejection.

#### SMS template

A copy of the SMS you will send in the campaign.
{% endtab %}

{% tab title="SMSMode" %}
1. **Sender ID:** The name that will appear as the sender on each SMS.
2. **Client consent:** A formal document from your organization that explicitly approves the sending of smishing simulation messages using the specified Sender ID.
3. **Total SMS count:** The total number of messages planned for dispatch in the campaign.
4. **SMS content:** The exact text of the message to be sent.
5. **Campaign duration:** The total length of the campaign, including any testing days.
6. **Locations:** A list of all the countries where the campaign recipients are located, to ensure compliance and proper delivery of the smishing messages.

{% hint style="info" %}
If you opt for the Custom integration using your own SMSMode account, you will need to directly submit your whitelisting information to SMSMode Support.
{% endhint %}
{% endtab %}
{% endtabs %}

## User detection methods

To help employees recognize and respond to hyperlink phishing attempts effectively, the following user detection methods can be incorporated into training programs:

**Unfamiliar numbers**\
Be cautious of text messages from unknown or unrecognized phone numbers, especially if they ask for sensitive information or contain urgent requests.

**Spelling and grammar errors**\
Smishing messages often contain unusual grammar, spelling mistakes, or awkward phrasing, which can indicate a fraudulent source.

**Verify links before clicking**\
Hover over or long-press any links in the message to inspect the URL. Fraudulent links often use misspelled brand names or suspicious web addresses.

**Be wary of urgency**\
Smishing attacks commonly try to create a sense of panic or urgency, pushing users to act without thinking. Messages that demand immediate action, like "Your account will be locked," should be treated with suspicion.

**Avoid sharing personal information**\
Legitimate organizations rarely ask for sensitive information (like passwords or credit card details) via SMS. Always verify through official channels if you're unsure.

**Cross-check with official sources**\
If a message claims to be from a known service or institution, contact them directly using their official website or customer support to confirm its legitimacy.
