#projects/tcm 
#resources/phishing

# Intro

How does Phishing Work?

- Authority
- Trust
- Intimidation
- Social Proof
- Urgency
- Scarcity
- Familiarity

Phishing Case Studies

- Colonial Pipeline Attack (2021)
- Levitas Capital (2020)
- Ubiquiti Networks (2015)
- Ukraine’s Power Grid (2015)

# Email Fundamentals

SMTP

Bob (Sender) → (SMTP) Bob’s Mail Server (Gmail) → (SMTP) Alicia’s Mail Server (Yahoo) → (POP3) Alicia (Recipient)

Email Headers

- Metadata of email message

Email Body

- HTML of email content

Email Addresses

- [bob.smith@example.com](mailto:bob.smith@example.com)
    - Local Part (Mailbox)
    - Domain
    - Top-Level Domain

Email Protocols

- SMTP (25 or 465 587)
- POP3 (110 or 995)
    - Email is downloaded and then deleted on server.
    - Email can only be seen on a single device
- IMAP (143 or 993)
    - Email is stored on server
    - Email can be viewed on multiple devices

Mail Agents

- Mail Transfer Agent (MTA)
    - Routes and transfer email messages across mail servers
- Mail User Agent (MUA)
    - Compose, send, receives, emails
    - Gmail, Yahoo, Thunderbird, Outlook
- Mail Delivery Agent (MDA)
    - Accepting incoming email messages from MTAs
    - Places email in recipients inbox

# Requirements

Install the following

- git clone [https://github.com/MalwareCube/SOC101](https://github.com/MalwareCube/SOC101) onto Ubuntu VM and WIndows VM
    - unzip course files into Ubuntu VM and Windows VM
    - run ./SOC101/resources/install/install.sh within Ubuntu VM
- Configure Windows VM
    - **PowerShell Commands**
        - Disable real-time protection: `Set-MpPreference -DisableRealtimeMonitoring $true`
        - Disable network file scanning: `Set-MpPreference -DisableScanningNetworkFiles $true`
        - Disable first sight blocking: `Set-MpPreference -DisableBlockAtFirstSeen $true`
        - Disable Windows Defender AntiSpyware: `reg add "HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f`
        - Clone repository: `git clone <https://github.com/MalwareCube/SOC101.git`>
    - Next, extract each of the course ZIP files onto the desktop using the password below:
        - ZIP password: `murky-backboard-headache`
- Configure Ubuntu
    - Thunderbird
    - Sublime

# Phishing Attack Types and techniques
#resources/phishing-techniques
## Types

Information Gathering

- Reconnaissance

Credential Harvesting

- Obtain login credentials from victims

Malware Delivery

- Delivering a payload/malware to a victims computer

[[Spear Phishing]]

- Phishing curated toward specific target

Whaling

- Targeting high profile

[[Vishing]], [[Smishing]], [[QRPhishing]]

- Alternative methods of phishing through phone calls, SMS, or QR codes

[[Business Email Compromise (BEC)]]

Spam

- Mass email through-put

## Techniques

Pretexting

- Manipulating under false pretense

Spoofing and Impersonation

- Email spoofing

URL Manipulation

- URL shortening
- Subdomain Spoofing
- Changing URL to look legit

Encoding

- Obfuscate and evade detection

Attachments

- Malicious downloads and executables

Abuse of Legitimate Services

- Using services such as Google Drive, Dropbox, etc to send malware

Pharming

- Two-step technique
- DNS Poisoning

Links

- [](https://bitly.com/)[https://bitly.com](https://bitly.com)
- [](https://unshorten.it/)[https://unshorten.it](https://unshorten.it)
- [https://www.irongeek.com/homoglyph-attack-generator.php](https://www.irongeek.com/homoglyph-attack-generator.php)
- [https://github.com/elceef/dnstwist](https://github.com/elceef/dnstwist)
- [https://dnstwist.it/](https://dnstwist.it/)
- [https://dnstwister.report/](https://dnstwister.report/)
- [https://phishtank.org/](https://phishtank.org/)

# Phishing Analysis Methodology

Initial Triage

- Determine attributes to determine threat level

Header and Sender Examination

- Investigate MTA’s, addresses, IPs
- Identify the true origin

Content Examination

- Analyze for language, formatting, etc

Web and URL Examination

- Collect web artifacts

Attachment Examination

- attachment examination

Contextual Examination

- Consider broader context, recent or current incidents
- Look for patterns

Defense Measures

- Take reactive defense actions (if needed)
- Take proactive defense actions

Document and reporting

- Always be documenting throughout an investigation

# Email Header and Sender Analysis

Most emails are downloadable through the MTA

|Standard Headers||
|---|---|
|Date|Timestamps create timelines|
|From|Most common spoofed header|
|Subject|“Signature of email”|
|Message-ID|Unique ID by first MTA message traverses through. Duplicate ID could mean malicious activity|
|To|Recipients|
|Reply-To|Common way for attackers to redirect traffic to attacker email|
|Return-Path:|Checkwith From Header. Mass fish|
|||
|X-Sender-IP / X-Originating-IP|IP reputation can be tracked. Certain email providers do not include this|
|**Received:**|Typically see more than one|
|Show’s how many MTA’s.||
|Reliable metric||
|Reverse chronological order||

Tools for investigation

- whois
- [DomainTools.com](http://DomainTools.com)
- Message Header Analyzer
- MXToolBox

# Email Authentication Methods

Sender Policy Framework (SPF)

DKIM

DMARC

Tools

- nslookup
- dig

# Email Content Analysis

Download the email and search the content for suspicious links, bodies, or obfuscated text.

Tool

- CyberChef
    - URL Encoding
    - Base64 Encoding
    - HTML Entity

# The Anatomy of a URL

Clean URL example:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/da4464e2-a892-4dd0-ae84-8806ab1bbd40/image.png)

Phishing URL example:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/93fdbb45-8c2b-4d09-8095-a24a3f7683be/image.png)

Subdomain spoofing with legitimate service:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/99c294f8-5587-434f-b059-139de5fb2dad/image.png)

Subdomain spoofing with legitimate service:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/957457b4-bc76-46ef-854c-1732931fa1fa/image.png)

Lookalike domain:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/69a1c7bc-8654-4751-9811-b43a92d13c7c/image.png)

Legitimate URL:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/70f89670-4e45-4423-bda6-5d670923e02f/image.png)

Mimic typosquating:

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/523f65b7-d9e2-4f61-a7f5-cad973488594/2dfe27a6-e831-4f16-bb62-4c9f7bc263bb/image.png)

# Email URL Analysis

Tools

- [](https://gchq.github.io/CyberChef)[https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/)
- [https://github.com/MalwareCube/Email-IOC-Extractor](https://github.com/MalwareCube/Email-IOC-Extractor)
- [https://phishtank.org/](https://phishtank.org/)
- [https://www.url2png.com/](https://www.url2png.com/)
    - screenshots as a service
- [https://urlscan.io/](https://urlscan.io/)
- [https://www.virustotal.com/gui/home/upload](https://www.virustotal.com/gui/home/upload)
- [https://www.urlvoid.com/](https://www.urlvoid.com/)
- [https://www.wannabrowser.net/](https://www.wannabrowser.net/)
    - simulate browsers
- [https://unshorten.it/](https://unshorten.it/)
- [https://urlhaus.abuse.ch/](https://urlhaus.abuse.ch/)
- [https://transparencyreport.google.com/safe-browsing/search](https://transparencyreport.google.com/safe-browsing/search)
- [https://www.joesandbox.com/](https://www.joesandbox.com/)

# Email Attachment Analysis

Put bad files into isolated VM.

File Hashes allow you to check a document against known malicious files

Windows

- get-filehash .\[filename]
    - default is 256

Tools

- [https://github.com/DidierStevens/DidierStevensSuite/blob/master/emldump.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/emldump.py)
- [https://github.com/MalwareCube/Email-IOC-Extractor](https://github.com/MalwareCube/Email-IOC-Extractor)
- [https://www.virustotal.com/gui/home/upload](https://www.virustotal.com/gui/home/upload)
- [https://talosintelligence.com/](https://talosintelligence.com/)

# Dynamic Attachment Analysis and Sandboxing

Tools

- [https://hybrid-analysis.com/](https://hybrid-analysis.com/)
- [https://cloud.google.com/blog/topics/threat-intelligence/cve-2017-0199-hta-handler](https://cloud.google.com/blog/topics/threat-intelligence/cve-2017-0199-hta-handler)
- [https://medium.com/@asmcybersecurity/diving-deeper-into-the-microsoft-office-cve-2017-0199-vulnerability-11bd3e725ab7](https://medium.com/@asmcybersecurity/diving-deeper-into-the-microsoft-office-cve-2017-0199-vulnerability-11bd3e725ab7)
- [](https://joesandbox.com/)[https://joesandbox.com](https://joesandbox.com)
- [](https://app.any.run/)[https://app.any.run](https://app.any.run)

# Static MalDoc Analysis

Tool

• h[ttps://github.com/DidierStevens/DidierStevensSuite/blob/master/oledump.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/oledump.py)

# Static PDF Analysis

Tool:

- [https://github.com/DidierStevens/DidierStevensSuite/blob/master/pdf-parser.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/pdf-parser.py)
- [https://github.com/DidierStevens/DidierStevensSuite/blob/master/pdfid.py](https://github.com/DidierStevens/DidierStevensSuite/blob/master/pdfid.py)

# Automated Email Analysis with PhishTool

Community edition will scan emails for you and shows all of the different headers, lines, content, and other things that are found manually

# Reactive Phishing Defense

Containment

- determine scope
    - log search using threat actor artifacts from known bad email
- Quarantine
- Block sender artifacts
    - Have to be careful about blocking the following
        - email provider
        - domain
        - IP address
        - subject line
    - Setting up an exchange admin center can work.
        - Setting up email rules based off headers such as “sender” to delete the email without notification (which could trigger SOC alerts)
        - Creating in depth rules will create LESS false positives within your organization
- Block web artifacts
    - Can set up rules based off content of web artificats
- Block file artifiacts
    - Block based of file hashes
    - Leverage EDR or other managed services

Eradication

- Remove malicious emails
    - Purge emails based off of artifacts or specific senders to eradicate any left over emails within your environment
    - Use logs to track malicious emails
- Remove malicious files that could have been downloaded
- Abuse form submissions
    - reporting these malicious hashes or URLs will help others
- Reset passwords

Recovery

- restore systems

Communication

- notify/alert affected users
- update vendors/stakeholders

User Education

- end-user training

Tools

- [https://learn.microsoft.com/en-us/exchange/monitoring/trace-an-email-message/message-trace-modern-eac](https://learn.microsoft.com/en-us/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
- [https://learn.microsoft.com/en-us/purview/ediscovery-content-search-overview](https://learn.microsoft.com/en-us/purview/ediscovery-content-search-overview)
- [https://learn.microsoft.com/en-us/purview/ediscovery-content-search](https://learn.microsoft.com/en-us/purview/ediscovery-content-search)

# Proactive Phishing Defense

Email Filtering

- Email security appliances/services
    - mimecast
- Marketing external emails

URL Scanning and Blocking

- Real-time URL inspection
    - chrome extension
- Block recently registered domains

Attachment Filtering

- file extension blocks
- attachment sandboxing

Email Authentication Methods

- SPF
- DKIM
- DMARC

User Training

# Documentation and Reporting

Keep clear and concise notes as you investigate malicious phishing incidents (or any incident)

```jsx
Phishing Analysis Report Template

Headers
======================================
Date:
Subject:

To:
From:

Reply-To:
Return-Path:

Sender IP:
Resolve Host:

Message-ID:

URLs
=======================================

Attachments
======================================
Attachment Name:
MD5:
SHA1:
SHA256:

Description
======================================

Artifact Analysis
======================================
Sender Analysis:

URL Analysis:

Attachment Analysis:

Verdict
======================================

Defense Actions
======================================

```

[[Static Analysis Phishing Tools]]