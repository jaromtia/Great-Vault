#resources/windows 

![[windows-processes-heirarchy.png]]

# Tools:
## Finding general processes
[[tasklist]]

## Find further details on specific processes
[[wmic]]

## Tasklist but on steroids
[[process explorer]]

# System Process 
- Kernel-mode system thread 
- Manages CPU, memory, disk
- device drivers, hardware, process scheduling, etc.
## Always true
![[system-process.png]]

If anything is different from the system process and is saying it is the system process then this is cause for alerting

# smss.exe (Session Manager Subsystem)

![[system-process-heirarchy.png]]

- First Master instance of process created child instances
- child instances initializes components
- once initialization is complete then child instance are terminated
	- normally will initialize [[#csrss.exe]]

## Always true
![[windows-session-manager-true.png]]
- Should only be one smss.exe as children instances should always self-termiante

# csrss.exe (Client/Server Runtime Subsystem)
## Always true

![[csrss-exe-true.png]]

- csrss.exe will often look like an orphaned process since [[#smss.exe (Session Manager Subsystem)]] child process self-terminates

# wininit.exe (Windows Initialization)
![[winiti-exe-true.png]]

# services.exe (Service Control Manager)
Child process of [[#wininit.exe (Windows Initialization)]]
![[SCM-true.png]]

# svchost.exe (Service Host)
Child process of [[#services.exe (Service Control Manager)]]
normal to have a LOT of instances.
**Often a target for attackers to hide malware or bad processes**
![[svchost-exe-true.png]]

# lsass.exe (Local Security Authority Subsystem Service)
common mimikatz target by attackers
Child process of [[#wininit.exe (Windows Initialization)]]
![[lsass-exe-true.png]]

# winlogon.exe (Windows Logon)
![[winlogon-exe-true.png]]

# explorer.exe (Windows Explorer)
![[explorer-exe-true.png]]

# Process Investigation
![[registry-analysis-method.png]]

[[SANS_DFPS]]


