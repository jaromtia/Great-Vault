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

## **Overview** 
shows everything about the sensor
**Analytics** will show what is collected form the sensor 
![[Pasted image 20250130045935.png]]
## **Detections** 
will alert according to response rules. Clicking on detections will show in-depth details of logs in json format.
- Use this to create detection rules and actions for when a detection happens. 

![[Pasted image 20250130045950.png]]
## **Live Feed** 
will show incoming detection live 
## **Timeline** 
shows the telemetry of the sensor. Basically shows a snapshot of everything in a certain time range chronologically
- gives context to detections and events 
- can filter by fields 
![[Pasted image 20250130050043.png]]

# Automation 

![[Pasted image 20250130050204.png]]

## **D&R**  
rules set to describe what to detect and within will show what to respond. 

## **Outputs**  
where automated flows go into other tools. Integration tooling. It has a streamline way of setting these up through web hooks and api
![[Pasted image 20250130050319.png]]
# Deploying Agent

## Installation Keys 
![[Pasted image 20250130050552.png]]

Sensor Key - general key

Chrome Key - browser

Adapter Key - integrations 

![[Pasted image 20250130050723.png]]

After key is created we can download the agent installer for the sensor to connect to. 

Scroll down for downloads 
![[Pasted image 20250130050756.png]]

Copy sensor key and run the executable that was downloaded in powershell (admin)

Windows: 
![[Pasted image 20250130050906.png]]

Host should be very quickly added to the list:
![[Pasted image 20250130050949.png]]

Going into that endpoint we will see details specific to that machine
![[Pasted image 20250130051048.png]]

LimaCharlie allows you to run console commands directly on the machine. There is a pre-set amount of commands that can be range
![[Pasted image 20250130051145.png]]

Can access the filesystem of the machine
![[Pasted image 20250130051222.png]]
Show what is connected to the host machines network or what is running and connecting out 
![[Pasted image 20250130051318.png]]

See what processes are being ran 
![[Pasted image 20250130051352.png]]

See what services are being ran 
![[Pasted image 20250130051411.png]]

Has containment capabilities
![[Pasted image 20250130051441.png]]

