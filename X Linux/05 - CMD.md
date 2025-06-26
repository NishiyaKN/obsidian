`export [var]` - transforms local variable to environment variable
`unset [var]` - removes the variable, local or env
`type [command]` - tells if [command] is an alias, if not, then the localtion of the executable
`alias` - shows all aliases
### Quotes
##### "Double Quotes" 
- Ignores glob characters such as * and ?, but allows for $
	- `echo "The glob characters are *, ? and [ ]"` - works
	- `echo "$PATH"` - works
###### 'Single Quotes'
- Ignores any special characters
	- `echo '$PATH'` - outputs exactly `$PATH`