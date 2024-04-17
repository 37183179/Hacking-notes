## Goal
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).
## Solution

```bash
                                                                                
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ wget https://artifacts.picoctf.net/c/235/atbash.jpg                                    
--2024-04-16 22:23:08--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.62, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51499 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                 100%[========================================>]  50.29K  --.-KB/s    in 0.06s   

2024-04-16 22:23:09 (904 KB/s) - ‘atbash.jpg’ saved [51499/51499]
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ ls
atbash.jpg
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ file atbash.jpg                             
atbash.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 465x455, components 3
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ strings atbash.jpg

┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/HideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_92533667}

````

+ The name of the image gives you a clue about the encryption.
+ I copied what I had in my file where the information was encrypted with atbash.
+ I used the Atbash Cipher recipe to decrypt the string
krxlXGU{zgyzhs_xizxp_92533667}
picoCTF{atbash_crack_92533667}
## Notes

The `steghide extract` command is used to extract hidden data from a steganographic file. The `-sf` option specifies the steganographic file from which the data is to be extracted.

Here is a breakdown of the command:

- `steghide` is the name of the program
- `extract` is the command to extract data from a steganographic file
- `-sf` is an option that specifies the steganographic file
## References
[Página web sobre Steghide](https://systemweakness.com/steghide-a-beginners-tutorial-35ec0ea90446)

