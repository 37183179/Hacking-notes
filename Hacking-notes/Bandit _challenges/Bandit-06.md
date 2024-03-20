
# Bandit challenges
# Bandit 06#

## Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Access data

+ Username: bandit6
+ Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit6@bandit.labs.overthewire.org -p 2220
bandit6@bandit:~$ find / -type f 2>/dev/null -size 33c -user bandit7 -group bandit6
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$

````

## Notes
- **Location:** Starts from the root directory (`/`) and searches recursively using the `find` command.
- **File type:** Only searches for regular files (`-type f`), excluding directories, symbolic links, etc.
- **Size:** Files with a size of exactly 33 bytes (`-size 33c`).
- **Owner:** Owned by the user `bandit7`.
- **Group:** Belonging to the group `bandit6`.

However, the `2>/dev/null` part of the command redirects any standard error output (e.g., error messages) to `/dev/null`, which is a special file that discards any data written to it. This effectively silences any errors that might occur during the search, which could be a security risk as it might hide potential issues.

## References
https://www.gnu.org/software/findutils/manual/html_node/find_html/index.html#SEC_Contents