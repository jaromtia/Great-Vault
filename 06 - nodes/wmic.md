#tool-blue/windows 

helps determine system or process information
`wmic process where processid=[PID] get name, parentprocessid, processid`
![[wmic-commandline-example.png]]

General search for any parentprocess piped into `find` query
`wmic process get name, parentprocessid, processid | find "192`

Gives path to executable
`wmic process where processid=[PID] get commandline`
- can output file path
- can output command itself
- can output powershell
- etc...