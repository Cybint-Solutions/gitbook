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
    visible: true
---

# Exports

### Overview

LUCY provides a versatile data export functionality, accessible through the "Export" option within the campaign overview page. Users have the flexibility to export either all monitored data or select specific data for export. This feature supports a range of formats and methodologies, catering to various user needs.

{% hint style="info" %}
Navigate to a **Campaign -> Results -> Exports**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (352).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
All exports are available in either CSV or XML format.
{% endhint %}

***

### Recipient Statistics

<figure><img src="../../../../.gitbook/assets/image (353).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Recipient Statistics Descriptions</summary>

* **All**: Exports the entire dataset of campaign recipients without any filters applied.
* **All By Recipient Group**: Allows you to export data for specific groups of recipients.&#x20;
* **Succeeded**: Filters and exports data for recipients who completed the desired action of the attack, indicating they were successfully phished.
* **Not Succeeded**: Selects recipients who did not complete the attack's intended action, meaning the phishing attempt was unsuccessful with them.
* **Clicked**: Focuses on recipients who clicked on the link in the phishing email, message (SMS), or link to Awareness training.
* **Started Training**: Filters recipients who have begun the training modules provided in the campaign.
* **Not Started Training**: Exports data for recipients who have not initiated any training modules linked to the campaign.
* **Completed Training**:  Filters recipients who have gone through and completed the training modules.
* **Downloaded File**: Identifies recipients who have downloaded a file, as part of an attack or malware simulation.
* **Visits**: Exports data on all recipients who visited the campaign's landing pages.
* **Scenario Visits**: Focuses on recipients who visited a specific scenario in the campaign.
* **Awareness Visits**: Filters out data for recipients who visited the awareness pages that are typically set up to educate them post-engagement with the phishing attempt.
* **Quiz Answers**: Exports data specifically related to the recipients' engagement with quizzes, such as answers submitted.
* **Received Training Certificate**: Filters and exports data for recipients who have received a certificate upon completing a training module, signifying their participation and completion.
* **Clicks Data**: Provides detailed data on the interactions of recipients with the phishing links, such as the time of click and frequency.

</details>

***

### Recipient Success Actions

<figure><img src="../../../../.gitbook/assets/image (356).png" alt=""><figcaption></figcaption></figure>

<details>

<summary>Recipient Success Actions Descriptions</summary>

* **Succeeded to Group**: This option allows you to filter and export data for recipients who have been successfully phished or who have completed the desired success action in the campaign. The recipients who meet this criterion will be grouped together, which can be useful for follow-up actions such as simulating or training again.
* **Not Succeeded to Group**: Contrary to the above, this option will filter out and export data for recipients who did not fall for the phishing attempt or who did not complete the intended success action. These recipients are also grouped, allowing you to target them for more challenging simulations.
* **Clicked to Group**: This selection filters recipients based on whether they clicked on a phishing link or not. It groups the clickers, providing a list of those who showed initial engagement with the phishing content.

</details>

***

### Export recipients within a submitted time range to a new group.

This option exports data for recipients within a specified time range to a new group. This is useful for creating segments of recipients who have been active or participated within a certain period, and facilitating targeted follow-up campaigns or analyses.

<figure><img src="../../../../.gitbook/assets/image (127).png" alt="" width="290"><figcaption></figcaption></figure>

***

### Export campaign benchmark results

The Benchmark export provides a snapshot of campaign performance by compiling key metrics like message delivery, open rates, click-throughs, and overall success rates into a comprehensive report.

<figure><img src="../../../../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

***

### Export collected data

This export option compiles a detailed log of user interactions from the campaign, recording entries like timestamps, participant details, associated scenarios, and specific user-submitted information, exemplified by login credentials.

<figure><img src="../../../../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

***

### Automated Export

Automated Exports is a functionality that allows for the scheduled and recurrent generation of reports based on predefined criteria and intervals.

{% hint style="info" %}
Navigate to a **Campaign -> Results -> Automated Exports**
{% endhint %}

<figure><img src="../../../../.gitbook/assets/image (357).png" alt=""><figcaption></figcaption></figure>

* **Export Target**: Choose data sets to automate, like All Victims, Not Succeeded, Clicks Data, or Campaign Benchmark.
* **Export Frequency**: Set the frequency for the export—daily, weekly, monthly, or yearly.
* **Export Time**: Decide the specific time of day for the export to run.
* **Export Days**: Specify which days the export should occur, based on the chosen frequency.
* **Export Type**: Select the format of the exported file, such as XML or CSV.

This tool is designed to regularly provide fresh data without manual effort, aiding consistent and timely analysis sent directly to the email address of the campaign creator.

***

### Alternative Export Methods

* **API Integration**: LUCY offers [API access](../../../settings/common-system-settings/api-whitelist/) for users preferring automated data retrieval.

***

### All Exportable Columns

Lucy provides many exportable data points, covering aspects from recipient information to interaction metrics, such as:

* Personal and contact information (name, email, phone number)
* Engagement metrics (clicks, submissions, training completion)
* Campaign specifics (scenario name, domain, staff type)
* Technical data (operational system, IP, browser, plugins used)
* Interaction timelines (email submission, click, report times)
* Quiz and training metrics (quiz answers, training completion)
* Security awareness levels



| Collumn name                              | Description                                                                                         | Value Type        |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------- | ----------------- |
| name                                      | Name of the recipient                                                                               | Text              |
| email                                     | Email of the recipient                                                                              | Text              |
| phone                                     | Phone number of the recipient                                                                       | Numeral           |
| gender                                    | Gender of the recipient                                                                             | Male / Female     |
| link                                      | Unique link of the recipient                                                                        | Text              |
| lure\_submitted\_at                       | Time of lure email submission                                                                       | Timestamp         |
| mail\_submitted\_at                       | Time of email submission                                                                            | Timestamp         |
| clicked                                   | Recipient clicked the link in the email                                                             | Yes / No          |
| clicked\_at                               | Time recipient clicked the link in the email                                                        | Timestamp         |
| succeeded                                 | Success action triggered for the recipient                                                          | Yes / No          |
| succeeded\_at                             | Time when success action was triggered                                                              | Timestamp         |
| trained                                   | Recipient has completed the training                                                                | Yes / No          |
| trained\_at                               | Time when recipient has completed the training                                                      | Timestamp         |
| reported                                  | Recipient has reported the message via LUCY Report Plugin                                           | Yes / No          |
| reported\_at                              | Time when recipient has reported the message                                                        | Timestamp         |
| domain                                    | Domain used in the campaign's scenario                                                              | Text              |
| scenario                                  | Name of the scenario on the campaign                                                                | Text              |
| staff\_type                               | Info about recipient's staff category                                                               | Text              |
| location                                  | Info about recipient's location                                                                     | Text              |
| division                                  | Info about recipient's department                                                                   | Text              |
| comment                                   | Additional optional comment about the recipient                                                     | Text              |
| os                                        | Operational System of the workstation that submitted first click                                    | Text              |
| ip                                        | IP of the workstation that submitted first click                                                    | Numeral           |
| proxy\_ip                                 | IP of the proxy                                                                                     | Numeral           |
| browser                                   | Browser of the workstation that submitted first click                                               | Text              |
| plugins                                   | Plugins detected on the workstation that submitted first click                                      | Text              |
| country                                   | Country based on IP                                                                                 | County Code       |
| success\_rate                             | How many times a recipient was successfully attacked, depending on the Success Action               | Numeral           |
| click\_rate                               | How many times a recipient clicked the attack link                                                  | Numeral           |
| scenario\_time                            | Amount of time the victim has spent on the phishing link page                                       | Numeral           |
| awareness\_time                           | Amount of time the victim has spent on the awareness link page                                      | Numeral           |
| email\_subject                            | Subject of the sent email                                                                           | Text              |
| first\_click\_after\_delivery             | Time value in seconds between mail\_submitted\_at and succeeded\_at                                 | Numeral           |
| first\_report\_after\_delivery            | Time value in seconds between mail\_submitted\_at and reported\_at                                  | Numeral           |
| reminder\_click\_submitted\_at            | Time when recipient clicked the reminder link                                                       | Timestamp         |
| reminder\_training\_start\_submitted\_at  | Time when the recipient started the training provided by reminder                                   | Timestamp         |
| reminder\_training\_finish\_submitted\_at | Time when the recipient finished the training provided by reminder                                  | Timestamp         |
| downloaded\_files                         | File-based attack downloaded files by the recipient                                                 | Text              |
| collected\_data                           | The data that has been submitted by the recipient on the landing page                               | Text              |
| out\_of\_office\_at                       | Time of Out of Office autorespond                                                                   | Timestamp         |
| bounced\_at                               | Time of the Bounced response                                                                        | Timestamp         |
| responded\_at                             | Time of the incoming response to the email                                                          | Timestamp         |
| certificate\_received                     | Recipient has received a certificate                                                                | Yes / No          |
| training\_with\_quiz\_passed              | Recipient has passed a training with Quiz mode enabled                                              | Yes / No          |
| training\_with\_quiz\_passed\_at          | Time when recipient has passed a training with Quiz mode enabled                                    | Timestamp         |
| training\_noquiz\_finished                | Recipient has finished a training without Quiz                                                      | Yes / No          |
| training\_noquiz\_finished\_at            | Time when recipient has finished a training without Quiz                                            | Timestamp         |
| security-level                            | Level of awareness security                                                                         | Numeral           |
| answers\_count\_0                         | Quiz answers count                                                                                  | Numeral           |
| answers\_percent\_0                       | Quiz answers percentage (based on total number of questions)                                        | Percentage        |
| correct\_answers\_count\_0                | Number of correct quiz answers                                                                      | Numeral           |
| correct\_answers\_percent\_0              | Correct answers percentage (based on total number of questions)                                     | Percentage        |
| wrong\_answers\_count\_0                  | Number of wrong quiz answers                                                                        | Numeral           |
| wrong\_answers\_percent\_0                | Wrong answers percentage (based on total number of questions)                                       | Percentage        |
| quiz\_time\_spent\_0                      | Time spent for quiz                                                                                 | Minutes / Seconds |
| training\_succeeded\_0                    | Recipient has completed the training with Extended method of tracking the end of the quiz           | Yes / No          |
| training\_succeeded\_at\_0                | Time when recipient has completed the training with Extended method of tracking the end of the quiz | Timestamp         |



###
