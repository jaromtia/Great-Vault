#resources/linux

# Tools

[[netstat]]

# Linux Commands 
`lsof`


```
# Important directories and files

## Proc 
`/proc` - Memory of system processes or system resource

`/proc/[processid]/environ` - environmental variables of process 

`/proc/[processid]/exe` - symbolic link of executable file
# Methodology

```bash
sudo lsof -i -n -p
```
-i 
-n 
-p 

Find established network connections 

Start wide then go narrow with abnormalities 
