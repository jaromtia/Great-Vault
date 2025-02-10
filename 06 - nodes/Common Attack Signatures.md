#resources/SOC 

# User Behavior 

- Multiple Failed Login Attempts
	- Incorrect usernames or passwords 
	- increase in failures from a single user account 
	- Increase in failures form multiple user accounts 
- Login Times 
- Login/Access Locations 
- File Access Patterns 
- User-Agents Strings 
	- Can create user baseline 
	- track unusual or associated known tools

# SQL Injection 

- Inserting or injecting malicious SQL statements 
- Manipulate expected database queries 
- Look for SQL keywords 
	- [[SQL Syntax]]
- Look for injection characters
	- ` "" '' ; # -  ` 
	- Can be URL encoded 
- Malformed entries or errors within database logs
- [Payload all the things examples](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection) 
# Cross-Site Scripting
- Executing malicious code by injecting JavaScript 
	- Hijack user sessions 
	- Steal cookies 
	- Deface websites 
- Look for script tag indicators 
- look for event handlers 
	- onload, onclick, onmouseover
	- References to script tags 
	- References to "javascript" 
- Special characters 
- URL-encoded injection characters 
	- [URL encoded characters](https://www.w3schools.com/tags/ref_urlencode.ASP)

# Command Injection
- Executing arbitrary OS commands 
- Look for special characters that separate commands 
- Look for references to commands or utilities 
- URL-encoded injection commands 

# Path Traversal / Local File Inclusion 
- Accessing files outside of the web root 
	- include or execute unintended files/scripts
- Path Traversal 
	- Access files/directories outside of the web root 
	- enumerate the system, read hardcoded credentials 
- Local File Inclusion (LFI)
	- Include a local file from the system 
	- Enumerate the system, read hardcoded credentials 
	- Execute scripts / remote code execution 
- Look for path traversal sequences 
	- URL Encoded characters 
- Look for sensitive file paths 