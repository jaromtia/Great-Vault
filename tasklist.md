#tool-blue/windows 

**Run as administrator to see more processes and details**
![[tasklist-command-line.png]]

Filter examples:
`tasklist /FI "PID eq 2088"`
![[task-list-filter-example1.png]]

`tasklist /FI "IMAGENAME eq notmalware.exe`
![[tasklist-filter-imagename.png]]

**Show Dynamically linked libraries**
`tasklist /FI "PID eq 2088" /M`
![[tasklist-filter-PID.png]]
- DLL are not necessarily malicious by default but can be helpful for creating detection rules.

