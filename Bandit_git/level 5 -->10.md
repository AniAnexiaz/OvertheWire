## Instructions
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

-   human-readable
-   1033 bytes in size
-   not executable

## Commands you may need to solve this level

ls, cd, cat, file, du, *find*
## Resources 
man page of find command

## Answer Explanation
- `find  -size 1033c ! -executable | xargs file | grep text`
- My mistake was `-size 1033c` no dash before 1033 required
- ! is a special operator means NOT 
- `-executable` means executable files 

## Entry 6
lvl6 --> ssh to *bandit6*@**bandit.labs.overthewire.org** port 2220
pass:DXjZPULLxYr17uwoI01bNLQbtFemEgo7

## Instructions

The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

## Commands you may need to solve this level

ls, cd, cat, file, du, find, grep

## Resources
- man page of find
## Answer Explanation
- `find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null`
- `/` because it is somewhere in the system specifically `/var/lib/dpkg/info/bandit7.password`
- `2>/dev/null` to remove errors

## Entry 7
lvl7 --> ssh to *bandit7*@**bandit.labs.overthewire.org** port 2220
pass: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Instructions

The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd
## Answer Explanation
- `cat data.txt | grep millionth`

## Entry 8
lvl8 --> ssh to *bandit8*@**bandit.labs.overthewire.org** port 2220
pass: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Instructions

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

-   [Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

## Answer Explanation
- use `-uniq -u` to find unique lines
- but it doesnt work if the duplicate are not adjacent
- so use `-sort` 
- `cat data.txt | sort | uniq -u`

## Entry 9
lvl9 --> ssh to *bandit9*@**bandit.labs.overthewire.org** port 2220
pass: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Instructions
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Answer Explanation
`strings data.txt | grep "==="`
Strings prints the the printable characters grep searches for the pattern ===
ps: this problem can also be solved with regex learn that .
## Entry 10
lvl10 --> ssh to *bandit10*@**bandit.labs.overthewire.org** port 2220
pass: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

