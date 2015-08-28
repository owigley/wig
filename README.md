# wig
Bash script utility for manipulating individual lines of stdout / stdin

 Name

     wig

 Synopsis

     wig [-pl]

 Description

     Caches any input from stdin. Each bash terminal session has a separate cache.
     Caches persists until overwritten by wig, or when system reboots.

     With no arguments passed it expects input via stdin.

     -p displays current cache content, each line item prefixed with index

     -l <index> prints just line item without index prefixed

     -h print help

 Examples

     echo ls | wig            //store input from ls
     wig -p                   //print all cached items with indices prefixed
     wig -l 3                 //print cached line item 3
     cp `wig -l 3` ~          //copy line item 3 to home dir
     git commit `wig -l 3`    //git commits the file item
     cat main.c | wig         //store content of file
     ps | wig                 //store ps output

Using With Git

     $git status | wig         //store current git status
     $wig -p                   //view modified files
     $git commit `wig -l 10`   //commits line item 10
