#tool-blue/network

packet capture and analysis tool. Uses network interface to intercept packets for analysis

`tcpdump [option] [expression]`

must specify which interface to collect packets from

`tcpdump -D`

Shows all interfaces available to take from 

Example:
![[Pasted image 20241230164707.png]]

## Capture filters

`tcpdump -i [interface] -n` - prevents capture filters
`tcpdump -i [int] -n host [hostname]` - filters out from specific host
`tcpdump -i [int] -n src [ip]` - track from specific source
`tcpdump -i [int] -n dst [ip]` - track from specific destination 
`tcpdump -i [int] -n net [ip]` - track traffic from specific network
`tcpdump -i [int] -n dst port [port number]` - track from specific traffic from destination port

`sudo tcpdump -i [int] 'src [ip] and dst [ip] and not (port 443 or port 22)'` 
- From interface
- from source address
- to destination address
- except from ports 443 and 22

File saving

`sudo tcpdump [options] [expressions] -w /[filepath].pcap` - writes traffic to existing or new filepath

`sudo tcpdump [options] [expressions] -r /[filepath].pcap [protocol/ip/express]` - reads the file and tcpdump will analyze/parse according to options given

## Analyzing Network Traffic

`tcpdump -r [file].pcap --count` - counts number of packets that match

`tcpdump -r [file].pcap -c 2` - returns first two packets that match

`tcpdump -r [file].pcap -t` - removes all time stamps

`tcpdump -r [file].pcap -tt` - turns all timestamps to UTC

`tcpdump -r [file].pcap -ttt` - turns all timestamps to milliseconds

`tcpdump -r [file].pcap -tttt` - reformats timestamps dates

`tcp -tt -r [file].pcap -n tcp | cut -d " " -f 3 | cut "." 1-4 | sort | uniq -c | sort -nr`
- Reads the file in universal timetamps. 
- cuts out everything that isn't in the third column
- cuts out everything that isn't range 1-4
- sorts everything
- puts all duplicates into a count and shows only unique fields
- sorts again by numerical count in reverse