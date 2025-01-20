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

Filters