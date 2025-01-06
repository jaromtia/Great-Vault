#projects/tcm

# Network Security Theory
## Network Layer Protocols
- Internet Protocol (IP)
	- IP addressing
	- works at layer 4
- Transmission Control Protocol ([[TCP]])
- User Datagram Protocol ([[UDP]])

IPv4 Header
![[Pasted image 20241230085242.png]]

TCP Header
![[Pasted image 20241230085631.png]]

UDP Header
![[Pasted image 20241230085706.png]]

[[Three-Way Handshake]]
![[Pasted image 20241230090532.png]]

Common Ports
- 21 File Transfer Protocol
- 22 Secure Shell (SSH)
- 23 Telnet (ssh but not secure)
- 25 Simple Mail Transfer Protocol (SMTP)
- 53 Domain Name System (DNS)
- 80 HyperText Transfer Protocol (HTTP)
- 110 Post Office Protocol 3 (POP3)
- 135 Microsoft Remote Procedure Call (RPC)
- 139 NetBIOS
- 143 (IMAP)
- 389 (LDAP)
- 443 (HTTPS)
- 445 (SMB)
- 3389 (RDP)
- 8080 (HTTP)

# Packet Capture (PCAP)

### Packets
Header
Payload - Actual data
Trailer

- Intercepting Packets
	- port mirroring (SPAN Ports)
	- Inline network devices
	- Network taps
- **PCAP Files**
	- Binary file format
	- Header and raw payload
	- tcpdump, wireshark, Tshark
- Advantages
	- Most detailed record
	- includes packet payload
- Disadvantages
	- Resource intensive
	- requires significant storage space
	- hard to scale

**Flow Records**
- Aggregated metadata
- 5-tuple
	- Source IP 
	- source ports
	- destination IP
	- destination ports
	- transport protocol
- advantages
	- efficient bandwidth and storage requirements
	- high level pattern and anomaly detection
	- easier to scale
- disadvantages
	- lacks payload detailed
	- doesn't give you the whole picture

[[tcpdump]] and how to capture network traffic

[[Wireshark]] methodology 

# Intrusion Detection and Prevention Systems (IDS/IPS)

Intrusion Detection Systems ([[IDS]])
- Passive monitoring and analysis
- Alert generation
- Logging
Intrusion Prevention Systems ([[IPS]])
- Traffic inspection
- Blocking and dropping packets
- Terminating connections
- Alert generation
- Logging
- Inline deployment
Network-Based IDS/IPS (NIDS/NIPS)
- Operate at the network level
- analyze traffic flowing through network appliances
- Alert, log, and/or block malicious traffic
Host-Based IDS/IPS (HIDS/HIPS)
- Operate at the endpoint level
- Analyze activities on the host (file system, logins, apps)
- Alert, log, and/or block malicious activity

## Detection Methods
Signature-based detection
- comparing traffic or activities against known attack patterns
- effective at identifying known threats
- cannot detect what it doesn't know exits
Behavior-based detection
- identify anomalies that deviate from a pre-established baseline
- most effective at detecting unknown threats
- can create a lot of false positives if base-line is not well defined
Rule-based detection
- Enforcing policies to define acceptable actions or violations
- highly customizable to an organizations requirements
- requires frequent maintenance and rule updates

[[Snort]]
