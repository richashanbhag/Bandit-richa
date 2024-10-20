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
exit 
```
Password for Level 1-
```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```
## Level 1
The required filename is '-'. We need to login the server using the command ssh bandit1@bandit.labs.overthewire.org -p 2220 and use the password retrieved in the previous level. Using the ls command, we can get  the list of files. We can use cat command to read the content of - file. We cannot just use cat - . Instead we should use cat ./- 
### Commands:
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
ls
cat ./-
exit 
```
Password for level 2 is
```
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```
## Level 2
The required filename is 'spaces in this filename'. We need to login the server using the command ssh bandit2@bandit.labs.overthewire.org -p 2220 and use the password retrieved in the previous level. Using the ls command, we can get  the list of files. We can use cat command to read the content of spaces in this filename file. We cannot just use cat spaces in this filename as it will think that these all are different files. Instead we should use cat spaces\ in\ this\ filename to show that the filename has spaces in it.
### Commands
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
ls
cat spaces\ in\ this\ filename
exit 
```
Password for level 3-
```
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
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
exit 
```
Password for level 4-
```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
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
exit 
```
Password for level 5
```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
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
exit 
```
Password for level 6
```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
## Level 6
The required file is stored somewhere on the server has all of the following properties:owned by user bandit7, owned by group bandit and 33 bytes in size. We can find the file using find -attribute. We can use find / to Search the entire server and and type f to search for files. We can sort the resulting files using find -user bandit7 to get the files owned by user bandit 7 and -group bandit6 to get the files which are owned by group bandit6 and -size 33c to get the list of files whose size is 33 bytes. To hide the permission denied messages, we can append 2>/dev/null.
### Commands
```
ssh bandit6@bandit.labs.overthewire.org -p 2220
find / -type f -user bandit7 -group bandit6 -size 33c
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
exit 
```
Password for level 7
```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
## Level 7
The password is stored in the file data.txt next to the word millionth. We can use the grep command to find the string millionth in the file.
### Commands
```
ssh bandit7@bandit.labs.overthewire.org -p 2220
ls
grep millionth data.txt
exit 
```
Password for level 8
```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
## Level 8
The password is stored in the file data.txt and only occurs once. sort command sorts the contents of a text file and pipe command is used to when output will serve as input to the next command. uniq -u command can be used to command remove any search result if that result is an exact duplicate of the previous result. So, we can serve the output of sort command as input to the uniq command.
### Commands
```
ssh bandit8@bandit.labs.overthewire.org -p 2220  
ls  
sort data.txt | uniq -u
exit 
```
Password for level 9
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
## Level 9
The password is stored in the file data.txt and is in one of the few human-readable strings, preceded by several ‘=’ characters. strings command is used to extract readable strings from a binary file. We can extract the human readable strings from the file using string command and use this output as input in the grep ==== command.
### Commands
```
ssh bandit9@bandit.labs.overthewire.org -p 2220  
ls   
strings data.txt | grep ====
exit 
```
Password for level 10
```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
## Level 10
The password is stored in the file data.txt and is as base64 encoded data. echo command is used to display the text passed in as an argument.base64 -d command is used to decode the base64 encoded data. We can use the encoded data as input for the base64 -d command.
### Commands
```
ssh bandit10@bandit.labs.overthewire.org -p 2220  
ls
cat data.txt
echo 'VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==' | base64 -d
exit 
```
Password for level 11
```
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
## Level 11
The password is stored in the file data.txt where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions. We can use tr command to translate. Acoording to ROT13, we should convert the set of letters 'n-z' to 'a-m' and 'N-Z' to 'A-M'.
### Commands
```
ssh bandit11@bandit.labs.overthewire.org -p 2220  
ls
cat data.txt
cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'
exit 
```
Password for level 12
```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
## Level 12
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. We need to create a directory under /tmp in which we can work using mkdir. First we make a directory '/tmp/tempo' and copy the file data.txt into the directory using cp command. Then we enter the directory using cd command. Then we rename the file using mv command so it is easier to operate on the file contents. The data is in hexdump format. To read the contents from a hexdump of a file, xxd -r is used. Using file command tells that 'mycompdata' is a gzip type compressed file and 'mydata' is a text file. It is said that the file is compressed repeatedly. To retrieve the text, we need to decompress repeatedly.
Since gzip files have the extension .gz, we rename 'mycompdata' as 'mycompdata.gz' using mv command. gzip -d command is used to decompress a gzip file. Using file command again we get to know that the file has been decompressed into a bzip2 type file, so we rename the file as 'mycompdata.bz2'. bzip2 -d mycompdata.bz2 is used to decompress the bzip2 file. Repeat this till we encounter a tar archive. Rename the file as 'mycompdata.tar' tar -xf  is used to extract a file from a tar archive. 'data5.bin' is extracted, which is also a tar archive. Extracting files from data5.bin using tar and using file shows that data6.bin is a bzip2 type compressed file, which should be decompressed.
Repeat until password is retrieved.
### Commands
```
ssh bandit12@bandit.labs.overthewire.org -p 2220
mkdir /tmp/tempo
cp data.txt /tmp/tempo
cd /tmp/tempo
mv data.txt mydata
xxd -r mydata mycompdata
file *
ls
mv mycompdata mycompdata.gz
gzip -d mycompdata.gz
file *
mv mycompdata mycompdata.bz2
bzip2 -d mycompdata.bz2
file *
mv mycompdata mycompdata.gz
gzip -d mycompdata.gz
file *
mv mycompdata mycompdata.tar
tar -xf mycompdata.tar
ls
file *
tar -xf data5.bin
ls
file *
mv data6.bin data6.bin.bz2
file *
tar -xf data6.bin
ls
file *
mv data8.bin data8.bin.gz
gzip -d data8.bin.gz
file *
cat data8.bin
exit -d
```
Password for level 13
```
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```
## Level 13
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, we don’t get the next password, but we get a private SSH key that can be used to log into the next level. First, we can get the private SSH key by using ls command. Then, we connect to the server using ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220 and get the password using cat command
### Commands
```
ssh bandit13@bandit.labs.overthewire.org -p 2220
ls
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14
exit -d
```
Password for level 14
```
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```
## Level 14
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost. We can connect to localhost on port 30000 using nc (netcat) command and then, submit the password of level 14.
### Commands
```
ssh bandit14@bandit.labs.overthewire.org -p 2220
nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
exit -d
```
Password for level 15
```
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Level 15
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption. OpenSSL is an all-around cryptography library and we can use openssl s_client -connect <hostname>:<port> command to connect.
### Commands
```
ssh bandit15@bandit.labs.overthewire.org -p 2220
openssl s_client -connect localhost:30001
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
exit -d
```
Password for level 16
```
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```
## Level 16
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.   
nmap  commands scans networks and ports. We can check all the ports which have a server listening to them in the range 31000 to 32000.  Next we try to connect to each of the above ports with openssl s_client -connect localhost:<port> command. Port 31790 asks for the password and returns an RSA PRIVATE KEY, which is the required port. We  can store the key in a file in the tmp directory. To read the key into the file, any text editor can be used. We can use  vim for which we type vim <filename> and then press 'i' to enter into inserting mode. After typing, we press 'esc' to stop inserting. Then type :wq to save and exit the file. If we try to connect, we get an error message saying 'Permissions 0664 for 'private16.key' are too open. We can use chmod 400 to get the user read permission, and removes all other permissions and then read the password using cat command.
### Commands
```
ssh bandit16@bandit.labs.overthewire.org -p 2220
nmap localhost -p31000-32000
openssl s_client -connect localhost:31046
openssl s_client -connect localhost:31518
openssl s_client -connect localhost:31691
openssl s_client -connect localhost:31790
mkdir /tmp/randomsshkey
cd /tmp/randomsshkey
touch private16.key
ls
vim private16.key
i
<insert the rsa private key>
<press escape>
:wq
ssh -i private16.key bandit17@bandit.labs.overthewire.org -p 2220
chmod 400 private16.key
ssh -i private16.key bandit17@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit17
exit-d
```
Password for level 17
```
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
```
## Level 17
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new. To identify the differences in both the files, we can use diff command.
### Commands
```
ssh bandit17@bandit.labs.overthewire.org -p 2220
ls
diff passwords.new passwords.old
exit -d
```
Password for level 18
```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```
## Level 18
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH. When we login using ssh bandit18@bandit.labs.overthewire.org -p 2220, we get a "Byebye!" message and get logged out. We can use option -t which forces a pseudo terminal allocation. 
### Commands 
ssh bandit18@bandit.labs.overthewire.org -p 2220
ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
exit -d
```
Password for level 19
```
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
