# macOS Shell Snippets

## Summary:

Helpful shell snippets for macOS



---
## Commands:

snippet `z.logged_in_user` : creates a varible to get the current logged in users name

```shell
logged_in_user=$(scutil <<< "show State:/Users/ConsoleUser" | awk '/Name :/ && ! /loginwindow/ { print $3 }')
```


---
snippet `z.if`: Create an empty if statement

```shell
if [[ xx ]]; then
	command
fi
```


---
snippet `z.else`: Creates an empty if/else statement

```bash
if [[ command ]];then
   command
else
   commmand
fi
```


---
snippet `z.80`: Creates a 80 character comment line

```bash
#-------------------------------------------------------------------------------
```


---
snippet: `z.100`: Creates a 100 character comment line

```bash
#---------------------------------------------------------------------------------------------------
```

