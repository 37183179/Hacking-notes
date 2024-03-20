# Bandit challenges
# Bandit 07#

## Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Access data

+ Username: bandit7
+ Password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit7@bandit.labs.overthewire.org -p 2220
bandit7@bandit:~$ ls --all
.  ..  .bash_logout  .bashrc  data.txt  .profile
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$
````

## Notes
The `grep` command is a powerful tool in Unix-like systems for searching text within files. Here's a breakdown of the command and its key features:

**Purpose:**
- Searches for lines matching a specified pattern (text, regular expression) within one or more files.
- Displays only the lines containing the matches.

## References

https://www.gnu.org/software/grep/manual/grep.html#Command_002dline-Options