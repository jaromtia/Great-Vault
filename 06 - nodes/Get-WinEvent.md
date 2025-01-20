#tool-blue/windows 
https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-7.4 
Gets events from event logs and event tracing log files on local and remote computers

```powershell
Get-WinEvent
   [[-LogName] <String[]>]
   [-MaxEvents <Int64>]
   [-ComputerName <String>]
   [-Credential <PSCredential>]
   [-FilterXPath <String>]
   [-Force]
   [-Oldest]
   [<CommonParameters>]
```

Creating Get-WinEvent queries with FilterHashtable

https://learn.microsoft.com/en-us/powershell/scripting/samples/creating-get-winevent-queries-with-filterhashtable?view=powershell-7.4

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

```powershell 
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```
