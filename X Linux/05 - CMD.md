`export [var]` - transforms local variable to environment variable
`unset [var]` - removes the variable, local or env
`type [command]` - tells if [command] is an alias, if not, then the localtion of the executable
`alias` - shows all aliases

`man -f passwd` - show all man pages that matches with passwd	
```
	passwd (5)           - the password file                              
	passwd (1)           - change user password                           
	passwd (1ssl)        - compute password hashes
```
`man 5 passwd` - shows man page for passwd on section 5
`man -k copy` - shows all man pages titles and sections that matches `copy` as part of the title or description
`apropos` - same as `man -k`

`whereis passwd` - shows location of the commands, source files and man
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
	