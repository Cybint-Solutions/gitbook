---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: false
---

# Statistics Dashboard

### Introduction

The Statistics Dashboard offers a comparative overview of all campaign-related activities. Its purpose is to provide insights into phishing trends, key performance indicators, and benchmarking campaigns from different clients against each other.

<figure><img src="../.gitbook/assets/image (696).png" alt=""><figcaption></figcaption></figure>

***

### Filtered Campaign Results

The Statistics Dashboard allows administrators to filter campaigns based on time, quantity, and/or clients. The filtered results will adjust all displayed metrics according to the selected filter criteria.

#### Time and quantity-based filtering:

<figure><img src="../.gitbook/assets/image (698).png" alt="" width="170"><figcaption></figcaption></figure>

#### Client-based filtering:

<figure><img src="../.gitbook/assets/image (699).png" alt="" width="375"><figcaption></figcaption></figure>

#### Filtered Campaigns:

These results provide a cumulative total of campaigns in each status, based on your filtered criteria.

<figure><img src="../.gitbook/assets/image (700).png" alt="" width="195"><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Running" %}
These are active campaigns currently in a **started** status:

<figure><img src="../.gitbook/assets/image (701).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Finished" %}
These campaigns have concluded and are displayed with a **stopped** status:

<figure><img src="../.gitbook/assets/image (702).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Planned" %}
These are campaigns in a **ready** status:

<figure><img src="../.gitbook/assets/image (703).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Pending Approval" %}
These campaigns are pending approval from a Supervisor, who has the authority to approve the start of campaigns submitted by users with limited privileges. They are marked with a **pending** status:

<figure><img src="../.gitbook/assets/image (704).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Archived" %}
These campaigns have been stopped and archived, indicated by an **archived** status:

<figure><img src="../.gitbook/assets/image (705).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Deep Archived" %}
These campaigns have been archived, and the related scenario and awareness templates have been deleted from the campaign as part of the [smart storage management](settings/advanced-system-settings/advanced-settings.md#smart-storage) of a Lucy server.

{% hint style="info" %}
Deep archiving a campaign will not remove the statistical data, even when the scenarios or awareness templates have been deleted from the campaign.
{% endhint %}
{% endtab %}
{% endtabs %}

#### Campaign Types:

These results provide an overview of each type of campaign. Each type is separated by a time-based metric, offering a view of how many campaigns are planned for the future, currently running, and finished.

<figure><img src="../.gitbook/assets/image (733).png" alt="" width="197"><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Future" %}
These campaigns have been created but not yet started and are denoted by a **ready** status:

<figure><img src="../.gitbook/assets/image (734).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Current" %}
These are active campaigns currently in a **started** status:

<figure><img src="../.gitbook/assets/image (735).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Finished" %}
These campaigns have concluded and are displayed with a **stopped** status:

<figure><img src="../.gitbook/assets/image (736).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

***

### Grouping Campaign Results

Group attack and awareness campaign results by their campaign type, recipient group, department, branch, or location for more precise analysis.

<figure><img src="../.gitbook/assets/image (793).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Available starting in version 5.1.
{% endhint %}

***

### Phishing Simulation Results

The phishing simulation results display key metrics related to each campaign based on the predefined filtered criteria. This holistic view shows trends and statistical data for main parameters of each campaign, such as reports, successful phishing simulations, clicks, replies, and errors.

<figure><img src="../.gitbook/assets/image (737).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Phishing Trend" %}
The phishing trend line serves as the main indicator for administrators to assess the effectiveness of their security awareness programs. Each black dot represents a campaign, with its specific placement on the graph based on an average calculation of that campaign and the previous five completed campaigns.

For example:\
\
Campaign 1 = 23% phished successfully

Campaign 2 = 58% phished successfully

Campaign 3 = 0% phished successfully

Campaign 4 = 43% phished successfully

Campaign 5 = 13% phished successfully

<figure><img src="../.gitbook/assets/image (693).png" alt=""><figcaption></figcaption></figure>

The calculation will add all phished successfully results and divide them by five:

`(23+58+0+43+13)/5 = 27.4%`

This is the graphical representation of point 5 in the graph.
{% endtab %}

{% tab title="Reported" %}
The **Reported** bar represents the number of recipients who successfully identified the phishing simulation and reported it using the email report button in their respective email client.

{% hint style="info" %}
See our platform reference article on [Incidents](incidents.md)
{% endhint %}
{% endtab %}

{% tab title="Phished Success" %}
The **Phished Successfully** bar represents the number of recipients who were successfully phished based on the success action of the campaign.
{% endtab %}

{% tab title="Clicked" %}
The **Clicked** bar represents the recipients who have clicked on the link in the simulated phishing email.

{% hint style="info" %}
For hyperlink attacks, a click is also counted as a successful phishing attempt since no landing page is provided after the click is captured.
{% endhint %}
{% endtab %}

{% tab title="Replied" %}
The **Replied** bar indicates the number of recipients who received the simulation and decided to reply to the email, demonstrating a form of unwarranted engagement.

{% hint style="warning" %}
To capture reply statistics, ensure your domain has the relevant [MX records set up](settings/common-system-settings/domains/#prerequisites-for-adding-a-custom-domain) for your Lucy server to receive replies.
{% endhint %}
{% endtab %}

{% tab title="Errors" %}
The **Error** bar indicates any processing errors that may have occurred during the campaign's active period. This metric is particularly important for running campaigns, as it helps troubleshoot issues and ensures that all recipients receive the simulated email.
{% endtab %}
{% endtabs %}

{% hint style="info" %}
When hovering over a campaign within the graph, a pop-up will appear displaying all campaign-related data. Additionally, you can click through to the campaign to access it directly from the graphical dashboard.

![](<../.gitbook/assets/image (692).png>)
{% endhint %}

#### Average Results of Campaign Metrics:

On the right side of the graph, all metrics are displayed as averages based on the predefined filtered criteria. These results are weighted averages calculated over all campaigns within the filtered range, allowing administrators to gather a holistic view of the overall results rather than focusing on individual phishing trend points on the graph.

<figure><img src="../.gitbook/assets/image (688).png" alt="" width="265"><figcaption></figcaption></figure>

***

### Awareness Results

Awareness results focus on two key points: the completion rate, which determines how many recipients have completed the awareness exercise, and the exam score, which indicates the average results of awareness exercises that include a quiz or exam.

<figure><img src="../.gitbook/assets/image (689).png" alt=""><figcaption></figcaption></figure>

The Exam Score is represented as a black dot on the graph. Its position is determined by the average score achieved by recipients who have completed the exam or quiz.

{% hint style="info" %}
Awareness exercises without an exam or quiz will not have a black dot representing the average exam score.
{% endhint %}

The completion rate is defined for each campaign as the average percentage of recipients who have completed the awareness exercise:

<figure><img src="../.gitbook/assets/image (690).png" alt=""><figcaption></figcaption></figure>

The average completion rate of all awareness campaigns, based on the filtered criteria, will be displayed on the right side of the graph to show the overall completion percentage as an average.

<figure><img src="../.gitbook/assets/image (691).png" alt=""><figcaption></figcaption></figure>

***

### Exporting Statistical Data

Customize your exports by selecting specific data sets, such as Phishing or Awareness, and choose how to display the data—whether as percentages, absolute numbers, or both.

<figure><img src="../.gitbook/assets/image (794).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (795).png" alt=""><figcaption></figcaption></figure>

#### Branding & Customization

Upload your organization's branding and choose from a variety of color schemes to personalize your reports.

#### Language Support

Generate reports in multiple languages to cater to your diverse audience and stakeholders.
