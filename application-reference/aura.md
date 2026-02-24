# AURA

{% hint style="info" %}
AURA is available in Lucy version 5.7 and above.
{% endhint %}

{% hint style="info" %}
AURA is currently in Beta and is available by request.

For access to this Beta feature, please contact your account manager.
{% endhint %}

## Introduction <a href="#overview.1" id="overview.1"></a>

AURA is an automated awareness engine designed to run a continuous security awareness program without requiring manual campaign setup.

Administrators select topics, define target audiences, choose main courses, set validity periods, and define boosts frequency. Once activated, AURA continuously checks which users need which training and automatically sends the appropriate education based on their individual learning record.

Instead of launching recurring awareness campaigns, organizations configure the program once — and AURA maintains it automatically.

***

{% hint style="info" %}
## Relationship to Adaptive Phishing <a href="#relationship-to-adaptive-phishing" id="relationship-to-adaptive-phishing"></a>

AURA complements [Adaptive Phishing](adaptive-phishing-programs.md):

* **AURA maintains knowledge through structured education.**
* **Adaptive Phishing evaluates user behavior through ongoing simulations.**

Together, they provide continuous education and continuous behavioral testing.
{% endhint %}

## Program Configuration <a href="#how-it-works.1" id="how-it-works.1"></a>

{% hint style="success" %}
Understanding these terms is essential to understanding AURA.
{% endhint %}

<table data-header-hidden><thead><tr><th width="127">Term</th><th>Definition</th></tr></thead><tbody><tr><td><strong>Topic</strong></td><td><p>A cybersecurity subject (e.g., Phishing, Passwords, MFA).</p><p>AURA contains 18 predefined topics.</p></td></tr><tr><td><strong>Course</strong></td><td>The main learning material for a topic.</td></tr><tr><td><strong>Awareness Boost</strong></td><td>A short refresher sent after the course to reinforce knowledge.</td></tr><tr><td><strong>Valid Course</strong></td><td>A course that was completed and has not expired yet.</td></tr><tr><td><strong>Valid Topic</strong></td><td>A topic where the course is valid (boost not required for validity).</td></tr><tr><td><strong>Resilience</strong></td><td>A percentage score that shows how well a user is protected for a topic.</td></tr><tr><td><strong>Reminder</strong></td><td>Automatic follow-up email if a user has not completed assigned material.</td></tr><tr><td><strong>Repeat Offender</strong></td><td>A user who received at least one course for every topic and completed none.</td></tr></tbody></table>

For each awareness topic, administrators define:

* The required Course
* The Topic and Course validity period (when it expires)
* The Boost (short reinforcement material such as videos, games, or short learning units)
* How often Boosts should be sent
* The target audience

This setup defines the organization’s structured awareness program.

***

### Continuous Automated Education <a href="#id-2.-continuous-automated-education" id="id-2.-continuous-automated-education"></a>

After activation, AURA regularly checks all users and determines:

* Who has not completed required Courses
* Whose Courses validity has expired
* Who is due to receive Boost content
* Who has not engaged with previously assigned material

Based on this evaluation, AURA automatically sends the relevant course or booster to each user.

Education is assigned per user based on:

* Completed Courses
* Expiration status
* Boost history
* Outstanding requirements

No recurring manual campaign creation is required.

***

### Courses Lifecycle Management <a href="#id-3.-courses-lifecycle-management" id="id-3.-courses-lifecycle-management"></a>

AURA continuously monitors courses validity and ensures:

* Courses are reassigned when they expire
* Users receive reminders when required
* Training coverage remains up to date

This prevents awareness levels from degrading over time.

***

### Risk & Progress Dashboard <a href="#id-4.-risk-and-progress-dashboard" id="id-4.-risk-and-progress-dashboard"></a>

AURA includes a dashboard providing visibility into:

* Overall training completion rates
* Completion per security awareness topic
* Courses validity status
* Boost delivery and engagement
* Progress over time

Security officers can monitor awareness coverage across the organization and identify gaps.

***

{% hint style="danger" %}
## Limitations in the Beta release <a href="#beta-version-current-limitations" id="beta-version-current-limitations"></a>

### Content & Template Structure <a href="#content-and-template-structure" id="content-and-template-structure"></a>

* Fixed structure of **18 predefined topics**
* Each topic includes **1 course and 2 boost templates** (total: 54 templates)
* All templates must be pre-installed in Lucy before AURA activation
* Template usage is hard-coded in the AURA database
* Administrators cannot:
  * Select alternative templates
  * Replace templates
  * Define custom topics
  * Attach custom templates to topics

***

### Language Support <a href="#language-support" id="language-support"></a>

* English only
* All awareness materials are sent in English regardless of the user’s preferred language
* This must be communicated clearly to multilingual customers

***

### Deployment & Architecture <a href="#deployment-and-architecture" id="deployment-and-architecture"></a>

* Designed to run exclusively on a VPS with internet access
* Not compatible with on-premise Lucy deployments
* Running multiple AURA instances connected to a single Lucy environment is not recommended and not fully tested
* Supporting multiple clients would require separate VPS deployments
* The current codebase is not optimized for large parallel instances with heavy recipient groups

***

### Administration Constraints <a href="#administration-constraints" id="administration-constraints"></a>

* Only one administrator account supported
* No administrator management interface
* Only one active AURA program instance can run per Lucy environment

***

### Testing Constraints <a href="#testing-constraints" id="testing-constraints"></a>

* Initial training assignments can be observed within a day
* Boosts are triggered one month after course completion
* Full course and boost flow testing requires extended time
* Short test cycles are not practical
{% endhint %}
