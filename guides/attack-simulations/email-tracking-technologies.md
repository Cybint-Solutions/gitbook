# Email Tracking Technologies

### Introduction

Tracking email opens can be achieved through various technologies:

**Read-receipts:** Employed by applications like Microsoft Office Outlook and Mozilla Thunderbird, this technology allows senders to request a notification when an email is opened. However, it is not supported by web-based mail clients or mobile devices, and users can disable this feature or ignore the requests.

**Tracking Images (Tracking Pixels):** These are tiny (often 1x1 pixel) GIF files embedded in emails, known as beacons. When the email is opened, the pixel loads the GIF from a server, logging an event that indicates the email has been opened. However, if the mail client has disabled automatic image loading, the tracking will not work.

**Link Tracking:** This involves embedding unique identifiers in links within the email. When a recipient clicks on a link, the event is logged, providing reliable data on user engagement.

### **LUCY's approach to Tracking opened emails**

LUCY employs tracking images and link tracking but avoids read-receipts due to their limited reliability and perceived intrusiveness. Link tracking is highly effective as it automatically provides data based on link interactions. It is enabled by default and requires no manual setup.

### **Challenges with Tracking Pixels**

* **Automatic Image Loading Disabled:** If the recipient's email client has disabled automatic image loading, the tracking pixel will not load, and no open event will be logged.
* **Preliminary Image Downloading:** Some email clients may download external content preemptively for caching or security, which might falsely indicate an email as opened.

### **Configuration**

Email tracking settings can be adjusted within the [scenario settings of a campaign](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#advanced-tracking), allowing for tailored tracking strategies based on campaign goals and the technology's limitations.
