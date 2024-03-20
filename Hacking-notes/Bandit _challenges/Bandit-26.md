
# Bandit challenges
# Bandit 26#

## Goal

Good job getting a shell! Now hurry and grab the password for bandit27!

## Access data

+ Username: bandit26
+ Password: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit26@bandit.labs.overthewire.org -p 2220

 | |                   | (_) | |__ \ / /  
 | |__   __ _ _ __   __| |_| |_   ) / /_  
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \'
 
:shell
bandit26@bandit:~$ ls
bandit27-do  text.txt                                                                 
bandit26@bandit:~$ file bandit27-do 
bandit27-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=037b97b430734c79085a8720c90070e346ca378e, for GNU/Linux 3.2.0, not stripped                                       
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS                                                      
bandit26@bandit:~$ 
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
                                                                                      
                                                                                      
                            

````

## Notes

## References