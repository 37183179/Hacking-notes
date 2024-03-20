
# Bandit challenges
# Bandit 17#

## Goal

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Access data

+ Username: bandit17
+ Password: VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit17@bandit.labs.overthewire.org -p 2220
bandit17@bandit:~$ ls --all
.  ..  .bandit16.password  .bash_logout  .bashrc  passwords.new  passwords.old  .profile  .ssh
bandit17@bandit:~$ man diff
bandit17@bandit:~$ diff passwords.new passwords.old
42c42
< hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
---
> p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
bandit17@bandit:~$

````

## Notes

## References