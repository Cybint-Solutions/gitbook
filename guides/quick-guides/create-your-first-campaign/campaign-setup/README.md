# Campaign Setup

**1.1** On the Lucy dashboard, select "New Campaign"

<figure><img src="../../../../.gitbook/assets/image (232).png" alt=""><figcaption></figcaption></figure>

**1.2** Choose the Campaign Type:\
\
Lucy's campaign creation strategy includes three key elements: Attack Simulations, Employee Education (Awareness), and Infrastructure Tests. These components can operate individually or together.

<figure><img src="../../../../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Attack Simulation" %}
To begin creating a campaign with an Attack, first select the Attack type. You can also link an Awareness training template in subsequent steps if desired.

[**Data Entry Attack:**](../../../attack-simulations/attack-types/data-entry-attack.md)\
\
The recipient will receive an email with a link that leads to a fake webpage designed to harvest credentials. A successful attack occurs when the recipient enters their data on this page.

[**Hyperlink Attack:**](../../../attack-simulations/attack-types/hyperlink-attack.md)

The recipient will receive an email with a link, and the attack is deemed successful as soon as they click on this link. There is no associated landing page in this scenario.

[**File Attack:**](../../../attack-simulations/attack-types/file-attack.md)

Like Data Entry Attacks, the user receives an email with two potential actions: they can click a link to visit a landing page where they download an executable file, or the executable file can be directly attached to the email itself.

[**Portable Media Attack:**](../../../attack-simulations/attack-types/portable-media.md)

LUCY provides the capability to create files for use on various removable media devices, including CDs, USBs, DVDs, SD Cards, and others. The most common approach involves attacks via USB sticks.

[**Smishing:**](../../../attack-simulations/attack-types/smishing.md)

Smishing, also known as SMS Phishing, is a deceptive tactic where fraudulent text messages are sent to trick recipients into revealing sensitive information such as credit card details or passwords. It's important to note that this type of attack can only be configured in [**Expert Mode**](../../../../application-screens-reference/campaigns/new-campaign/expert-mode.md).
{% endtab %}

{% tab title="Educate Employees" %}
This selection is reserved for Awareness-only campaigns, where an administrator aims to focus solely on training their users.
{% endtab %}

{% tab title="Infrastructure Tests" %}
Infrastructure tests are designed to assess your organization's defenses against common attack vectors.

**Technical Malware Test**: Evaluate your technical defenses against malware by simulating a malware attack and observing whether the current security setup can detect and neutralize the threat.

**Mail & Web Filter Test**: Assesses the effectiveness of your email and web filtering systems. This test sends non-malicious simulated spam and phishing emails to see if the filters can successfully block these potential threats.

**Spoofing Test**: Checks the robustness of the system against email spoofing. It tests whether someone can mimic or 'spoof' an email address from your domain, which is a common tactic used in phishing and social engineering attacks.
{% endtab %}
{% endtabs %}
