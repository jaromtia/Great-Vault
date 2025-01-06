#tool-blue/network 
## Methodology

1. Set up timestamp to something more familiar than default
2. Statistics
	1. capture file properties
		1. Great high level view
		2. starts a timeline and view of relevant data
	2. conversations
		1. can sort by most used packets
	3. Hierarchy
		1. low hanging fruit can be found
		2. can create starting points
3. Set columns to give more information in the Wireshark view
4. Look within suspicious or interesting packets
	1. follow streams of packets and see the full conversations found
5. analyze analyze analyze
6. Gather IOCs
	1. download files to get more information.
		1. hashes
		2. file type
		3. virus total
		4. malware analysis
	2. - [malware traffic analysis](https://www.malware-traffic-analysis.net/)
7. Once IOCs are found look for attack techniques or malware uses in threat intelligence databases
8. pivot based off of research
	1. set new display filters
	2. repeat steps 2, 4-8 in any order that makes sense
9. 