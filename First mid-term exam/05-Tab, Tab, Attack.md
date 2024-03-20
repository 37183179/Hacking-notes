## Goal

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip)
## Solution

```bash
greygods-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
--2024-02-28 01:03:35--  https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip  100%[=======================>]   4.41K  --.-KB/s    in 0s      

2024-02-28 01:03:35 (1.59 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

greygods-picoctf@webshell:~$ ls
Addadshashanammu.zip
greygods-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
greygods-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
greygods-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabita
shpi/Maelkashishi/Onnissiralis/Ularradallaku$ pwd
/home/greygods-picoctf/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku
greygods-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabita
shpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
greygods-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabita
shpi/Maelkashishi/Onnissiralis/Ularradallaku$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=fcea24fb5379795a123bb860267d815e889a6d23, not stripped
greygods-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabita
shpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_d32e018c}
greygods-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabita
shpi/Maelkashishi/Onnissiralis/Ularradallaku$
````


## Notes
I unzipped the .zip file using unzip, looked at the directory that was created, changed directory with cd and tab.

## References