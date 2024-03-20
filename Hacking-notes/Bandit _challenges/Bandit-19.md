
# Bandit challenges
# Bandit 19#

## Goal

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Access data

+ Username: bandit19
+ Password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit19@bandit.labs.overthewire.org -p 2220
bandit19@bandit:~$ ls --all
.  ..  bandit20-do  .bash_logout  .bashrc  .profile
bandit19@bandit:~$ file bandit20-do
bandit20-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=037b97b430734c79085a8720c90070e346ca378e, for GNU/Linux 3.2.0, not stripped
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$

````

## Notes

## References