#tool-blue/windows 

Tool for going through windows registry keys
- [https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns)
- [https://github.com/p0w3rsh3ll/AutoRuns](https://github.com/p0w3rsh3ll/AutoRuns)
# GUI
Key:
🟩 = signed by trusted published
🟨 = unsigned or unknown publisher
🟥 = potential security risk

![[Pasted image 20250107152142.png]]

You can disable registries with this tool

# Command Line

New-Autoruns Baseline - Baseline
```powershell
Get-PSAutorun -VerifyDigitalSignature |
Where { -not($_.isOSbinary)} |
New-AutoRunsBaseLine -Verbose -FilePath .\Baseline.ps1
```


New-Autoruns Baseline - Current State
```powershell
Get-PSAutorun -VerifyDigitalSignature |
Where { -not($_.isOSbinary)} |
New-AutoRunsBaseLine -Verbose -FilePath .\CurrentState.ps1
```

# How to use

Run Autorun twice. One for the baseline of a machine that you believe to be fairly safe. The other of the current state of the machine
![[Pasted image 20250107155415.png]]
After that you can run
```powershell
Compare-AutoRunsBaseLine -ReferenceBaseLineFile .\Baseline.ps1 -DifferentBaseLineFile .\CurrentState.ps1
```

This will show the differences between baselines for you.
![[Pasted image 20250107155256.png]]

