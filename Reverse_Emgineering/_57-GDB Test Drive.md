## Goal
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/86/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/GDB Test Drive]
└─$ wget https://artifacts.picoctf.net/c/86/gdbme                                             
--2024-04-26 13:47:26--  https://artifacts.picoctf.net/c/86/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: ‘gdbme.1’

gdbme.1                                100%[===========================================================================>]  16.65K  --.-KB/s    in 0.006s  

2024-04-26 13:47:27 (2.84 MB/s) - ‘gdbme.1’ saved [17048/17048]

                                                                                                                                                           
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/GDB Test Drive]
└─$ chmod +x gdbme                  
                                                                                                                                                           
┌──(kali㉿kali)-[~/picoCTF/Rerverse_Engineering/GDB Test Drive]
└─$ gdb gdbme 
picoCTF{d3bugg3r_dr1v3_72bd8355}
````

[GDB output](Screenshot 2024-04-26 114648.png)
## Notes

## References