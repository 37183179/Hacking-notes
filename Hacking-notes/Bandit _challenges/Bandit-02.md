# Bandit challenges
# Bandit 02

## Goal

The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Access data

+ Username: bandit2
+ Password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename" 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ 
````

## Notes

## References