
# Bandit challenges
# Bandit 25#

## Goal 

Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.
## Access data

+ Username: bandit25
+ Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit25@bandit.labs.overthewire.org -p 2220

ssh -i bandit26.sshkey bandit26@localhost -p 2220

:r /etc/bandit_pass/bandit26
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1


````



## Notes

## References