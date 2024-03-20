## Goal

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static)? This [BASH script](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh) might help!

## Solution

```bash
greygods-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
--2024-02-26 18:53:41--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                100%[=======================>]   8.18K  --.-KB/s    in 0s      

2024-02-26 18:53:41 (89.1 MB/s) - 'static' saved [8376/8376]

greygods-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
--2024-02-26 18:53:59--  https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh              100%[=======================>]     785  --.-KB/s    in 0s      

2024-02-26 18:53:59 (412 MB/s) - 'ltdis.sh' saved [785/785]

greygods-picoctf@webshell:~$ ls
README.txt  flag  ltdis.sh  static  warm
greygods-picoctf@webshell:~$ chmod +x static 
greygods-picoctf@webshell:~$ chmod +x ltdis.sh 
greygods-picoctf@webshell:~$ ./static 
Oh hai! Wait what? A flag? Yes, it is around here somewhere!
greygods-picoctf@webshell:~$ s
Display all 206 possibilities? (y or n)
greygods-picoctf@webshell:~$ ./ltdis.sh 
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
greygods-picoctf@webshell:~$ ls
README.txt  flag  ltdis.sh  static  warm
greygods-picoctf@webshell:~$ ./ltdis.sh static 
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
greygods-picoctf@webshell:~$ ls          
README.txt  ltdis.sh  static.ltdis.strings.txt  warm
flag        static    static.ltdis.x86_64.txt
greygods-picoctf@webshell:~$ grep "pico" static.ltdis.strings.txt 
   1020 picoCTF{d15a5m_t34s3r_ccb2b43e}
greygods-picoctf@webshell:~$ 
````


## Notes

## References
