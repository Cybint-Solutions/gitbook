# Wizard Mode

<details>

<summary>What is a Campaign?</summary>

A campaign is a structured program designed to assess and improve employees' understanding and response to cybersecurity threats. It typically includes simulated attacks, such as phishing, and educational content about best practices in cybersecurity. \
\
These campaigns serve as benchmarks for an organization's security awareness level, helping to identify areas of risk and plan for future training to mitigate these risks.

</details>

> Creating a campaign is easy and efficient using our Campaign Wizard. For more granular control, you can explore our [**expert mode**](../expert-mode.md) for creating advanced campaigns.

**1.1** On the Lucy dashboard, select "New Campaign"

<figure><img src="../../../../.gitbook/assets/image (232).png" alt=""><figcaption></figcaption></figure>

**1.2** Choose the Campaign Type:\
\
Lucy's approach to campaign creation is anchored in three core components: Attack Simulations, Employee Education (Awareness), and Infrastructure Tests. These elements can function independently or synergistically, forming a comprehensive Security Awareness Training program.\
\
The initial stage involves determining the primary Campaign Type. In this example, the focus is on deploying a Data Entry Attack. If the recipient is successfully phished by this attack, they will be directed to the corresponding Awareness training.

<figure><img src="../../../../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Attack Simulation" %}
**Creating a campaign with an Attack begins by selecting the Attack type. Please note that you can also associate an Awareness training template in the following steps if you choose to do so.**

[**Data Entry Attack:**](../../../../guides/attack-simulations/attack-types/data-entry-attack.md)\
\
**The recipient will receive an email with a link that leads to a fake webpage designed to harvest credentials. A successful attack occurs when the recipient enters their data on this page.**

[**Hyperlink Attack:**](../../../../guides/attack-simulations/attack-types/hyperlink-attack.md)

**The recipient will receive an email with a link, and the attack is deemed successful as soon as they click on this link. There is no associated landing page in this scenario.**

[**File Attack:**](../../../../guides/attack-simulations/attack-types/file-attack.md)

**Like Data Entry Attacks, the user receives an email with two potential actions: they can click a link to visit a landing page where they download an executable file, or the executable file can be directly attached to the email itself.**

[**Portable Media Attack:**](../../../../guides/attack-simulations/attack-types/portable-media.md)

**LUCY provides the capability to create files for use on various removable media devices, including CDs, USBs, DVDs, SD Cards, and others. The most common approach involves attacks via USB sticks.**

[**Smishing:**](../../../../guides/attack-simulations/attack-types/smishing.md)

**Smishing, also known as SMS Phishing, is a deceptive tactic where fraudulent text messages are sent to trick recipients into revealing sensitive information such as credit card details or passwords. It's important to note that this type of attack can only be configured in** [**Expert Mode**](../expert-mode.md)**.**
{% endtab %}

{% tab title="Educate Employees" %}
This selection is reserved for Awareness-only campaigns, where an administrator aims to focus solely on training their users.
{% endtab %}

{% tab title="Infrastructure Tests" %}
Infrastructure tests are designed to assess your organization's defenses against common attack vectors.

**Technical Malware Test**: Evaluates your technical defenses against malware by simulating a malware attack and observing whether the current security setup can detect and neutralize the threat.

**Mail & Web Filter Test**: Assesses the effectiveness of your email and web filtering systems. This test sends non-malicious simulated spam and phishing emails to see if the filters can successfully block these potential threats.

**Spoofing Test**: Checks the robustness of the system against email spoofing. It tests whether someone can mimic or 'spoof' an email address from your domain, which is a common tactic used in phishing and social engineering attacks.
{% endtab %}
{% endtabs %}
