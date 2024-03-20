
# Bandit challenges
# Bandit 18 #

## Goal

The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
## Access data

+ Username: bandit18
+ Password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit18@bandit.labs.overthewire.org -p 2220
ssh bandit18@bandit.labs.overthewire.org -p 2220 ls
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:

readme

ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:

awhqfNnAbc1naukrpqDYcF95h7HoMTrC

````

## Notes

## References