
# Bandit challenges
# Bandit 21#

## Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

## Access data

+ Username: bandit21
+ Password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit21@bandit.labs.overthewire.org -p 2220
bandit21@bandit:~$ ls --all /etc/cron.d/
.   cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  .placeholder
..  cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir  sysstat
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:~$



````

## Notes

## References