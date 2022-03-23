## Entry 0
Lvl 0--> ssh to *bandit0*@**bandit.labs.overthewire.org** port 2220
pass: bandit0
## Instructions
The password for the next level is stored in a file called **readme** located in the home directory


## Commands you may need to solve this level

ls, cd, cat, file, du, find

## Entry 1
lvl 1--> ssh to *bandit1*@**bandit.labs.overthewire.org** port 2220
pass:boJ9jbbUNNfktd78OOpsqOltutMc3MY1

Commands used: ls & cat

## Instructions
The password for the next level is stored in a file called **-** located in the home directory

## Commands you may need to solve this level

ls, cd, cat, file, du, find

## Helpful Reading Material

-   [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
-   [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)

## Answer explanation
- The **-** character is a special character for bash that stands for STDIN/STDOUT dev/stdin or dev/stdout that is why it cant take it as a filename
- The solution could be *<* to redirect file output to cat since redirection does not recognize - as special
- We can use commands like rev which dont treat - as special 
- We can give full path to file ./- here referes to . is current directiory / is path separator 
- We cannot use quotes that doesnt work

## Entry 2
Lvl2 --> ssh to *bandit2*@**bandit.labs.overthewire.org** port 2220
pass: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Instructions

The password for the next level is stored in a file called **spaces in this filename** located in the home directory

## Commands you may need to solve this level

ls, cd, cat, file, du, find

## Helpful Reading Material

-   [Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)
-   [Resource](https://linoxide.com/how-to-read-filename-with-spaces-in-linux/)
### Answer
- Spaces usually mean different files
- to mean same file use quotes 
- or \ after each word
- or just use tab autocomplete
## Entry 3
lvl3 --> ssh to *bandit3*@**bandit.labs.overthewire.org** port 2220
pass: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

## Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

## Resources
[Hidden Files](https://devconnected.com/how-to-show-hidden-files-on-linux/)

## Commands you may need to solve this level

ls, cd, cat, file, du, find

## Answer
- To find hidden files use ls -a
- then cat the dotfile/hiddenfile

## Entry 4
lvl4 --> ssh to *bandit4*@**bandit.labs.overthewire.org** port 2220
pass: pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Instructions

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Commands you may need to solve this level

ls, cd, cat, file, du, find

## Resources
[Human Readable](https://newbedev.com/finding-human-readable-files-on-unix)

## Answer explanation
- readable from find doesnt work that is only for access -r not file type
- we need to 1st find all files
- use `find -type f`
- then  pipe this to `file` command to find type of all files'
- but `find type -f | file` doesnt work
- why because there are certain commands which cant take  arguments from STDIN and `file` is one of them
- So we use [`xargs`](https://www.baeldung.com/linux/xargs)
- Which converts the STDIN to command line arguments 
- `find type -f | xargs file` gives the data type of  all files
- But to find only the human readable file we need `grep text`
- this gives only  the text files
- `find -type f | xargs file | grep text` is the final command
- file is starting with *-* thus remember to use full path or <
- result is in -file07

## Entry 5
lvl5-->ssh to *bandit5*@**bandit.labs.overthewire.org** port 2220
pass: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
