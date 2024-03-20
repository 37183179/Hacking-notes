
# Bandit challenges
# Bandit #

## Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

## Access data

+ Username: bandit20
+ Password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ echo -n 'VxCazJaVykI6W36BkBU0mJTCM8rR95XT' | nc -l -p 2024
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
bandit20@bandit:~$
````

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
bandit20@bandit:~$ ./suconnect 2024
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
bandit20@bandit:~$
````
## Notes

## References