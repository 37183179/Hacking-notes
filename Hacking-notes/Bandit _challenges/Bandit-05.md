
# Bandit challenges
# Bandit 05

## Goal

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Access data

+ Username: bandit5
+ Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit5@bandit.labs.overthewire.org -p 2220
bandit5@bandit:~$ man find
bandit5@bandit:~$ find ./ -type f  -size 1033c ! -executable
./inhere/maybehere07/.file2
bandit5@bandit:~$ cat ./inhere/maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
bandit5@bandit:~$ 
````

## Notes
+ **`find ./`**: This tells `find` to start searching from the current directory represented by `./`.
+ **`-type f`**: This option instructs `find` to only consider regular files, excluding directories, symbolic links, or other special file types.
+ **`-size 1033c`**: This condition filters the results further by only selecting files with a size of exactly 1033 bytes (equivalent to 1.033 kilobytes).
+ **`! -executable`**: This negates the "executable" condition, meaning it excludes files that have the executable permission flag set. These files cannot be directly run as programs.

## References
 [https://www.gnu.org/software/findutils/find](https://www.gnu.org/software/findutils/find)