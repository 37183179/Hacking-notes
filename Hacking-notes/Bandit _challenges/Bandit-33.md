
# Bandit challenges
# Bandit 33#

## Goal

**At this moment, level 34 does not exist yet.**

## Access data

+ Username: bandit33
+ Password: odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit33@bandit.labs.overthewire.org -p 2220
bandit33@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
-rw-------  1 bandit33 bandit33  430 Oct  5 06:19 README.txt
bandit33@bandit:~$ cat README.txt
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!
bandit33@bandit:~$


````

## Notes

## References