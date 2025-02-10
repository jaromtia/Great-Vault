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
