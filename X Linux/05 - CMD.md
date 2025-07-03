`export [var]` - transforms local variable to environment variable
`unset [var]` - removes the variable, local or env
`type [command]` - tells if [command] is an alias, if not, then the localtion of the executable
`alias` - prints all aliases

`man -f passwd` - prints all man pages that matches with passwd
	`passwd (5)           - the password file`
	`passwd (1)           - change user password` 
	`passwd (1ssl)        - compute password hashes`
`whatis` - same as `man -f`
`man 5 passwd` - prints man page for passwd on section 5
`man -k copy` - prints all man pages titles and sections that matches `copy` as part of the title or description
`apropos` - same as `man -k`

`whereis passwd` - prints location of the commands, source files and man pages to `passwdd`
	`passwd: /usr/bin/passwd /etc/passwd /usr/share/man/man1/passwd.1.gz /usr/share/man/man1/passwd.1ossl.gz /usr/share/man/man5/passwd.5.gz`
	
`locate passwd`- prints all files that contain `passwd` in name or path
`updatedb` - updates the `locate` database manually
### Quotes
##### "Double Quotes" 
- Ignores glob characters such as * and ?, but allows for $ and \`
	- `echo "The glob characters are *, ? and [ ]"` - works
	- `echo "$PATH"` - works
###### 'Single Quotes'
- Ignores any special characters
	- `echo '$PATH'` - outputs exactly `$PATH`
###### \`Back Quotes\`
- Substitutes commands
	- `echo today is`\``date`\`
	- Basically like `echo today is $(date)`
### Navigation / files
`cd ~bob` goes to the home dir of user bob
`ls -R` lists all files recursively
`ls -S` sorts by biggest size 
`ls -t` sorts by last modified
`ls --full-time` shows in `-l` format with full timestamp
### Regex
`echo *` shows all files in the directory
`ls [aD]*` shows all files that start with a or D
`ls [!a-c]*` shows all files that don't start with a,b or c
`ls D*` shows all files inside all folders that starts with D
`ls -d D*` shows all files and folders that starts with D (does not do it recursively)
### cp/mv
`cp/mv -i source dest` asks before overwriting file `dest`
`cp/mv -n source dest` does not overwrite file `dest`
`cp/mv -p` preserve file attributes, such as timestamp
note: `rm -i file` asks before deleting
