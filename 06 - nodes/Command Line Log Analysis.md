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
`grep "Mozilla/5.0 (Hydra)" access.log | awk '$9 > 200' | sort | uniq -c`

Search by a specific timestamp for a specific endpoint
grep "17/Jul/2024:18:49:02 - 0400" access.log | grep -v "login.php"
## Online tools to analyze artifacts 
- [https://whois.domaintools.com/](https://whois.domaintools.com/)
- [https://talosintelligence.com/](https://talosintelligence.com/)