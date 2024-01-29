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
```
Password for level 5
```
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
## Level 5
The required file is human readable file that means the ascii text file and 1033 bytes in size and not executable  
We need to first change the directory to inhere directory. Then using the ls command, we can get the list of files

