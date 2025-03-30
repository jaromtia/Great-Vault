#cybersecurity-concepts 

# Job Study

1. Describe a security automation you've implemented. What problem did it solve and what technologies did you use?
2. How would you use Python to parse and analyze logs for suspicious activity?
3. What experience do you have with security orchestration platforms (e.g., Splunk SOAR, Rapid7 InsightConnect, Tines)? Give examples of playbooks you've created.
4. Explain how you would create an automated alert triage system. What APIs would you leverage?
5. How would you approach automating vulnerability scanning in a CI/CD pipeline?
6. Describe how you'd use APIs to integrate different security tools. What challenges might you encounter?
7. What metrics would you use to evaluate the effectiveness of your security automation?
8. How would you implement automated user access reviews using scripting?
9. Explain how you might use machine learning in security automation. What security problems is ML best suited for?
10. How would you design an API to allow other teams to query security data while maintaining proper access controls?
11. Walk through how you would automate the process of investigating and containing a compromised endpoint.
12. How would you implement automated data loss prevention controls programmatically?
13. What security considerations are important when developing automation scripts that have elevated privileges?
14. How would you handle API rate limiting in your security automation tools?
15. Describe how you would create and manage secrets for automation tools securely.

## Incident Detection and Threat Management

1. What data sources do you prioritize when setting up a detection strategy and why?
2. How do you differentiate between false positives and true positives in security alerts?
3. Describe your experience with SIEM platforms. How have you customized detection rules?
4. What methodology do you use to develop detection content for new threats?
5. How do you stay current with emerging threat actors and their TTPs?
6. How would you detect lateral movement in a network? What indicators would you look for?
7. Explain how you would create a detection for data exfiltration attempts.
8. What's your approach to tuning alerts to reduce alert fatigue while maintaining security coverage?
9. How would you implement threat hunting in an organization? What tools and techniques would you use?
10. Describe your experience with EDR/XDR solutions and how you've utilized them for threat detection.
11. How do you approach detecting malicious insiders versus external attackers?
12. What are the advantages and disadvantages of signature-based versus behavior-based detection?
13. How would you detect living-off-the-land techniques where attack
14. Explain your experience with threat intelligence platforms and how you've integrated intelligence into your detection strategy.
15. How would you measure the effectiveness of your detection capabilities?

## Incident Response Investigation

1. Walk me through your process for investigating a suspected security incident from initial alert to resolution.
2. What tools do you use for digital forensics and why?
3. How do you prioritize incidents when multiple alerts are triggered simultaneously?
4. Describe a challenging security incident you've investigated and how you resolved it.
5. How do you maintain chain of custody during a security investigation?
6. What are the key artifacts you look for when investigating a potentially compromised Windows system?
7. What are the key artifacts you look for when investigating a potentially compromised Linux system?
8. How do you approach memory forensics? What tools do you use?
9. Explain your methodology for malware analysis.
10. How do you document and communicate findings during an investigation?
11. What considerations are important when performing incident response in cloud environments versus on-premises?
12. How do you determine patient zero and the initial infection vector during an incident?
13. Describe how you would investigate a potential data breach.
14. What techniques would you use to determine the scope and impact of an incident?
15. How do you balance between quick containment and thorough investigation during an active incident?
16. How would you investigate suspicious activity in containerized or ephemeral environments?
17. What's your approach to post-incident analysis and implementing lessons learned?
18. How do you ensure your incident response process complies with relevant regulations (GDPR, HIPAA, etc.)?
19. Describe how you would determine if an attacker still has access to your environment after an incident.
20. How would you investigate an incident where logs may have been tampered with?

## General Security Knowledge

1. How do you stay current with cybersecurity trends and emerging threats?
2. How do you explain complex security concepts to non-technical stakeholders?
3. How do you measure the ROI of security investments or initiatives?
4. What's your approach to balancing security requirements with business objectives?
5. Describe how you've implemented security improvements following an incident.
6. What experience do you have with compliance frameworks (NIST, ISO, CIS, etc.)?
7. How would you assess the security posture of a new acquisition or third-party vendor?
8. What is your philosophy on security awareness training?
9. How do you approach securing cloud-native vs traditional infrastructure?
10. What are the most challenging aspects of security in your experience and how do you address them?

## Incident Response Investigation

1. What are the key phases of the incident response lifecycle, and what activities occur in each phase?
2. How do you prioritize incidents when multiple security events are occurring simultaneously?
3. Describe your process for collecting and preserving digital evidence during an investigation.
4. What tools do you use for memory forensics, and how do they assist in incident investigations?
5. How would you determine if a system has been compromised if there are no obvious indicators of compromise?
6. Explain the difference between indicators of compromise (IOCs) and indicators of attack (IOAs).
7. How do you establish a timeline of events during an incident investigation?
8. What are some common anti-forensic techniques attackers use, and how do you counter them?
9. Describe a situation where you had to perform malware analysis as part of an incident investigation.
10. How do you approach root cause analysis after containing an incident?
11. What information should be included in an incident report, and why is each element important?
12. How do you determine the initial attack vector during an investigation?
13. What techniques do you use to identify lateral movement in a network during an incident?
14. How would you investigate a suspected data exfiltration event?
15. What considerations are important when communicating about an ongoing incident to stakeholders?

## Incident Response on Linux

1. What Linux commands would you use to identify currently running processes, and how would you spot suspicious ones?
2. How do you investigate unusual network connections on a Linux server?
3. What are the most important log files to examine during a Linux security incident?
4. How would you identify and analyze a rootkit infection on a Linux system?
5. Describe how you would collect volatile data from a compromised Linux server.
6. What tools would you use to analyze a Linux memory dump, and why?
7. How do you investigate privilege escalation attacks on Linux systems?
8. What methods would you use to detect file tampering on a Linux server?
9. How would you identify and analyze persistence mechanisms on a Linux system?
10. Explain how you would use auditd for incident response and forensic purposes.
11. What steps would you take to analyze a suspicious cron job or systemd service?
12. How would you investigate a compromised container in a Linux environment?
13. What filesystem artifacts are most valuable when investigating Linux security incidents?
14. How would you detect and investigate a compromised SSH service?
15. Explain how you would use Linux command-line tools to create a forensic timeline of events.

## Incident Response on AWS

1. What AWS services would you use to detect security incidents, and why?
2. How would you investigate unauthorized access to an AWS account?
3. What steps would you take to contain an incident involving a compromised EC2 instance?
4. How do you collect logs and forensic data from AWS environments during an incident?
5. Explain how you would use AWS CloudTrail to investigate suspicious API calls.
6. What security groups and network ACL changes would you look for during an AWS security incident?
7. How would you investigate data exfiltration through S3 buckets?
8. What would your response be to a cryptomining attack detected in your AWS environment?
9. How do you preserve forensic evidence in AWS when instances can be easily terminated?
10. What steps would you take if you detected unauthorized IAM users or roles in your AWS account?
11. How would you investigate suspicious Lambda function executions?
12. Explain your approach to incident response in a multi-account AWS environment.
13. What AWS-specific indicators of compromise would you look for during an investigation?
14. How would you handle incident response for serverless applications in AWS?
15. What tools and techniques would you use to investigate potential AWS infrastructure-as-code sabotage?
