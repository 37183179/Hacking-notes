## Goal

#### Description

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm) has extraordinarily helpful information...


## Solution

```bash

greygods-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
--2024-02-26 18:28:55--  https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                  100%[=======================>]  10.68K  --.-KB/s    in 0s      

2024-02-26 18:28:55 (190 MB/s) - 'warm' saved [10936/10936]

greygods-picoctf@webshell:~$ ls
README.txt  flag  warm
greygods-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
greygods-picoctf@webshell:~$ chmod +x ./warm 
greygods-picoctf@webshell:~$ ./warm 
Hello user! Pass me a -h to learn what I can do!
greygods-picoctf@webshell:~$ ./warm -h
Oh, help? I actually do not do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}
greygods-picoctf@webshell:~$ 
````

## Notes

## References