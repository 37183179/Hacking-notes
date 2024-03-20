
# Bandit challenges
# Bandit 03

## Goal

The password for the next level is stored in a hidden file in the **inhere** directory.
## Access data

+ Username: bandit3
+ Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit3@bandit.labs.overthewire.org -p 2220
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ ls ./inhere/ --all
.  ..  .hidden
bandit3@bandit:~$ cat ./inhere/.hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~$ 

````

## Notes

## References