## Instructions
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

-   [Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)

## Answer Explanation
cat the `data.txt` an decode using terminal or online

## Entry 11
lvl11 --> ssh to *bandit11*@**bandit.labs.overthewire.org** port 2220
pass: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

## Instructions
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

-   [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)

## Answer Explanation
- Use ROT13

## Entry 12
lvl12 --> ssh to *bandit12*@**bandit.labs.overthewire.org** port 2220
pass: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

## Instructions
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Commands you may need to solve this level
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

## Helpful Reading Material

-   [Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)
-   [Hex](https://stackoverflow.com/questions/43724144/hexdump-reverse-command)

## Answer Explanation
- 1st cp the file to /tmp/[directory I made] to mess with it 
- The file is in hex format so 1st use `xxd -r` to convert it to normal
- Then find the file type and comression tool using `file` command
- Rename file to proper extenson like `gz` , `bz2` etc using mv command
- Decompress using the same tool used for compression like `gzip -d`, `bzip2 -d`,`tar -xvf`(for posix tar archive)
- Keep doing it and always check if it is compressed even if it is named `.bin`
- Finally you will get the file that is `ASCII text` type 
- that has the password

## Entry 13
lvl13 --> ssh to *bandit13*@**bandit.labs.overthewire.org** port 2220
pass: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
