
# Bandit challenges
# Bandit 14#
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Goal

## Access data

+ Username: bandit14
+ Password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$

````

## Notes

The `nc` command, also known as Netcat, is a versatile network debugging and exploration tool available in most Unix-like systems.

- **Creating TCP or UDP connections:** `nc` can establish either TCP or UDP connections to specified hosts and ports.
- **Listening for connections:** It can also act as a server, listening on a specific port for incoming connections.

## References
https://unix.stackexchange.com/questions/113491/can-xxd-be-used-to-output-the-binary-representation-of-hex-number-not-a-string