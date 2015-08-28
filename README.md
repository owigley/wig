# wig
Bash script utility for manipulating individual lines of stdout

#
# Name
#     wig
#
# Synopsis
#     wig [-pl]
#
# Description
#
#     Caches any input from stdin. Each bash terminal session has a separate cache.
#     Caches persists until overwritten by wig, or when system reboots.
#
#     With no arguments passed it expects input via stdin.
#
#     -p displays current cache content, each line item prefixed with index
#
#     -l <index> prints just line item without index prefixed
#
#     -h print help
#
# Examples
#     echo ls | wig            //store input from ls
#     cat main.c | wig         //store content of file
#
#     wig -p                         //print all chached items with indices prefixed
#     wig -l 3                       //print cached line item 3
#     cp `wig -l 3` ~                //copy line item 3 to home dir
#     git commit `wig -l 3`          //git commits the file item
