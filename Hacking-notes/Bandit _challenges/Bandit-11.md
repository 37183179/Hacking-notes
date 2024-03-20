
# Bandit challenges
# Bandit 11#

## Goal

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Access data

+ Username: bandit11
+ Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit11@bandit.labs.overthewire.org -p 2220
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr a-zA-Z n-za-mN-ZA-M
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$

````

## Notes

## References
https://www.gnu.org/software/coreutils/manual/html_node/tr-invocation.html
[ROT13 - Wikipedia](https://en.wikipedia.org/wiki/ROT13