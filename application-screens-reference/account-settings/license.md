# License

### Introduction

The license section provides comprehensive details about the type of license for your Lucy server, including your server's Workstation ID and related balance information. It also allows you to upload additional funds for smishing campaigns and domain registration.

***

### Workstation ID:

{% hint style="info" %}
Navigate to **User Account -> License**

![](<../../.gitbook/assets/image (739).png>)
{% endhint %}

<figure><img src="../../.gitbook/assets/image (740).png" alt=""><figcaption></figcaption></figure>

This is your Lucy server's unique identifier. We always require this ID when updating licenses or when you interact with our [Technical Support Department](../../when-to-contact-us/contact-technical-support.md).

{% hint style="warning" %}
Please ensure to always include your Workstation ID when referring to your server, whether for account-related or support-related inquiries, to avoid any delays in processing your request.
{% endhint %}

***

### License Type

We offer three license types: Core, Pro, and Elite. This parameter will indicate which license your Lucy server is currently activated for. For more information about the different license types, please visit our [website](https://thrivedx.com/for-enterprise/pricing) for further details.

{% hint style="info" %}
For renewal please reach out to your Customer Success Manager, or ask to be connected at [support@lucysecurity.com](mailto:%20support@lucysecurity.com)
{% endhint %}

***

### Balance

This is your current balance (USD) for your Lucy server. A positive balance is required when launching [smishing campaigns](../../guides/attack-simulations/attack-types/smishing.md) or [registering a domain](../settings/common-system-settings/domains/#register-a-domain-via-the-domain-registration-wizard).

* Balance can be uploaded to your server by selecting the "Add" button

<figure><img src="../../.gitbook/assets/image (788).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Lucy no longer uses PayPal to add funds to your workstation, we have switched to [Stripe](https://stripe.com/).

If your workstation is on version **5.0 or greater**, Stripe has been integrated on this page and you may proceed with adding funds as normal.

If you are on version **4.14.2 or lower**, please contact your account manager to assist with adding funds to your workstation.

You may also wish to consider [updating](../support/update.md) to the latest version of Lucy.
{% endhint %}

* Fill out the Invoice Details and click "Save"
* Choose to receive the payment link via email, or pay immediately.

<figure><img src="../../.gitbook/assets/image (789).png" alt="" width="537"><figcaption></figcaption></figure>

***

### FAQ

<details>

<summary>My commercial license disappeared</summary>

**Issue:** The Commercial license changed to Community, and extra features are unavailable despite an active long-term license.

**Cause:** This occurs due to Anti-Piracy protection. Lucy Security License Server binds a LUCY instance with a specific Workstation ID to a public IPv4. If the public IPv4 changes, the Workstation ID resets to prevent piracy.

**Solution:** Contact support at support@lucysecurity.com to transfer the license to the new Workstation ID.

**Note:** This can happen with non-static IPv4 or after proxy configuration. Anti-Piracy protection can be deactivated upon request if your external IPv4 is dynamic.

</details>

<details>

<summary>Can I transfer my license to another server?</summary>

**Unique Workstation ID:** Every LUCY installation has a unique, randomized Workstation ID. Upon connecting to the internet after downloading LUCY, you automatically receive this ID. When you purchase a LUCY license, a key is created on a central server associating the Workstation ID with the license key.

**Transferring LUCY License Files:** The license file is stored on our centralized server. To move an existing license, [provide us with the new Workstation ID](../../when-to-contact-us/contact-technical-support.md), and we will update it on our licensing server.

</details>

<details>

<summary>What happens after the license expires?</summary>

**Automatic Renewal:**

* No automatic renewal. Contact your Customer Success Manager or connect with our [Technical Support department](../../when-to-contact-us/contact-technical-support.md) to renew your license.

**Available Features and Data:**

* Only community license features will be available. Data remains safe and will be fully accessible once the license is reactivated.

**Post-Expiration:**

* Community license features remain available.
* The software continues to work with minor updates, but major version updates are not available.

**Cloud LUCY Expiration:**

* The instance will not be immediately canceled. Your Customer Success Manager will contact you to discuss further actions.

</details>

***

### License Details

| Feature                                           | Description                                                                                                   |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Schedule                                          | Allows scheduling of campaigns                                                                                |
| Scheduler Randomization                           | Enables random scheduling to prevent predictability.                                                          |
| Reports                                           | Provides various reporting options to track campaign performance.                                             |
| Comprehensive Reporting                           | Offers detailed and extensive reporting capabilities.                                                         |
| Bounce and Out-of-Office Reporting                | Tracks email bounces and out-of-office replies.                                                               |
| Client View Accounts                              | Allows view-only accounts for your Clients                                                                    |
| Incident User Reputation Profiles                 | Maintains profiles of user reputations based on incidents.                                                    |
| Recipients History                                | Records and tracks the campaign interaction history of recipients.                                            |
| Role-Based Access Controls                        | Grants access based on user roles.                                                                            |
| Multi-Layered User Groups                         | Supports multiple layers of user group hierarchies.                                                           |
| Whitelabel                                        | Enables rebranding to reflect your branding in Lucy.                                                          |
| LDAP Sync                                         | Synchronizes data with LDAP directories.                                                                      |
| DMZ Mode                                          | Allows deployment & operation in a Demilitarized Zone for enhanced security.                                  |
| Rest API                                          | Provides a RESTful API for integration with other systems.                                                    |
| LDAP API                                          | Offers an API for LDAP directory interactions.                                                                |
| SAML Single Sign-On (SSO)                         | Enables single sign-on using SAML.                                                                            |
| Domain API                                        | Provides API access for domain management.                                                                    |
| 2-Factor Authentication                           | Adds an extra layer of security with two-factor authentication.                                               |
| Custom Homepage Creation                          | Allows customization of the homepage.                                                                         |
| URL Shortening                                    | Supports shortening of URLs for campaigns.                                                                    |
| Benchmark                                         | Provides benchmarking tools to compare performance.                                                           |
| Advanced Video Tracking                           | Tracks user interactions with video content.                                                                  |
| Advanced Quiz Tracking                            | Monitors quiz performance and completion.                                                                     |
| Landing Page Time Tracking                        | Tracks time spent on landing pages.                                                                           |
| Realtime Dashboard                                | Displays real-time data and analytics in the Campaign Dashboard and Statistics Dashboard.                     |
| Support for Anonymization and Data Protection     | Ensures data anonymization and protection on a global or campaign level for GDPR and compliance requirements. |
| Reminders                                         | Sends reminders for user engagement on campaigns.                                                             |
| Multi-Language Admin Interface                    | Supports multiple languages for the Lucy admin interface.                                                     |
| Custom Rule-Based Analysis                        | Allows creation of custom rules (RegEx) for reported phishing emails to Lucy.                                 |
| Mobile-Responsive                                 | Ensures mobile compatibility.                                                                                 |
| Incidents Handling                                | Manages and tracks phishing-reported incidents.                                                               |
| Incident Auto Feedback                            | Provides automatic feedback for phishing-reported incidents.                                                  |
| Incident Clients                                  | Manages clients involved in incidents.                                                                        |
| Awareness Education Diploma                       | Provides diplomas for completing awareness education.                                                         |
| End user Training Portal                          | Offers a portal for end-user training.                                                                        |
| Double Barrel Attacks                             | Simulates double-barrel phishing attacks.                                                                     |
| Mixed Attacks                                     | Simulates mixed types of cyber attacks, inclusive of file-based with a landing page.                          |
| Portable Media Attacks                            | Simulates attacks using portable media. (USB / Rubber-Ducky)                                                  |
| Smishing                                          | Simulates SMS phishing attacks.                                                                               |
| Custom Message Bird Account                       | Integrates with custom Message Bird accounts.                                                                 |
| Custom Smsmode Account                            | Integrates with custom Smsmode accounts.                                                                      |
| Java-Based Attacks                                | Simulates attacks using Java vulnerabilities.                                                                 |
| Simultaneous Attack Template Usage                | Supports using multiple attack templates in any given campaign.                                               |
| File-Based Attacks                                | Simulates attacks using malicious files.                                                                      |
| Pentest Kit                                       | Provides tools for penetration testing, specifically the Low Hanging Fruit Collector template (LHFC).         |
| Mail and Web Filter Test                          | Tests mail and web filters.                                                                                   |
| Attack URL Variations                             | Supports variations in attack URLs.                                                                           |
| Data Entry Attacks                                | Simulates attacks through data entry forms.                                                                   |
| Hyperlink Attacks                                 | Simulates attacks using malicious hyperlinks.                                                                 |
| Level-Based Attacks                               | Simulates attacks based on different levels of sophistication and user Risk Levels.                           |
| Ransomware Simulation Attacks                     | Simulates ransomware attacks.                                                                                 |
| Standard Phishing & Training Simulation           | Simulates standard phishing attacks and training.                                                             |
| Spear Phishing Simulation                         | Simulates targeted phishing attacks.                                                                          |
| Integration with Attack Simulations               | Integrates with various attack simulation tools.                                                              |
| Spoofing Test                                     | Tests for email spoofing vulnerabilities.                                                                     |
| Rich Media Awareness Training                     | Provides training with rich media content.                                                                    |
| SCORM Import/Export                               | Supports SCORM import and export for training modules.                                                        |
| Approval Workflows                                | Manages approval processes for various campaign-based tasks.                                                  |
| Reputation Based Learning                         | Adjusts learning based on user reputation.                                                                    |
| Dynamic Training Hints                            | Offers dynamic hints during training sessions.                                                                |
| Export Features                                   | Provides options to export data and reports.                                                                  |
| Advanced Security Features                        | Includes advanced security options like Firewalls, custom Admin ports, and Admin domain paths.                |
| SSL Certificates                                  | Utilizes SSL certificates for secure communications via Let's Encrypt.                                        |
| Certificate-Based Authentication                  | Supports authentication using certificates.                                                                   |
| Multi-Tenant View-Only Access                     | Provides view-only access for multiple Clients.                                                               |
| Active and Passive Client Vulnerability Detection | Detects vulnerabilities in client systems.                                                                    |
| Mail Scanner                                      | Scans emails for malicious content.                                                                           |
| Campaign Templates                                | Provides templates for creating campaigns.                                                                    |
| Campaign Checks                                   | Performs checks on campaign setup and execution.                                                              |
| Campaigns Comparison                              | Compares different campaigns for performance analysis.                                                        |
| Performance Tools                                 | Offers tools to monitor and enhance performance.                                                              |
| Digital Signatures                                | Supports the use of digital signatures.                                                                       |
| Flexible e-Mail Delivery Methods                  | Offers various methods for email delivery.                                                                    |
| DKIM / S/MIME Support for Phishing E-mails        | Supports DKIM and S/MIME for phishing emails.                                                                 |
| Full Mail Communication Client                    | Provides a complete mail communication client.                                                                |
| Website Cloner                                    | Clones websites for simulation purposes.                                                                      |
| Data Entry Validation Toolkit                     | Validates data entry during simulations.                                                                      |
| Powerful URL Redirection Toolkit                  | Offers tools for URL redirection from Attack to Awareness.                                                    |
| Malware Testing Toolkit                           | Provides tools for testing malware.                                                                           |
| Basic Attack Templates                            | Includes basic templates for attack simulations.                                                              |
| Extended Attack Template Library                  | Offers an extended library of attack templates.                                                               |
| Full Attack Template Library                      | Provides a comprehensive library of attack templates.                                                         |
| Multilingual Attack Template Library              | Includes templates in multiple languages.                                                                     |
| Training Library                                  | Provides a library of training materials.                                                                     |
| Basic Education Template Library                  | Includes basic education templates.                                                                           |
| Extended Education Template Library               | Offers an extended library of education templates.                                                            |
| Full Education Template Library                   | Provides a comprehensive library of education templates.                                                      |
| Microlearning Modules                             | Offers modules for microlearning.                                                                             |
| Support Subscription: Standard                    | Provides standard support subscription.                                                                       |
| Support Subscription: Business                    | Provides business-level support subscription.                                                                 |
| Support Subscription: Premium                     | Offers premium support subscription.                                                                          |
| Virtualized Private Server, Professional          | Provides a professional-grade virtual private server.                                                         |
| Virtualized Private Server, Premium               | Offers a premium virtual private server.                                                                      |
| Virtualized Private Server, Ultra                 | Provides an ultra-grade virtual private server.                                                               |
| Sector Specific Templates                         | Includes templates specific to various sectors.                                                               |
| Custom Template Creation                          | Allows creation of custom templates.                                                                          |
| Gmail Plugin                                      | Integrates with Gmail.                                                                                        |
| Outlook Plugin                                    | Integrates with Outlook.                                                                                      |
| Outlook 365 Plugin                                | Integrates with Outlook 365.                                                                                  |
| Plugin Customization Options                      | Offers options to customize mail plugins.                                                                     |
| Multi-Client Compatible                           | Supports multiple clients.                                                                                    |
| Video Customization                               | Allows customization of video content.                                                                        |
| Video Import/Export                               | Supports import and export of video content.                                                                  |
| Offline Training Support                          | Provides support for offline training.                                                                        |
| Easy Installation                                 | Ensures easy installation process.                                                                            |
| Setup Wizard with Risk-Based Guidance             | Guides through setup with risk-based instructions.                                                            |
| Installation Support                              | Provides support during installation.                                                                         |
| Custom Video Creation                             | Allows creation of custom videos.                                                                             |
| Static Training Support                           | Provides support for static training content.                                                                 |
| Consulting Service Subscription                   | Offers consulting service subscriptions.                                                                      |
| Third Party Integration                           | Supports integration with third-party services.                                                               |
| Positive Behavior Reinforcement                   | Encourages positive behavior through reinforcement mechanisms.                                                |
