# setx - Just another bash script than can be used for debugging another shell script.

https://github.com/Jetchisel/setx

Copyright 2016 Jetchisel

A bash shell script that inserts set -x and a PS4 debug code
or a trap to make the script execute line by line by using
the return key. Shell script is  more verbose when the code
is added in the script in question. This script  requires the  
follwing  GNU utilities, ed(1) for editing the shell script and
file(1)  for  testing  file type of the script in question and.
grep for matching patterns against the debug codes.


## Usage:
```
setx [OPTION] [FILE
```

## Options:
```
-s, --step     Make the execution of script line by line using a trap.
-u, --undo     Undo or remove all the debug code in the script.
-x, --xtrace   Add set -x and PS4 debug code below the shebang.
-a, --about    A brief info about setx.
-h, --help     Show this help.
```

## TODO:
Add option to insert debug codes in a specific line.



For more info about debugging please have a look at the following site.

https://www.shellcheck.net

http://mywiki.wooledge.org/BashGuide/Practices#Debugging
