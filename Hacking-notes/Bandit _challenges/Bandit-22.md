
# Bandit challenges
# Bandit 22#

## Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Access data

+ Username: bandit22
+ Password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit22@bandit.labs.overthewire.org -p 2220 
bandit22@bandit:~$ ls --all /etc/cron.d
.   cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  .placeholder
..  cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir  sysstat
bandit22@bandit:~$ ls --all /etc/cron.d/cronjob_bandit23
/etc/cron.d/cronjob_bandit23
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo I am user $myname | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$

````

## Notes

## References