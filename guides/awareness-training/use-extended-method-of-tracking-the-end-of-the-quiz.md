# Use extended method of tracking the end of the quiz

### Introduction

"Use extended method of tracking the end of the quiz" is available to monitor when users complete a quiz at a pre-defined placeholder within the Awareness template. This option can be found on the Awareness Template editing page.

<figure><img src="../../.gitbook/assets/image (533).png" alt=""><figcaption></figcaption></figure>

### Configuration

{% hint style="info" %}
The default state of this feature is disabled.
{% endhint %}

To activate this method, add a call to the additional function `lucyQuizEnd()` without any parameters. Call this function after the user answers the last question in your desired quiz.

{% hint style="danger" %}
Enabling this option without calling the `lucyQuizEnd()` function will prevent recipients from being marked as "trained". By default, Lucy marks each recipient as "Trained" after receiving the first answer to the quiz. Enabling the "Use extended method of tracking the end of the quiz" option and calling the `lucyQuizEnd()` function allows you to set the "Trained" status at the appropriate moment.
{% endhint %}

Using the awareness template "**Internet Security**" as an example:

{% hint style="info" %}
Navigate to **Templates -> Awareness Templates**&#x20;
{% endhint %}

Select "Edit Template"

<figure><img src="../../.gitbook/assets/image (535).png" alt="" width="273"><figcaption></figcaption></figure>

Select "**Content Template**"

<figure><img src="../../.gitbook/assets/image (536).png" alt=""><figcaption></figcaption></figure>

To enhance the "**Internet Security**" template, integrate the `lucyQuizEnd()` function into the source code to process quiz answers. The quiz consists of 9 questions, aiming to identify users who correctly answer at least 5. Activate the "**Use extended method of tracking the end of the quiz**" option in the Website section of the Awareness Settings for the campaign.

Use your "**File**" drop-down to navigate to the correct file javascript file `game.js`

{% hint style="warning" %}
This file might vary depending on the template.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (537).png" alt=""><figcaption></figcaption></figure>

1. Add a new variable `correctAnswerCount` to keep track of the number of correct answers:

<figure><img src="../../.gitbook/assets/image (538).png" alt=""><figcaption></figcaption></figure>

5. Find the place in the code where the function `lucyQuizAnswer()` is called and insert a call to the function `lucyQuizEnd()` after it with the condition as shown below:

<figure><img src="../../.gitbook/assets/image (539).png" alt=""><figcaption></figcaption></figure>

6. Save the template and run the campaign. After 5 quiz questions are answered correctly, the recipient will be marked as "**Trained**".

{% hint style="danger" %}
Using the function `lucyQuizEnd()` together with the option "**Ignore repeated answers in awareness**" should be avoided, as this function disregards the restrictions set by that option.
{% endhint %}

### Advanced Functions

* `lucyQuizStart(quizNumber, countQuestions, errorHandler)`\
  Starts a quiz for the current user and tracks the time when the quiz started. Useful for templates with randomly sorted questions and a variable number of questions.
* `lucySetVariable(varName, varValue, errorHandler)`\
  Permanently saves text data for the current user.
* `lucyGetVariable(varName, successHandler, errorHandler)`\
  Retrieves previously saved variables by name.

### Troubleshooting

Issue: Lucy marks recipients as 'Trained' without any quiz answers given.\
Solution: Enable the "Quiz" option within the Website section of the Awareness Settings in the campaign.

Issue: Lucy does not mark recipients as 'Trained' despite receiving positive quiz answers.\
Solution: Disable the "Extended method of tracking the end of the quiz" option within the Website section of the Awareness Settings in the campaign, or adjust your awareness template accordingly.
