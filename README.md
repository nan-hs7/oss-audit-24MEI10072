Name: Nandita Nair
Reg No: 24MEI10072
Chosen software: Python

**Description**
the project demonstrtes Linux shell concepts using five shell scripts. Each script performs a particular task that is, display information of system, inspect package, disk auditing, log file analysis and making custom manifesto.

**Script 1: System Identity Report**
We are naming the file script1.sh for convenience. 
The script is used for displaying Linus system information using bash scripting concepts such as variables, echo and command substitution to execute command and display output.
1. Command Substitution $( ): used for running command and save output into a variable e.g., KERNEL=$(uname -r).
2. Variables: used to store data like name or system paths for easy use in echo statements.
3. Environment Variables: $HOME is built-in variable which  automatically points to the current user's home directory.
4. grep and cut: used to extract the 'pretty name' of the Linux distribution from the system files.

**Script 2: FOSS package inspector**
file is named script2.sh for convenience. it checks if a specified package is installed on Linuz system, displays its version and summary. It proovides a small description of its purpose.

1. if-then-else: used to verify if the package exists on the system.
2. >/dev/null 2>&1: silences the output of the check command so user only sees custom echo messages.
3. grep -E: uses regular expressions to find multiple fields, Version, License, etc,  at once.
4. case statement: provides clean way to map specific package names to their philosophy or description.

**Script 3: Disk and permission auditor**
file names as script3.sh for easy access. its a bash script and uses dir array. it is designed to audit system dictionaries. it reports owner, permissions etc.

1. for DIR in "${DIRS[@]}": proper syntax to loop through every item in a Bash array.
2. ls -ld: -d flag is important. it tells ls to list the directory itself, than its contents.
3. awk '{print $1, $3, $4}': extracts specific columns from ls output:
4. $1: Permissions (e.g., drwxr-xr-x)
5. $3: Owner (e.g., root)
6. $4: Group (e.g., root)
7. du -sh: calculates disk usage in a human-readable format.
8. 2>/dev/null: hides "Permission Denied" errors that might occur if script is run by a non-root user on restricted system folders.

**Script 4: Log File analyzer**

1. LoGFILE=$1: captures the first word you type after the script name (the file path).
2. ${2:-"error"}: is a bash parameter expansion. uses the second argument as the keyword, but if not provide one, it defaults to "error".
3. while IFS= read -r LINE; do ... done < "$LOGFILE":
4. ifs= prevents leading/trailing whitespace from being trimmed.
5. -r prevents backslashes from being interpreted as escape characters.
6. < "$LOGFILE" redirects the file content into the loop.
7. $((COUNT + 1)): the standard way to perform arithmetic in Bash.
8. grep -iq:
-i: case-insensitive (matches "Error", "ERROR", or "error").
-q: quiet mode. It doesn't print the line to the screen; it just tells the if statement whether the word was found or not.

**Script 5: Open source manifesto generator**

1. read -p: captures user input and assigns it to variables ($TOOL, $FREEDOM, $BUILD).
2. $(date ...): uses the date command to format the current day, month, and year.
Redirectors:
>: creates (or overwrites) the file with first line of text.
>>: appends the subsequent lines to the end of the file so you don't lose the previous content.
$(whoami): dynamically inserts your system username into the filename.
Aliases Comment: included at the top to demonstrate the concept as requested by the prompt.

**How to run script:**
1. Open terminal
2. Make it executable using chmod +x *.sh
3. run the 5 scripts

**Conclusion**
The project demonstrates practical use of shell scripting using Linux and helps understand the importance of tools in system managemnet and automation.
