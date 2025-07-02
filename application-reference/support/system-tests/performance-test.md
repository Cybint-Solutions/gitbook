# Performance Test

### Introduction

The Performance Test Module helps ensure your hardware meets your campaign requirements.

With it you can:

1. **Run a Performance Test**: Check if your hardware can manage the specified number of recipients.
2. **Verify Campaign Settings**: Ensure that your campaign settings are optimized for performance.

For detailed hardware recommendations, refer to [this wiki page](../../../guides/installing-lucy/hardware-requirements.md).

{% hint style="info" %}
Navigate to **Support -> System Tests -> Performance Test**
{% endhint %}

***

### Running the performance test

To run the test simply enter the expected number of recipients and click **Start Test**.

<figure><img src="../../../.gitbook/assets/image (874).png" alt=""><figcaption></figcaption></figure>

You will be prompted to enter an email address as the sender, be sure to use an email address you would really use in a campaign.

{% hint style="warning" %}
In order to run the performance test you must pause all campaigns on the workstation.
{% endhint %}

***

### Performance test results

Depending on the number of recipients you entered the test may take between 10 and 15 minutes to complete, perhaps longer for a really large number of recipients (in the 10s of thousands). Once the test is complete you can view the results to get a breakdown of your workstation's capacity in terms of email sending rate and concurrent connections.

<figure><img src="../../../.gitbook/assets/image (875).png" alt=""><figcaption></figcaption></figure>

Select a timeframe for the campaign and the results will adjust to account for the allotted time - a longer campaign window allows for a larger campaign with more recipients.

