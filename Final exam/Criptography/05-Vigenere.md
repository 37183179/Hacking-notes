## Goal
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".
## Hints
+ https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Vigenere]
└─$ wget https://artifacts.picoctf.net/c/159/cipher.txt 
--2024-05-05 03:46:30--  https://artifacts.picoctf.net/c/159/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.11, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt               100%[==================================>]      43  --.-KB/s    in 0s      

2024-05-05 03:46:30 (50.1 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                    
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}

````

 Download the text file
+ Read its contents
+ I copied and pasted the contents of the file into a tool known as [Vigenere-Cipher](https://www.dcode.fr/vigenere-cipher) so that it would attempt to decipher the ciphertext.
+ Key: CYLAB
+ Ciphertext: rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}
+ Flag: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}
## Notes

## References