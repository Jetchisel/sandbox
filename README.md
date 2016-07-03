# setx - A bash script than can be used for debugging another shell script.

https://github.com/Jetchisel/setx

Copyright 2016 Jetchisel

A  bash  shell  script  that  insert  set [+-]x  and  a  PS4 debug 
code or a trap to make the script  execute line by  line by  using 
the  return  key.  Shell  script is  more  verbose  when  the code
is added in the script in question. It is quite handy when writing
and testing a shell script.

## Usage:
```
setx [OPTION]... [FILE]
```
## Options:
```
  -h  --help     Show this help.
  -a, --about    Show a brief info about ${BASH_SOURCE##*/}.
  -c, --comment  Add a # in front of a line.
  -r, --remove   Remove all the [keyword] code.
  -x, --xtrace   Add `set -x' code to the second line by default.
  -X, --Xtrace   Add `set -x' and a `PS4' code at the second line. by default.
  -p, --print    Print [keyword] code.
  -t, --trap     Make the execution of the script line by line, defaults to the second line.
```

## Examples of using the options.
```
-c FILE              Add a # in front of all lines.
-c 1 FILE            Add a # in front of the first line.
-c 10,20 FILE        Add a # in front of lines 10 to 20.
-x FILE              Insert `set -x' at the second line of FILE.
-x 5 FILE            Insert `set -x' at the fifth line of FILE.
-x 5,10 FILE         Insert `set -x' at the fifth line and `set +x' at the 10th.
-x ,10 FILE          Insert `set +x' at the 10th line of file.
-X FILE              Insert `set -x' and a `PS4' at the second line of FILE.
-X 5 FILE            Insert `set -x' and a `PS4' at the fifth line of FILE.
-X 5,10 FILE         Insert `set -x' and a `PS4' at the fifth line and \`set +x' at the 10th.
-t FILE              Insert a trap at the second line of FILE.
-t 5 FILE            Insert a trap at the fifth line of FILE.
-p [keyword] FILE    Print the [keyword] code if found in FILE.
-r [keyword] FILE    Remove all the [keyword] code in FILE.
```

## Keywords:
```
  debug    All the debug codes `set [+-]x', and the `trap'.
  comment  All the lines that has been commented by adding a # in front.
  tspace   All the lines that has trailing white space.
```

## Caveat:
Inserting any code inside the case statement for example will surely
break its syntax and will add more bugs in the script in question.


## TODO:
Add option to show carriage returns, and option to delete it too.

Replace grep with a while read loop. (maybe :))

## Other resources:

For more info about debugging please have a look at the following site.

https://www.shellcheck.net

http://mywiki.wooledge.org/BashGuide/Practices#Debugging

