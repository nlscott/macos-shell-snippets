# macOS Shell Snippets

## Summary:

VS Code extension for some helpful shell snippets for macOS



![macos-shell-snippets](https://github.com/nlscott/macos-shell-snippets/blob/main/images/icon.png/macos-shell-snippets.gif)



---
## Commands:

`z.template`: creates a template for zsh scripts

```shell
#!/bin/zsh

####################################################################################################
# Name      	: xxx.zsh
# Date         : 2025.xx.xx
# Version      : 0.1.0
# Author       : xxx
# Email        : xxx
# Description	: xxx
####################################################################################################

## VARIABLES ---------------------------------------------------------------------------------------
time_stamp_utc=$(date -u +"%Y-%m-%dT%H:%M:%SZ")
logged_in_user=$(scutil <<< "show State:/Users/ConsoleUser" | awk '/Name :/ && ! /loginwindow/ { print $3 }')
host_name=$(uname -n)

## FUNCTIONS ---------------------------------------------------------------------------------------
function log_message () {
   echo '{"timestamp": "'${time_stamp_utc}'", "hostname": "'${host_name}'", "user": "'${logged_in_user}'", "severity": "'$1'", "message": "'$2'"}' | jq -c
}

## COMMANDS ----------------------------------------------------------------------------------------
log_message Info "this is a test message to help debug"
```



---
 `z.header`: creates a header for a shell script

```shell
###########################################################################################
# Name      	: xxx.zsh
# Date        : 2025.xx.xx
# Version     : 0.1.0
# Author      : xxx
# Email       : xxx
# Description	: xxx
###########################################################################################
```



---
`z.variable_header`: creates a 100 character long header for variables

```shell
## VARIABLES ---------------------------------------------------------------------------------------
```



---
 `z.timestamp_utc`: creates a var for the current time in utc

```bash
time_stamp_utc=$(date -u +"%Y-%m-%dT%H:%M:%SZ")
```



 `z.logged_in_user` : creates a varible to get the current logged in users name

```shell
logged_in_user=$(scutil <<< "show State:/Users/ConsoleUser" | awk '/Name :/ && ! /loginwindow/ { print $3 }')
```



 `z.host_name`: creates a var for hostname

```shell
host_name=$(uname -n)
```



 `z.serial_number`: creates a var for serial number

```bash
serial_number=$(system_profiler SPHardwareDataType | grep Serial | cut -d ":" -f2 | xargs)
```



 `z.public_ip`: creates a var for public ip

```shell
public_ip=$(dig -4 TXT +short o-o.myaddr.l.google.com @ns1.google.com | tr -d '"')
```



---
`z.functions_header`: creates a 100 character long header for functions

```shell
## FUNCTIONS ---------------------------------------------------------------------------------------
```



---
 `z.log`: creates a logging function

```shell
function log_message () {
   echo '{"timestamp": "'${time_stamp_utc}'", "hostname": "'${host_name}'", "user": "'${logged_in_user}'", "severity": "'$1'", "message": "'$2'"}' | jq -c
}
```



---
`z.command_header`: creates a 100 character long header for commands

```shell
## COMMANDS ----------------------------------------------------------------------------------------
```



---
`z.test_log`: creates a test log, requires log_message function

```shell
log_message Info "this is a test message to help debug"
```



---
 `z.if`: Create an empty if statement

```shell
if [[ xx ]]; then
	command
fi
```



---
 `z.else`: Creates an empty if/else statement

```bash
if [[ command ]];then
   command
else
   commmand
fi
```



---
`z.80`: Creates a 80 character comment line

```bash
#-------------------------------------------------------------------------------
```



---
 `z.100`: Creates a 100 character comment line

```bash
#---------------------------------------------------------------------------------------------------
```

---
 `z.function`: Creates an empty function

```bash
    function function_name {
        # commands
    }
```





















