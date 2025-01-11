#course/D482 
### Components and Network Segmentation:

**1. Company A and Company B Sites (Separate Locations):**

- Each site is segmented into different VLANs for Finance, Medical Providers, and General Access.
- Firewalls at each site provide perimeter defense and Zero Trust enforcement.

**2. Cloud Integration:**

- Use AWS or Azure for scalable cloud services to host shared applications, data storage, and backups.
- A secure VPN tunnel connects on-premises sites to the cloud environment.

**3. Security Devices:**

- Next-Gen Firewalls (e.g., Palo Alto or Sophos XG).
- Intrusion Detection/Prevention System (IDPS).
- Endpoint Detection and Response (EDR) for all connected devices.

**4. Devices and their Logical Assignments:**

| Device                 | OSI Layer      | TCP/IP Layer |
|------------------------|----------------|--------------|
| Firewall               | Network        | Internet     |
| Router                 | Network        | Internet     |
| Servers                | Application    | Application  |
| Cabling                | Physical       | Link         |
| VPN                    | Data Link, Network | Transport, Internet |
| Laptops and Workstations | Application    | Application  |
| WAP                    | Data Link      | Link         |
| Printers               | Application    | Application  |
| Cloud Solution         | Application    | Application  |

**5. Combined Vulnerabilities from Risk Assessments:**

**Company A:**
- Open ports 21-90, 3389 (High risk).
- Weak password policies: 8-character passwords and no regular changes (Moderate risk).
- Unused user accounts not being removed (Moderate risk).
- Excessive local administrative privileges (Moderate risk).
- Use of end-of-life equipment (Low risk).

**Company B:**
- Distributed Ruby (dRuby) Remote Code Execution (Critical risk).
- Java RMI Server insecure configuration (Critical risk).
- PostgreSQL admin exposed to the internet (Critical risk).
- Ghostcat vulnerability in Apache Tomcat AJP (Critical risk).
- Multiple brute force vulnerabilities (VNC, FTP) (High risk).

**6. Remediation Plans:**

- Replace end-of-life systems such as Windows XP and legacy Exchange servers.
- Implement strict password policies (minimum 12 characters, complexity, and 90-day changes).
- Enforce multi-factor authentication (MFA) using DUO for all users.
- Use Sophos XG firewalls to block or monitor traffic on open ports and secure public-facing services.
- Integrate Akamai for cloud application security and Cisco Umbrella for DNS security.

**7. Components Purchased, Retained, or Repurposed:**

- **Purchased:** Sophos XG firewalls, Aruba AP-535 Access Points, AWS cloud services.
- **Retained:** Fortinet firewall from Company A, HPE switches from Company B.
- **Repurposed:** Older laptops for non-critical roles, with plans to upgrade gradually.

**8. Design Principles Implemented:**

- **Zero Trust:** Enforced by using MFA and network segmentation to limit access based on least privilege.
- **Scalability:** Cloud services ensure the network can scale with demand, and newer equipment supports future expansion.

**9. Regulatory Compliance:**

- **PCI DSS:** Required for handling customer payment data. Implemented secure encryption and access controls.
- **HIPAA:** Necessary for medical provider data. Enforced encryption and secure file sharing for sensitive data.

**10. Threats During or After the Merger:**

- **Data Breach:** Exposed by the integration of networks. Mitigated by patching vulnerabilities and monitoring traffic.
- **Insider Threats:** Addressed by restricting administrative privileges and monitoring access logs.

**11. Pricing Research:**

**Networking Equipment:**

1. **Next-Gen Firewall:**
   - Vendor: Sophos XG
   - Cost: $2,500 (per unit)
   - Quantity: 2 (1 per site)
   - Total: $5,000

2. **Router:**
   - Vendor: Cisco ISR 1000 Series
   - Cost: $900 (per unit)
   - Quantity: 2
   - Total: $1,800

3. **Access Points:**
   - Vendor: Aruba AP-535
   - Cost: $650 (per unit)
   - Quantity: 10
   - Total: $6,500

**Cloud Solutions:**

1. **AWS Infrastructure:**
   - Storage (S3): 1 TB = $100/month
   - Compute (EC2): $150/month
   - Total for 1 Year: $3,000

**Security Solutions:**

1. **EDR Solution:**
   - Vendor: CrowdStrike Falcon
   - Cost: $50/user/year
   - Users: 150
   - Total: $7,500

2. **IDPS:**
   - Vendor: Snort (Open Source)
   - Cost: $0 (software) + $500 (hardware setup)

**Miscellaneous:**

1. **VPN Solution:**
   - Vendor: OpenVPN Access Server
   - Cost: $15/month/license (10 users/license)
   - Total for 1 Year: $1,800

**Summary of Costs:**

- Networking Equipment: $13,300
- Cloud Solutions: $3,000
- Security Solutions: $8,000
- Miscellaneous: $1,800
- **Grand Total:** $26,100

This leaves room for unforeseen expenses within the $50,000 budget. Ensure to adapt further based on evolving requirements.

**12. Works Cited:**
- AWS Pricing Calculator. (n.d.). Retrieved from https://calculator.aws/
- Cisco ISR Series Specifications. (n.d.). Retrieved from https://www.cisco.com
- Sophos Products. (n.d.). Retrieved from https://www.sophos.com
- Aruba Access Points. (n.d.). Retrieved from https://www.arubanetworks.com
