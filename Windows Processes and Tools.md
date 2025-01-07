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