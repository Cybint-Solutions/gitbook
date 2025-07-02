# Custom Rules & Score Factors

{% hint style="info" %}
Navigate to **Settings > Submitted Email Settings > Custom Rules**
{% endhint %}

### Custom Rules

Custom Rules enable the creation and storage of regular expressions (regex) to search through the bodies of reported emails. When an email matches a rule, it is assigned a predefined number of points.

**How It Works**

1. **Define Regex Patterns**: Create regex patterns that identify specific text within email bodies.
2. **Set Points**: Assign a point value to each regex pattern.
3. **Scan Emails**: LUCY scans reported emails for text matching the stored regex patterns.
4. **Assign Points**: Emails that match a regex pattern are assigned the corresponding points.

<figure><img src="../../../.gitbook/assets/image (712).png" alt=""><figcaption><p>You can use an online tool like <a href="https://regexr.com/">https://regexr.com/</a> to help you build regular expressions.</p></figcaption></figure>

***

### Score Factors

{% hint style="info" %}
Navigate to **Settings > Submitted Email Settings > Score Factors**
{% endhint %}

These score factors are a multiplier that applies to each type of score. You can apply more or less weight to each type in order to fine-tune your results based on your organization's specific needs.

<figure><img src="../../../.gitbook/assets/image (713).png" alt=""><figcaption><p>A value of 1 is neutral because the score will be multiplied by 1.</p></figcaption></figure>
