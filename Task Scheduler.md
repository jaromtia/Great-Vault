#tool-blue/windows 

Allows you to see any scheduled tasks on windows. Works like a GUI for windows CRON jobs
![[task-scheduler.png]]

# Command-line

Display list of all tasks on the machine
```
schtasks /query /fo LIST
```

![[Pasted image 20250108141933.png]]

Query specific tasks
```
schtasks /query /tn "SystemCleanup" /v /fo LIST
```
![[schtasks-command-line.png]]
