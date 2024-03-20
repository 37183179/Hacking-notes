# Bandit challenges
# Bandit-08 #

## Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Access data

+ Username: bandit8
+ Password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit8@bandit.labs.overthewire.org -p 2220
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt |  uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$

````

## Notes
- The output of the `sort` command is then piped (`|`) to the `uniq` command. This means the sorted lines are sent as input to `uniq`.
- The `uniq` command removes duplicate lines from its input.
- The `-u` flag tells `uniq` to only keep unique lines, meaning those that appear only once in the input.
## References
+ https://man7.org/linux/man-pages/man1/sort.1.html
+ https://medium.com/@cuncis/cut-sort-uniq-a-guide-to-text-manipulation-in-linux-cheat-sheet-d251acca9231