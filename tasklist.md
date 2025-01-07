#tool-blue/windows 

**Run as administrator to see more processes and details**
![[Pasted image 20250107081820.png]]

Filter examples:
`tasklist /FI "PID eq 2088"`
![[Pasted image 20250107082107.png]]

`tasklist /FI "IMAGENAME eq notmalware.exe`
![[Pasted image 20250107082118.png]]

**Show Dynamically linked libraries**
`tasklist /FI "PID eq 2088" /M`
![[Pasted image 20250107082200.png]]
- DLL are not necessarily malicious by default but can be helpful for creating detection rules.

