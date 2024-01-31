# Bandit-richa
This repository contains writeup for helping in solving bandits by Richa Ganesh Shanbhag  
## Level 0
"ssh" is used for remote login into a server and for executing commands on a remote machine.    
"bandit.labs.overthewire.org" is the host and "2220" is the port.  
"ls" shows the list of available files  
"file <filename>" shows the type of file  
"cat <filename>" shows the content of the file 
exit -d is used to close the connection and exit.  
We need to login the server using the command ssh bandit0@bandit.labs.overthewire.org -p 2220. Using the ls command, we can get  the list of files. We can use cat command to read the content of readme file.
### Commands:
```
ssh bandit0@bandit.labs.overthewire.org -p 2220  
ls
cat readme
exit -d
```
Password for Level 1-
```
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
## Level 1
The required filename is '-'. We need to login the server using the command ssh bandit1@bandit.labs.overthewire.org -p 2220 and use the password retrieved in the previous level. Using the ls command, we can get  the list of files. We can use cat command to read the content of - file. We cannot just use cat - . Instead we should use cat ./- 
### Commands:
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
ls
cat ./-
exit -d
```
Password for level 2 is
```
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
## Level 2
The required filename is 'spaces in this filename'. We need to login the server using the command ssh bandit2@bandit.labs.overthewire.org -p 2220 and use the password retrieved in the previous level. Using the ls command, we can get  the list of files. We can use cat command to read the content of spaces in this filename file. We cannot just use cat spaces in this filename as it will think that these all are different files. Instead we should use cat spaces\ in\ this\ filename to show that the filename has spaces in it.
### Commands
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
ls
cat spaces\ in\ this\ filename
exit -d
```
Password for level 3-
```
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
## Level 3
cd command is used to change the working directory  
ls -a command is used to see the list of hidden files.   
The required file is hidden in the inhere directory. We have to change the directory from home to inhere. We can use cd command to change the directory. As the file is hidden, we can use ls -a command and read the hiiden file.
### Commands
```
ssh bandit3@bandit.labs.overthewire.org -p 2220
cd inhere
ls -a
cat .hidden
exit -d
```
Password for level 4-
```
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
## Level 4
The required file is human readable file that means the ascii text file.  
We need to first change the directory to inhere directory. Then using the ls command, we can get the list of files and we can use  file ./* to read  the type of all the files and then read the ASCII text file using the cat command.
### Commands
```
ssh bandit4@bandit.labs.overthewire.org -p 2220  
cd inhere  
ls
file ./*
cat ./-file07
exit -d
```
Password for level 5
```
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
## Level 5
The required file is human readable file that means the ascii text file and 1033 bytes in size and not executable. find -attribute command can be used to filter the resulting files. We can use the attribute ! -executable to get the non executable files and -size 1033c gives us the list of files whose size is 1033 bytes and then, we can use find to find the file type.
We need to first change the directory to inhere directory. Then using the ls command, we can get the list of files. Using the find attribute commands, we can filter the results and get the desired file  
### Commands
```
ssh bandit5@bandit.labs.overthewire.org -p 2220  
cd inhere  
ls
find ! -executable -size 1033c
file ./maybehere07/.file2
cat ./maybehere07/.file2
exit -d
```
Password for level 6
```
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Level 6
The required file is stored somewhere on the server has all of the following properties:owned by user bandit7, owned by group bandit and 33 bytes in size. We can find the file using find -attribute. We can use find / to Search the entire server and and type f to search for files. We can sort the resulting files using find -user bandit7 to get the files owned by user bandit 7 and -group bandit6 to get the files which are owned by group bandit6 and -size 33c to get the list of files whose size is 33 bytes. To hide the permission denied messages, we can append 2>/dev/null.
### Commands
```
ssh bandit6@bandit.labs.overthewire.org -p 2220
find / -type f -user bandit7 -group bandit6 -size 33c
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
exit -d
```
Password for level 7
```
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
## Level 7
The password is stored in the file data.txt next to the word millionth. We can use the grep command to find the string millionth in the file.
### Commands
```
ssh bandit7@bandit.labs.overthewire.org -p 2220
ls
grep millionth data.txt
exit -d
```
Password for level 8
```
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Level 8
The password is stored in the file data.txt and only occurs once. sort command sorts the contents of a text file and pipe command is used to when output will serve as input to the next command. uniq -u command can be used to command remove any search result if that result is an exact duplicate of the previous result. So, we can serve the output of sort command as input to the uniq command.
### Commands
```
ssh bandit8@bandit.labs.overthewire.org -p 2220  
ls  
sort data.txt | uniq -u
exit -d
```
Password for level 9
```
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Level 9
The password is stored in the file data.txt and is in one of the few human-readable strings, preceded by several ‘=’ characters. strings command is used to extract readable strings from a binary file. We can extract the human readable strings from the file using string command and use this output as input in the grep ==== command.
### Commands
```
ssh bandit9@bandit.labs.overthewire.org -p 2220  
ls   
strings data.txt | grep ====
exit -d
```
Password for level 10
```
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
## Level 10
The password is stored in the file data.txt and is as base64 encoded data. echo command is used to display the text passed in as an argument.base64 -d command is used to decode the base64 encoded data. We can use the encoded data as input for the base64 -d command.
### Commands
```
ssh bandit10@bandit.labs.overthewire.org -p 2220  
ls
cat data.txt
echo 'VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==' | base64 -d
exit -d
```
Password for level 11
```
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
## Level 11
The password is stored in the file data.txt where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions. We can use tr command to translate. Acoording to ROT13, we should convert the set of letters 'n-z' to 'a-m' and 'N-Z' to 'A-M'.
### Commands
```
ssh bandit11@bandit.labs.overthewire.org -p 2220  
ls
cat data.txt
cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'
exit -d
```
Password for level 12
```
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
