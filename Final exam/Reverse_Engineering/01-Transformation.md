## Goal
I wonder what this really is... [enc](https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`
## Hints
+ You may find some decoders online
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Transformation]
└─$ wget https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc
--2024-05-06 01:24:46--  https://mercury.picoctf.net/static/0d3145dafdc4fbcf01891912eb6c0968/enc
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 57 [application/octet-stream]
Saving to: ‘enc’

enc                                                        100%[====================================================

2024-05-06 01:24:47 (59.0 MB/s) - ‘enc’ saved [57/57]

                                                                                                                    
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Transformation]
└─$ file enc           
enc: Unicode text, UTF-8 text, with no line terminators
                                                                                                                    
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Transformation]
└─$ cat enc      
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弲㘶㠴挲ぽ
````
+ I downloaded the file and saw what it contained
+ I copied and pasted the contents of the file into [cyberchef](https://gchq.github.io/CyberChef/)
+ The recipe I chose was magic
+ The options I chose were the following:
	Depth: 6
	Intensive mode: Selected
+ This was the flag I got: picoCTF{16_bits_inst34d_of_8_26684c20}
## Notes

## References