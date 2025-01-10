#resources/windows 

# Tools
[[Registry Editor]]
[[Windows Forensic Artifact Checklist]]
[[Autoruns]] <-- super important tool both GUI and command line for finding baselines


# Useful Registries to Know

When a specific user is logged in
`HKCU\Software\Microsoft\Windows\CurrentVersion\Run`

When user logs into system
`HKLM\Software\Microsoft\Windows\CurrentVersion\Run`

Installed services on system
`HKLM\SYSTEM\CurrentControlSet\Services`
- attacker can create their own services

# Finding registry keys with Command Prompt
```bash
reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
```
![[reg-query-output.png]]

# Finding registry keys with Powershell

```Powershell
Get-ItemProperty -Path "Registry::-HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
```
![[powershell-registry-query.png]]

# Example of attacker creating persistence with registry keys

*Within msfconsole on attacker machine and after gaining a reverse tcp shell*

```bash
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "NotABackdoor" /t REG_SZ /d "C:\Users\tcm\Downloads\notmalware.exe" /f
```

## Finding the bad registry key with Registry Editor
![[registry-editor-view.png]]


## Finding the bad registry key with command prompt

```bash
reg query "HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
```
![[commandline-query-hkcu.png]]

## Finding the bad registry key with powershell
```powershell
Get-ItemProperty -Path "Registry::-HKCU\Software\Microsoft\Windows\CurrentVersion\Run"
```
![[powershell-reg-query-HKCU.png]]

