## Linux Commands 

`file [insert file name]` - file type 

`ls -lh` - Human readable directory listing 

`wc` - Word count of file 

`head` - first 10 lines 

`tail` - last 10 lines 

`less` - see entire file in chunks 

`cut access.log -d " " -f 1` - cut out specific parts of the file. 
-d delimitator that defines what to categorize each section as. 

## Combo Commands Examples 

Find all unique IP addresses connections
`cut access.log -d " " -f 1 | sort | uniq -c | grep -v " 1 " | sort -nr`

Finds all unique user-agent strings 
`cut -d "\"" -f 6 access.log | sort | uniq -c | sort -nr`

Find specific malicious tools within logs
`grep "Mozilla/5.0 (Hydra)" access.log | awk '{print $1}' | sort | uniq -c`

Find bad responses 
`grep "Mozilla/5.0 (Hydra)" access.log | awk '' | sort | uniq -c`
## Online tools to analyze artifacts 
- [https://whois.domaintools.com/](https://whois.domaintools.com/)
- [https://talosintelligence.com/](https://talosintelligence.com/)