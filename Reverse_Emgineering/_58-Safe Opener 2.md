## Goal
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/288/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
## Hints 
+ Download and try to decompile the file.
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/Safe Opener 2]
└─$ wget https://artifacts.picoctf.net/c/288/SafeOpener.class
--2024-04-26 14:00:03--  https://artifacts.picoctf.net/c/288/SafeOpener.class
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2036 (2.0K) [application/octet-stream]
Saving to: ‘SafeOpener.class’

SafeOpener.class                       100%[===========================================================================>]   1.99K  --.-KB/s    in 0s      

2024-04-26 14:00:03 (15.9 MB/s) - ‘SafeOpener.class’ saved [2036/2036]

                                                                                                                                                           
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/Safe Opener 2]
└─$ file SafeOpener.class 
SafeOpener.class: compiled Java class data, version 52.0 (Java 1.8)
                                                                                                                                                           
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/Safe Opener 2]
└─$ strings SafeOpener.class | grep picoCTF
,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_5bfbd6f1}
````
## Notes

## References