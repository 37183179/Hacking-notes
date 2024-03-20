
# Bandit challenges
# Bandit 09 #

## Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Access data

+ Username: bandit9
+ Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit9@bandit.labs.overthewire.org -p 2220
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep "="
=2""L(
x]T========== theG)"
========== passwordk^
Y=xW
t%=q
========== is
4=}D3
{1\=
FC&=z
=Y!m
        $/2`)=Y
4_Q=\
MO=(
?=|J
WX=DA
{TbJ;=l
[=lI
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
>8=6
=r=_
=uea
zl=4

````

## Notes
- `strings` only extracts printable characters, so information encoded in non-printable characters might be missed.
- `grep` is case-sensitive by default. If you want to search for "=" regardless of case, use the `-i` flag (e.g., `grep -i "="`).

## References
+ https://man7.org/linux/man-pages/man1/strings.1.html
+ https://man7.org/linux/man-pages/man1/grep.1.html