# Bandit challenges
# Bandit 04#

## Goal

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
## Access data

+ Username: bandit4
+ Password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit4@bandit.labs.overthewire.org -p 2220
bandit4@bandit:~$ man xargs
bandit4@bandit:~$ 
bandit4@bandit:~$ find ./ -type f | xargs file
./inhere/-file01: data
./inhere/-file02: data
./inhere/-file08: data
./inhere/-file06: data
./inhere/-file00: data
./inhere/-file04: data
./inhere/-file05: data
./inhere/-file07: ASCII text
./inhere/-file03: data
./inhere/-file09: data
./.profile:       ASCII text
./.bashrc:        ASCII text
./.bash_logout:   ASCII text
bandit4@bandit:~$ cat ./inhere/-file07 
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
````

## Notes
If you want all options what has a specific command use the command: "**man** *name of the command*"

+ **`find`**: This command starts by searching the current directory (represented by ./) for files.
+ **`-type`** f: This option tells find to only identify files (regular files), excluding directories, symbolic links, and other special file types.
+ **`|`**: This pipe symbol sends the output of the previous command (find) as input to the next command (xargs).
+ **`xargs`**: This tool takes a list of items (in this case, filenames) and executes a command on each item individually.
+ **`file`**: This command analyzes the provided files and tries to determine their type and content.

## References
 [https://www.gnu.org/software/findutils/find](https://www.gnu.org/software/findutils/find)
