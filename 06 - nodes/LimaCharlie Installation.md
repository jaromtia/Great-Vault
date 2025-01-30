#resources/EDR 

# Sign-up and initialization 
Sign into  [LimaCharlie Signup](https://app.limacharlie.io/signup) 

![[Pasted image 20250130045040.png]]

Verify email address

![[Pasted image 20250130045107.png]]

Fill out questionnaire 

![[Pasted image 20250130045142.png]]

An overview screen should appear 

![[Pasted image 20250130045210.png]]

Select `Create Organization` to set up a new profile/set-up. First 2 organizations are free. 

![[Pasted image 20250130045321.png]]

Once organization is set up it should initialize and show the following dashboard

![[Pasted image 20250130045428.png]]

# Sensor interface 

remove the filter to see all sensors available by default:
![[Pasted image 20250130045553.png]]

You can add or remove as you see fit. Clicking into a sensor will show details

![[Pasted image 20250130045626.png]]

**Overview** shows everything about the sensor
**Analytics** will show what is collected form the sensor 
![[Pasted image 20250130045935.png]]
**Detections** will alert according to response rules. Clicking on detections will show in-depth details of logs in json format.
- Use this to create detection rules and actions for when a detection happens. 

![[Pasted image 20250130045950.png]]
**Live Feed** will show incoming detection live 
**Timeline** shows the telemetry of the sensor. Basically shows a snapshot of everything in a certain time range chronologically
- gives context to detections and events 
- can filter by fields 
![[Pasted image 20250130050043.png]]

# Automation 

![[Pasted image 20250130050204.png]]

D&R are the rules set to describe what to detect and within will show what to respond. 