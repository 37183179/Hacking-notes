
# Bandit challenges
# Bandit 01

## Goal

The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Access data

+ Username: bandit1
+ Password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit1@bandit.labs.overthewire.org -p 2220
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
````

## Notes

## References