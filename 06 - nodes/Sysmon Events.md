#resources/windows 

Event ID 1 - Process Creation
- Excludes Microsoft Windows bainaries
Event ID 3 - Network Connection 
Event ID 5 - Process terminated
Event ID 7 - Image Loaded
Event ID 8 - CreateRemoteThread
- Potential malware injection in good processses 
Event ID 10 - ProcessAccess 
Event ID 11 - FileCreate
Event ID 12, 13, 14 - Registry Events 
Event ID 15 - FileCreateStreamHash
Event ID 22 - DNSEvent (DNS Query)
- Can be used to find top domains used in network 
Event ID 29 - FileExecutableDetected

# Powershell queries

Get all sysmon events 
```powershell
Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational"
```

Filters to collect logs with specific event IDs 
```powershell
Get-WinEvent -FilterHashtable @{logname="Microsoft-Windows-Sysmon/Operational"; id=1}
```

Better formatting
```powershell
Get-WinEvent -FilterHashtable @{logname="Microsoft-Windows-Sysmon/Operational"; id=3} -MaxEvents 1 | Format-List *
```

Filtering for network connections with specific ports 
```powershell
Get-WinEvent -LogName 'Microsoft-Windows-Sysmon/Operational' -FilterXPath "*[System/EventID=3 and EventData[Data[@Name='DestinationPort']='4444']]" | Format-List *
```

Searching with a specific process ID 
```powershell
Get-WinEvent -LogName 'Microsoft-Windows-Sysmon/Operational' -FilterXPath "*[System/EventID=1]"
```

Searching with a specific process ID and better formatting 
```powershell
Get-WinEvent -LogName 'Microsoft-Windows-Sysmon/Operational' -FilterXPath "*[System/EventID=1 and EventData[Data[@Name='ProcessId']='<ENTER YOUR PID HERE>']]" | Format-List *
```