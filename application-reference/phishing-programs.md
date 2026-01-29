# Phishing Programs

{% hint style="info" %}
Adaptive Phishing Programs are available in Lucy version 5.7 and above.
{% endhint %}

## Introduction

**Adaptive Attack Scenarios** is a new simulation mode that automatically adjusts phishing attack difficulty for each user based on their individual [**Risk Score**](users/risk-score.md). Instead of running static campaigns or manually segmenting users into fixed groups, Lucy continuously personalizes attack scenarios over time, creating a more realistic and scalable training experience.

With Adaptive Attack Scenarios, campaigns are generated automatically at scheduled intervals. Each recipient is assigned a phishing scenario that matches their current risk level, and this assignment evolves as their Risk Score changes. This allows organizations to deliver ongoing, tailored simulations without the need to redesign or rebalance campaigns manually.

This feature is designed for organizations that want:

* Continuous phishing simulations without manual campaign management
* Difficulty progression based on user behavior
* Reduced administrative overhead
* More accurate measurement of user risk over time

## Getting Started

To create an adaptive campaign navigate to **Phishing Programs** and then select **+ New Program:**

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

Give the program a name and a [client](settings/clients/), then select **Create**.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Test Mode enables smaller frequency options and limits recipients to 10 for safe testing.
{% endhint %}

## Configuration

Just like standard campaigns, Adaptive Programs have an initial configuration that must be completed first.&#x20;

### Base Settings

The [base settings](campaigns/campaign-settings/configuration/base-settings.md) are the same as any other campaign with one new setting, **Run Frequency**.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

This setting controls the length of each individual scenario within the program. In the screenshot above, every scenario will run for 2 weeks. At the end of this timeframe, the program will re-calculate the risk score for each user and randomly assign them a new scenario according to their new score.

{% hint style="success" %}
Click **Save** to apply your changes and select **Finalize Step** when you're ready to move on.
{% endhint %}

### Attack Simulation

In a standard campaign you can add one or more attack scenarios to your campaign, and the same is true of an adaptive program.

The difference is that Adaptive Programs use your configured [Risk Scores](users/risk-score.md) automatically. For each Range (Rookie, Advanced, Expert, etc.) you can add one or more attack scenarios that your Adaptive Program will use when randomly assigning scenarios.

Adding and configuring a scenario works just like in a [standard campaign](campaigns/campaign-settings/main-settings/attack-simulation/attack-templates.md).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Users will not receive a scenario they've already received unless they've exhausted all scenarios in their level. Be sure to add a sufficient number to avoid repeats, and think carefully about the overall length of your program!
{% endhint %}

{% hint style="success" %}
Select **Finalize Step** when you're ready to move on.
{% endhint %}

### Recipients

Unlike in standard campaigns, recipients in an Adaptive Program do not need to be bound to any scenarios. The program will automatically use the Risk Score of each recipient to send them the appropriate scenario, and when that scenario is finished the program will update their scores and do it again!

{% hint style="info" %}
Select **Finalize Step** when you're ready to move on.
{% endhint %}

## Starting a Program

Select **Start** to initiate the campaign checks and start your program.

The program must run the checks for each scenario, so give it time to finish and don't navigate away from the page while the checks are in-progress.

{% hint style="danger" %}
Programs cannot be edited once started, so double-check your settings!
{% endhint %}

## Program Dashboard

Once you've finalized each step you'll be taken to the program's dashboard view, which looks very similar to the standard campaign view:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Adaptive programs can use the [scheduler](campaigns/campaign-settings/configuration/schedule/), [generate reports](campaigns/campaign-settings/results/reports.md), and use all the other [advanced options](campaigns/campaign-settings/advanced-settings/) of a regular campaign.
{% endhint %}

### Program Statistics

On the dashboard page you can select **Program Statistics** to see an overview of your program:

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Selecting **Export Statistics** will take you to the [Statistics Dashboard](statistics-dashboard.md) where you can filter by Adaptive Programs and then generate a report.

Select **Edit Program** to go back to the program dashboard.
