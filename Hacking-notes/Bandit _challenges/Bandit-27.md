
# Bandit challenges
# Bandit 27#

## Goal

There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Access data

+ Username: bandit27
+ Password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit27@bandit.labs.overthewire.org -p 2220
bandit27@bandit:~$ ls
bandit27@bandit:~$ mkdir /tmp/ali
bandit27@bandit:~$ cd /tmp/ali
bandit27@bandit:/tmp/ali$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/ali$ ls
repo
bandit27@bandit:/tmp/ali$ cd repo/
bandit27@bandit:/tmp/ali/repo$ ls
README
bandit27@bandit:/tmp/ali/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/ali/repo$
````

## Notes

## References