
# Bandit challenges
# Bandit 10#

## Goal

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Access data

+ Username: bandit10
+ Password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit10@bandit.labs.overthewire.org -p 2220
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
````

## Notes
- **`base64`**: This is the core command for working with base64 encoding.
- **`-d`**: This flag specifies that you want to **decode** the data instead of encoding it.
## References
+ https://linux.die.net/man/1/base64