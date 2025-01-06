#tool-blue/network 

Sniffer Mode

Logger Mode

IDS/IPS Mode 

## Snort Rule Syntax

Snort Rule:
![[Pasted image 20241231101545.png]]

## Snort Rule examples
Potential .exe download over HTTP
`alert tcp any 80 -> any any (msg:"[message]"; http_header; sid:[sid-#]; rev:1;`

Detecting based off of magic byte
`alert ttcp any 80 -> any any (msg:"[message]"; file_date; content:"|4D 5A|"; depth: 2; sid[#]; rev:1;`

Detect SSLoad activity via User-Agent
`alert tcp any any -> any any (msg:"[message]"; content:"User-Agent":SSLoad/1.1"; http_header; nocase; sid:[#]; rev:1;`

Detect potential brute force attack
`alert tcp any any -> any 22 (msg:"[message]"; flow:to_server,established; threshold:type threshold, track by_src, count 5 , seconds 30; sid:[#]; rev:1; `


## Runnning rules against pcap

Detect which rules match within pcap files
`sudo snort -c /etc/snort/snort.conf -q -r [pcapfile] -A console`

Provide hex/ascii of packets
`sudo snort -r /var/log/snort/[snort.log] -q -d` 

