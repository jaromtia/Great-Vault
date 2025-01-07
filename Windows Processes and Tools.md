#resources/windows 

![[Pasted image 20250107081709.png]]

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
![[Pasted image 20250107110317.png]]

If anything is different from the system process and is saying it is the system process then this is cause for alerting

# smss.exe (Session Manager Subsystem)

![[Pasted image 20250107110531.png]]

- First Master instance of process created child instances
- child instances initializes components
- once initialization is complete then child instance are terminated
	- normally will initialize [[#csrss.exe]]

## Always true
![[Pasted image 20250107110710.png]]
- Should only be one smss.exe as children instances should always self-termiante

# csrss.exe (Client/Server Runtime Subsystem)
## Always true

![[Pasted image 20250107110932.png]]

- csrss.exe will often look like an orphaned process since [[#smss.exe (Session Manager Subsystem)]] child process self-terminates

# wininit.exe (Windows Initialization)
![[Pasted image 20250107113554.png]]

# services.exe (Service Control Manager)
Child process of [[#wininit.exe (Windows Initialization)]]
![[Pasted image 20250107113647.png]]

# svchost.exe (Service Host)
Child process of [[#services.exe (Service Control Manager)]]
normal to have a LOT of instances.
**Often a target for attackers to hide malware or bad processes**
![[Pasted image 20250107113821.png]]

# lsass.exe (Local Security Authority Subsystem Service)
common mimikatz target by attackers
Child process of [[#wininit.exe (Windows Initialization)]]
![[Pasted image 20250107113947.png]]

# winlogon.exe (Windows Logon)
![[Pasted image 20250107114057.png]]

# explorer.exe (Windows Explorer)
![[Pasted image 20250107114202.png]]

# Process Investigation
![[Pasted image 20250107114353.png]]

[[SANS_DFPS]]


