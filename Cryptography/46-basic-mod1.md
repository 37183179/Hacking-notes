## Goal
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Hints
+ Do you know what `mod 37` means?
+ `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solution

```bash
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/129/message.txt
--2024-04-16 21:24:24--  https://artifacts.picoctf.net/c/129/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.3, 3.161.225.62, 3.161.225.11, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.3|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 86 [application/octet-stream]
Saving to: ‘message.txt’

message.txt         100%[================>]      86  --.-KB/s    in 0s      

2024-04-16 21:24:24 (249 MB/s) - ‘message.txt’ saved [86/86]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ file message.txt 
message.txt: ASCII text, with no line terminators
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ cat message.txt 
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213                                                                              
┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ nano mod37.py   
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ cat mod37.py   

import string
data = open('message.txt').read().split()
print(data)
alphabet = string.ascii_lowercase + string.digits + "_" + string.ascii_uppercase
flag = "picoCTF{"
for i in data:
	flag += alphabet[int(i) % 37]
flag += "}"
print(flag)

┌──(kali㉿kali)-[~/picoCTF/Criptography/basic-mod1]
└─$ python3 mod37.py 
PS C:\Users\oliva\Downloads> python3.12.exe .\mod37.py
['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']
picoCTF{r0und_n_r0und_add17ec2}
````
## Notes

## References