#tool-blue/windows 

# Command-line
## Command Prompt
Show's running services
```
sc query
```

Query service details
```
sc qc [service]
```

## Powershell
Show all running services
```powershell
Get-Service | Where-Object { $_.Status -eq 'Running' }
```

Search details on specific service
```powershell
Get-Service -Name "[service-name]"
```

Accepts wildcards
```powershell
Get-Service -Name "B*"
```

Get in-depth details on specific service
```powershell
Get-WmiObject -Class Win32_Service -Filter "Name = '[service-name]'" | Select-Object
```

Use `CimInstance` whenever possible
```powershell
Get-CimInstance -Class Win32_Service -Filter "Name = '[service-name]'" | Select-Object
```
# GUI

![[Pasted image 20250108140649.png]]