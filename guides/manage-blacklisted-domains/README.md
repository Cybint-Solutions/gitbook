# Manage Blacklisted Domains

Domains used in phishing simulations are evaluated using the same security mechanisms and algorithms as any other domain to determine their legitimacy. Consequently, there isn't a singular reason a domain might be blacklisted. However, adhering to best practices can significantly reduce the risk of a domain being blacklisted.

<details>

<summary>Why was my domain blacklisted?</summary>

In the context of phishing simulations using Lucy, domains can be blacklisted based on several factors. Each security vendor uses different detection mechanisms to identify malicious domains. Here are some key factors:

1. **Spoofed Brands:**
   * Domains mimicking well-known brands (e.g., Google, Facebook, Microsoft) can be flagged. For example, Google’s algorithms detect visual and structural similarities to known brands to prevent phishing.
2. **Phishing Indicators:**
   * If the domain hosts landing pages that solicit login credentials, personal information, or payment details, it can be flagged as a phishing site.
3. **New or Untrusted Domains:**
   * Newly registered domains often lack a reputation. If these domains are used for phishing simulations, they are more likely to be blacklisted.
4. **Domain Configuration:**
   * The setup of SPF, MX, and A records pointing to the Lucy server is scrutinized. Misconfigurations or anomalies in these records can trigger blacklisting. Checks are done for alignment with typical usage patterns and legitimate email configurations.
5. **SSL Certificates:**
   * Even with valid SSL certificates, if the domain shows signs of misuse or if the certificates are not from well-known Certificate Authorities, the domain can be flagged.
6. **Malware Distribution:**
   * If the domain inadvertently hosts or distributes malware (e.g., through attachments or linked downloads), it will be blacklisted. Landing pages can be scanned for malicious software and scripts.
7. **Deceptive Content:**
   * Inspecting content that is intentionally deceptive or misleading, designed to trick users into performing unsafe actions. This includes fake warnings, alerts, and instructions.
8. **Suspicious Behavior Patterns:**
   * High volumes of emails sent from the domain, especially those resembling phishing emails, can raise red flags. Monitoring is done for sending patterns and email content for suspicious activities.
9. **User Reports:**
   * If users report the domain as suspicious or harmful, Google/Microsoft will take these reports into consideration. High numbers of user complaints can lead to a domain being blacklisted.
10. **Embedded Links and Redirects:**
    * Checks are implemented for suspicious links and redirects within the domain. If the site redirects to known malicious or phishing sites, it can be flagged.

</details>

<details>

<summary>What can I do to prevent Blacklisting?</summary>

To minimize the risk of your newly spoofed domains being blacklisted when conducting phishing simulations with content related to known brands like Google, Facebook, and Microsoft, follow these best practices:

### **Choose Reputable Domain Providers:**

* Register your domains with well-known and reputable domain providers. This helps establish initial trust. You can use the built-in [Domain wizard](../../application-screens-reference/settings/common-system-settings/domains/#register) for registration with GoDaddy.

### **Set Up Proper DNS Records:**

* Ensure your SPF, DKIM, and DMARC records are correctly configured to authenticate your emails.
*   [Example SPF record:](../../application-screens-reference/settings/common-system-settings/domains/#dns-records-explained)

    ```plaintext
    v=spf1 ip4:{your_lucy_ip_address} ~all
    ```
*   [Example DKIM record:](../../application-screens-reference/campaigns/campaign-settings/configuration/attack-settings.md#dkim-support)

    ```plaintext
    default._domainkey IN TXT "v=DKIM1; k=rsa; p=<public_key>"
    ```
*   Example DMARC record:

    ```plaintext
    _dmarc IN TXT "v=DMARC1; p=none; rua=mailto:dmarc-reports@yourdomain.com"
    ```

See our platform reference article on [DNS records](../../application-screens-reference/settings/common-system-settings/domains/#add-a-domain)

### **Implement HTTPS:**

* Use SSL/TLS certificates from reputable Certificate Authorities (CAs) to secure your domains. Use the built-in [Let's Encrypt certificate generator](../../application-screens-reference/settings/common-system-settings/ssl-settings/) for your domains.

### **Regularly Update Your DNS Records:**

* Keep your DNS records up-to-date and ensure there are no misconfigurations.

### **Content and Email Practices:**

**Avoid Exact Brand Imitation:**

* Avoid replicating the exact appearance of well-known brands like Google, Facebook, or Microsoft. Introduce subtle changes to the email and landing pages to prevent detection by algorithms.

**Use Clear Disclaimers:**

* Include disclaimers in your emails and landing pages stating that they are part of a security awareness program.

**Limit Email Volume:**

* Send your phishing simulation emails in small batches to avoid triggering spam filters. Use the built-in [Scheduler](../../application-screens-reference/campaigns/campaign-settings/configuration/schedule/) to achieve this.

**Monitor Email Content:**

* Ensure your emails do not contain elements commonly associated with spam or phishing, such as excessive links or suspicious attachments.

**Test Content with Spam Checkers:**

* Use tools like Mail-Tester or Litmus to test your emails for spammy elements before sending them out.

### **Domain Management and Monitoring:**

**Warm-Up Your Domain:**

* Gradually increase your email sending volume to establish a good sending reputation. Use the built-in [Scheduler](../../application-screens-reference/campaigns/campaign-settings/configuration/schedule/) to achieve this.

**Monitor Domain Health:**

* Use tools like [Google Search Console ](https://search.google.com/search-console/about)to monitor your domain’s health and address any issues promptly.

**Engage in Regular Clean-Up:**

* Periodically review and clean your email lists to ensure you are sending to valid addresses. Use [Lucy's built-in automation](../../application-screens-reference/settings/common-system-settings/ldap-settings.md#action-for-new-users) to automatically keep your users up to date with your organization's directory.&#x20;

### **Google Safe Browsing and User Reports:**

**Regularly Check for Blacklisting:**

* Periodically check your domains using tools like Google Safe Browsing to ensure they are not blacklisted.

**Promptly Address User Reports:**

* Respond quickly to any user reports of suspicious activity related to your domains.

**Verify and Whitelist Your Domain:**

* Verify your domain ownership with Google Search Console and request reviews if blacklisting occurs.

### **Legal and Ethical Considerations:**

**Stay Within Legal Boundaries:**

* Ensure your simulations comply with local laws and regulations regarding email communications and data privacy.

**Communicate with Stakeholders:**

* Inform relevant stakeholders within your organization about the phishing simulations to avoid misunderstandings and false reports to Google.

</details>

***

### Identify Vendors That Have Blacklisted Your Domain

You can use common tools like:

**MXToolbox** -> [https://mxtoolbox.com/blacklists.aspx](https://mxtoolbox.com/blacklists.aspx)

**Google SafeBrowsing** -> [https://www.google.com/webmasters/tools/security-issues](https://www.google.com/webmasters/tools/security-issues)

**Virus Total** -> [https://www.virustotal.com/gui/home/url](https://www.virustotal.com/gui/home/url)

* Enter your blacklisted domain
* Make a note of all blacklisted vendors

{% hint style="info" %}
If your domain is displaying "Deceptive Site Ahead" in Chrome, see our guide on [Google SafeBrowsing](managing-google-safebrowsing-alerts.md)
{% endhint %}

***

### Delisting a Blacklisted Domain

Most vendors allow you to submit a false positive claim to remove a blacklisted domain. Each vendor has specific procedures for this. Below is a list of vendors and their respective whitelisting processes:

{% hint style="success" %}
Our [Technical Support](../../when-to-contact-us/contact-technical-support.md) team is available to assist you with de-listing your domain.
{% endhint %}

| Vendor                                    | Contact Email                                                                    | False Positive Reporting                                                                                                                                                                                        |
| ----------------------------------------- | -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 360                                       | kefu@360.cn                                                                      | N/A                                                                                                                                                                                                             |
| Abusix                                    | support@abusix.com                                                               | [Abusix Lookup](https://lookup.abusix.com/)                                                                                                                                                                     |
| Acronis                                   | virustotal-falsepositive@acronis.com                                             | N/A                                                                                                                                                                                                             |
| ADMINUSLabs                               | info@adminuslabs.net, samples@adminus.net, falsepositive@adminuslabs.net         | N/A                                                                                                                                                                                                             |
| AegisLab                                  | support@aegislab.com                                                             | N/A                                                                                                                                                                                                             |
| Ahnlab                                    | e-support@ahnlab.com, samples@ahnlab.com                                         | N/A                                                                                                                                                                                                             |
| AILabs (Monitorapp)                       | aicc@monitorapp.com                                                              | N/A                                                                                                                                                                                                             |
| Alibaba                                   | virustotal@list.alibaba-inc.com                                                  | N/A                                                                                                                                                                                                             |
| AliCloud                                  | antivirus@alibabacloud.comm                                                      | N/A                                                                                                                                                                                                             |
| AlienVault                                | otx-support@alienvault.com                                                       | N/A                                                                                                                                                                                                             |
| AlphaMountain                             | support@alphamountain.freshdesk.com                                              | N/A                                                                                                                                                                                                             |
| AlphaSOC                                  | virustotal@alphasoc.com                                                          | N/A                                                                                                                                                                                                             |
| Alyac (Estsoft)                           | esrc@estsecurity.com                                                             | N/A                                                                                                                                                                                                             |
| Antivir (Avira)                           | N/A                                                                              | [Avira Submit URL](https://www.avira.com/en/analysis/submit-url)                                                                                                                                                |
| Antiy                                     | avlsdk\_support@antiy.cn                                                         | N/A                                                                                                                                                                                                             |
| Arcabit                                   | vt.fp@arcabit.pl                                                                 | N/A                                                                                                                                                                                                             |
| ArcSight Threat Intelligence              | arcsight-virustotal@microfocus.com                                               | N/A                                                                                                                                                                                                             |
| AutoShun                                  | info@autoshun.org                                                                | N/A                                                                                                                                                                                                             |
| Avast                                     | DL-Virus@gendigital.com                                                          | N/A                                                                                                                                                                                                             |
| AVG                                       | N/A                                                                              | [AVG Submit Sample](http://www.avg.com/submit-sample), [AVG Whitelist](http://www.avg.com/us-en/whitelist)                                                                                                      |
| Baidu                                     | bav@baidu.com, gaoyingchun@baidu.com                                             | N/A                                                                                                                                                                                                             |
| BitDefender                               | virus\_submission@bitdefender.com                                                | N/A                                                                                                                                                                                                             |
| BforeAi                                   | N/A                                                                              | [BforeAi Support](https://bfore.ai/support)                                                                                                                                                                     |
| Bkav                                      | fpreport@bkav.com, bkav@bkav.com                                                 | N/A                                                                                                                                                                                                             |
| Certego                                   | N/A                                                                              | [Certego Contact](https://www.certego.net/company/contact-us/)                                                                                                                                                  |
| Chong Lua Dao                             | info@chongluadao.vn                                                              | N/A                                                                                                                                                                                                             |
| CINS Army (Sentinel IPS)                  | cins@sentinelips.com                                                             | [CINS Army Contact](http://cinsscore.com/#contact)                                                                                                                                                              |
| ClamAV                                    | N/A                                                                              | [ClamAV Reports](http://www.clamav.net/reports/fp)                                                                                                                                                              |
| Clean-MX                                  | abuse@clean-mx.de                                                                | N/A                                                                                                                                                                                                             |
| Cluster25                                 | threatintel@cluster25.io                                                         | N/A                                                                                                                                                                                                             |
| CMC                                       | PSIRT@cmccybersecurity.com                                                       | N/A                                                                                                                                                                                                             |
| CRDF                                      | N/A                                                                              | [CRDF False Positive](https://threatcenter.crdf.fr/false_positive.html)                                                                                                                                         |
| Criminal IP (AI Spera)                    | support@aispera.com                                                              | N/A                                                                                                                                                                                                             |
| CrowdStrike                               | VTscanner@crowdstrike.com                                                        | N/A                                                                                                                                                                                                             |
| CSIS Security Group                       | abuse-reporting@csis.com                                                         | N/A                                                                                                                                                                                                             |
| CyanSecurity                              | virustotal@cyansecurity.com                                                      | N/A                                                                                                                                                                                                             |
| Cybereason                                | vt-feedback@cybereason.com                                                       | N/A                                                                                                                                                                                                             |
| Cyble                                     | cyblevt\_patnership@cyble.com                                                    | N/A                                                                                                                                                                                                             |
| Cylance                                   | cylancefilesubmit@cylance.com                                                    | N/A                                                                                                                                                                                                             |
| Cynet                                     | soc@cynet.com                                                                    | N/A                                                                                                                                                                                                             |
| CyRadar                                   | virustotal@cyradar.com                                                           | N/A                                                                                                                                                                                                             |
| Deep Instinct                             | vt-fps-requests@deepinstinct.com                                                 | N/A                                                                                                                                                                                                             |
| DNS8                                      | dns8@layer8.pt                                                                   | N/A                                                                                                                                                                                                             |
| DrWeb                                     | vms@drweb.com                                                                    | N/A                                                                                                                                                                                                             |
| eGambit (Tehtris)                         | virus@tehtris.com                                                                | [Tehtris eGambit FP](https://tehtris.com/en/forms/false-positives-false-negatives/)                                                                                                                             |
| Elastic                                   | fp\_reports@elastic.co                                                           | [Elastic Discuss](https://discuss.elastic.co/t/submitting-false-positives/232322)                                                                                                                               |
| Emsisoft                                  | submit@emsisoft.com, fp@emsisoft.com                                             | [Emsisoft Contact](https://www.emsisoft.com/en/help/1720/why-did-an-emsisoft-product-detect-an-innocent-file-as-malware-2/)                                                                                     |
| ESET                                      | N/A                                                                              | [ESET Support](https://support.eset.com/kb141/?page=content\&id=SOLN141)                                                                                                                                        |
| FireEye                                   | virustotal@fireeye.com                                                           | N/A                                                                                                                                                                                                             |
| F-Prot                                    | viruslab@f-prot.com                                                              | N/A                                                                                                                                                                                                             |
| F-Secure/WithSecure                       | spyware-samples@f-secure.com, vsamples@f-secure.com                              | N/A                                                                                                                                                                                                             |
| Forcepoint ThreatSeeker                   | reviewmysite@forcepoint.com                                                      | N/A                                                                                                                                                                                                             |
| Fortinet                                  | [Fortinet Contact Support](http://www.fortinet.com/support/contact_support.html) | [Fortinet Classification Dispute](https://www.fortiguard.com/faq/classificationdispute)                                                                                                                         |
| GData                                     | N/A                                                                              | [GData Submit Suspicious File](https://www.gdatasoftware.com/faq/consumer/submit-a-suspicious-file-app-or-url)                                                                                                  |
| Google (File Scanner)                     | google-at-virustotal@google.com                                                  | N/A                                                                                                                                                                                                             |
| Google Safe Browsing (URL/Netloc Scanner) | N/A                                                                              | [Google Safe Browsing Report](https://safebrowsing.google.com/safebrowsing/report_error/?hl=en)                                                                                                                 |
| GreenSnow                                 | N/A                                                                              | [GreenSnow Contact](https://greensnow.co/contact)                                                                                                                                                               |
| Gridinsoft                                | virus@gridinsoft.com                                                             | N/A                                                                                                                                                                                                             |
| Hacksoft                                  | virus@hacksoft.com.pe                                                            | N/A                                                                                                                                                                                                             |
| Hauri                                     | viruslab@hauri.co.kr                                                             | N/A                                                                                                                                                                                                             |
| Heimdal                                   | report-vt@heimdalsecurity.com                                                    | N/A                                                                                                                                                                                                             |
| Hunt.io Intelligence                      | k.lo@hunt.io                                                                     | N/A                                                                                                                                                                                                             |
| Hoplite Industries                        | vt-info@hopliteindustries.com                                                    | N/A                                                                                                                                                                                                             |
| Ikarus                                    | fp@ikarus.at                                                                     | N/A                                                                                                                                                                                                             |
| IPsum                                     | N/A                                                                              | [IPsum GitHub](https://github.com/stamparm/ipsum)                                                                                                                                                               |
| Jiangmin                                  | support@jiangmin.com, shaojia@jiangmin.com                                       | N/A                                                                                                                                                                                                             |
| K7                                        | reportfp@labs.k7computing.com, k7viruslab@labs.k7computing.com                   | N/A                                                                                                                                                                                                             |
| Kaspersky                                 | newvirus@kaspersky.com                                                           | N/A                                                                                                                                                                                                             |
| Kingsoft                                  | ti@mingting.cn                                                                   | N/A                                                                                                                                                                                                             |
| Lionic                                    | support@lionic.com                                                               | [Lionic Report FP](https://www.lionic.com/reportfp/)                                                                                                                                                            |
| Lumu                                      | vt@lumu.io                                                                       | N/A                                                                                                                                                                                                             |
| Malbeacon                                 | vtreport@malbeacon.com                                                           | N/A                                                                                                                                                                                                             |
| Malwarebytes                              | N/A                                                                              | [Malwarebytes False Positives](https://forums.malwarebytes.com/forum/122-false-positives/)                                                                                                                      |
| Malwares.com (Saint Security)             | kog@stsc.com                                                                     | N/A                                                                                                                                                                                                             |
| MalwareURL                                | team@malwareurl.com                                                              | N/A                                                                                                                                                                                                             |
| MAX (SaintSecurity)                       | root@malwares.com                                                                | N/A                                                                                                                                                                                                             |
| MaxSecure                                 | tech@maxpcsecure.com                                                             | N/A                                                                                                                                                                                                             |
| McAfee                                    | virus\_research@mcafee.com                                                       | N/A                                                                                                                                                                                                             |
| Skyhigh                                   | virus\_research\_gateway@avertlabs.com                                           | N/A                                                                                                                                                                                                             |
| Microsoft                                 | N/A                                                                              | [sender.office.com](https://sender.office.com/)                                                                                                                                                                 |
| Microworld                                | samples@escanav.com                                                              | N/A                                                                                                                                                                                                             |
| NANO                                      | false@nanoav.ru                                                                  | N/A                                                                                                                                                                                                             |
| Netcraft                                  | N/A                                                                              | [Netcraft Report Mistake](https://report.netcraft.com/report/mistake)                                                                                                                                           |
| Inca (previous nProtect)                  | virus\_info@inca.co.kr                                                           | N/A                                                                                                                                                                                                             |
| Palo Alto                                 | vt-pan-false-positive@paloaltonetworks.com                                       | N/A                                                                                                                                                                                                             |
| Panda                                     | falsepositives@pandasecurity.com, virussamples@pandasecurity.com                 | N/A                                                                                                                                                                                                             |
| Phishing Database                         | N/A                                                                              | [Phishing Database GitHub](https://github.com/mitchellkrogza/Phishing.Database#please-remove-my-domain-from-this-list-)                                                                                         |
| PhishLabs                                 | info@phishlabs.com                                                               | N/A                                                                                                                                                                                                             |
| Qihoo360                                  | support@360safe.com                                                              | N/A                                                                                                                                                                                                             |
| QuickHeal                                 | viruslab@quickheal.com                                                           | N/A                                                                                                                                                                                                             |
| Quttera                                   | support@quttera.com                                                              | N/A                                                                                                                                                                                                             |
| Rising                                    | N/A                                                                              | [Rising File Check](http://mailcenter.rising.com.cn/filecheck_en/)                                                                                                                                              |
| Sansec eComscan                           | support@sansec.io                                                                | N/A                                                                                                                                                                                                             |
| Sangfor                                   | virustotal@sangfor.com.cn                                                        | N/A                                                                                                                                                                                                             |
| Scumware.org                              | N/A                                                                              | [Scumware Removals](https://www.scumware.org/removals.php)                                                                                                                                                      |
| SecureAge                                 | N/A                                                                              | [SecureAge Report FP](https://www.secureaplus.com/features/antivirus/report-false-positive/)                                                                                                                    |
| Seclookup                                 | info@seclookup.com                                                               | N/A                                                                                                                                                                                                             |
| Segasec                                   | support@segasec.com                                                              | N/A                                                                                                                                                                                                             |
| Sentinel One                              | report@sentinelone.com                                                           | N/A                                                                                                                                                                                                             |
| SOCRadar                                  | vt@socradar.io                                                                   | N/A                                                                                                                                                                                                             |
| Sophos                                    | samples@sophos.com                                                               | [Sophos Support](https://support.sophos.com/support/s/article/KB-000033301?language=en_US)                                                                                                                      |
| Spamhaus                                  | N/A                                                                              | [Spamhaus DBL Removal](https://check.spamhaus.org/)                                                                                                                                                             |
| Sucuri                                    | soc@sucuri.net                                                                   | N/A                                                                                                                                                                                                             |
| Symantec                                  | N/A                                                                              | [Symantec Submit FP](https://symsubmit.symantec.com/submit/false_positive), [Symantec Content Submission](https://knowledge.broadcom.com/external/article/173729/how-to-submit-false-positives-on-content.html) |
| Tencent                                   | TAVfp@tencent.com                                                                | N/A                                                                                                                                                                                                             |
| TheHacker                                 | virus@hacksoft.com.pe, falsopositivo@hacksoft.com.pe                             | N/A                                                                                                                                                                                                             |
| Trapmine                                  | fp@trapmine.com                                                                  | N/A                                                                                                                                                                                                             |
| TrendMicro                                | virus@trendmicro.com, virus\_doctor@trendmicro.com                               | [TrendMicro Detection Re-evaluation](https://www.trendmicro.com/en_us/about/legal/detection-reevaluation.html)                                                                                                  |
| Trustwave                                 | N/A                                                                              | [Trustwave Detection Review](https://support.trustwave.com/virustotal-detection-review/)                                                                                                                        |
| Trustlook                                 | bd@trustlook.com                                                                 | N/A                                                                                                                                                                                                             |
| Underworld                                | post@helsecert.no                                                                | N/A                                                                                                                                                                                                             |
| URLQuery                                  | contact@urlquery.net                                                             | N/A                                                                                                                                                                                                             |
| Varist                                    | support@varist.com, virus@avsubmit.com                                           | N/A                                                                                                                                                                                                             |
| VBA32                                     | feedback@anti-virus.by                                                           | N/A                                                                                                                                                                                                             |
| Viettel Threat Intelligence               | cyberthreat@viettel.com.vn                                                       | N/A                                                                                                                                                                                                             |
| Vipre                                     | productsupport@vipre.com                                                         | N/A                                                                                                                                                                                                             |
| VirIT                                     | virustotal@viritpro.com                                                          | N/A                                                                                                                                                                                                             |
| VirusDie                                  | partners@virusdie.com                                                            | N/A                                                                                                                                                                                                             |
| Webroot                                   | N/A                                                                              | [Webroot Vendor Dispute](https://www.webroot.com/us/en/business/support/vendor-dispute-contact-us)                                                                                                              |
| WithSecure/F-Secure                       | spyware-samples@f-secure.com, vsamples@f-secure.com                              | N/A                                                                                                                                                                                                             |
| Xcitium Verdict Cloud (Comodo)            | support@xcitium.com                                                              | N/A                                                                                                                                                                                                             |
| Yomi                                      | yomi-false-positives@yoroi.company                                               | N/A                                                                                                                                                                                                             |
| Yandex                                    | yandex-antivir@support.yandex.ru                                                 | N/A                                                                                                                                                                                                             |
| Yandex Safebrowsing                       | sbapi@support.yandex.ru                                                          | N/A                                                                                                                                                                                                             |
| Zillya                                    | virus@zillya.com                                                                 | N/A                                                                                                                                                                                                             |
| ZoneAlarm                                 | zonealarm\_VT\_reports@checkpoint.com                                            | N/A                                                                                                                                                                                                             |
| Zoner                                     | false@zonerantivirus.com                                                         | N/A                                                                                                                                                                                                             |
