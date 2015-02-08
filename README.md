# HistLog - A bash script that archives and save ~/.bash_history

https://github.com/Jetchisel/HistLog

Copyright 2014-2015, Jetchisel
Licensed under the GNU Affero General Public License, v3

Goal of HistLog:

  - Avoid loosing bash_history
    save the history to an archive.

## Note: Read everything before using this script.

* Make sure to adjust your history limit in ~/.bashrc and (set or) understand the following history options:
  - -[arc]
  - HISTFILESIZE
  - HISTSIZE
  - PROMPT_COMMAND
  - shopt -s histappend

see **help history**

##
* Change the value of the variables of HistLog according to your own hearts content.
* By default this script will run every Minute being called via cron. (vixie-cron)
* It is able to check and create a crontab entry (*ONLY* if it does not exists) for the user that is calling the script .
* If bash_history is above 10,000 lines:
 - Lines from 1 to 5000 is going to be remove from bash_history
 - Will be pasted at the end of bash_history.archive.

## bash version required is 4 and up.

The value of Date is a bash4 feature which is
```shell
$(printf "%(%h %d %Y %H:%M:%S)T" -1)
```
If your bash version is less than 4 you can replace it with the (GNU) date utility, something like
```shell
$(date +'%h %d %Y %H:%M:%S')
```
See **strftime(3)** for a more control over the date format.

## Required external utilities
    ed
    crontab
    grep
    wc

## Files created
- "$HOME/.HistLog"
- "$HOME/.bash_history.archive" (*ONLY* if it does not exists.)

```shell
## A crontab entry that looks like this (of course with the absolute path.)
* * * * * HistLog
```
## Installation

* Download and extract the archive and put the HistLog script somewhere within your PATH. Run it once and viola!
  - git clone https://github.com/Jetchisel/HistLog
  - cd HistLog/
  - cp -v HistLog /bin
    * for single user you can put it in ~/bin
  - HistLog
  - tail -f ~/.HistLog

##
* Every user that will call/run HistLog will have the **Files created** in this readme.
* The script will run and will be called via cron every Minute.
* The ~/.HistLog file will grow faster because it logs everything every minute.
* Adjust the time in the cron entry before executing it, should you choose a different time for running HistLog.

## Cron entry

This code contains the crontab entry.
```shell
TimeAndDate="* * * * *"
```
Change only this part.  see **crontab(5)**
```shell
* * * * *
```
Don't foget to enclose it with quotes, just like the original code.

Happy logging!
