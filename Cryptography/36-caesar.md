## Goal
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).

## Solution
+ I download the file and print the content of the downloaded file in the terminal.
+ The challenge itself is giving me the encryption clue.
+ It is using ceasar encryption 
+ I go to the browser to look for a ceasar decryption tool, copy and paste the string.
[cesar decryptor](https://www.dcode.fr/cifrado-cesar)
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}

picoCTF{crossingtherubicondjneoach}

```bash
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/caesar]
└─$ wget https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext
--2024-04-04 21:51:34--  https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext          100%[================>]      35  --.-KB/s    in 0s      

2024-04-04 21:51:34 (22.7 MB/s) - ‘ciphertext’ saved [35/35]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/caesar]
└─$ ls
ciphertext
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/caesar]
└─$ file ciphertext 
ciphertext: ASCII text, with no line terminators
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/caesar]
└─$ cat ciphertext 
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}

|picoCTF{crossingtherubicondjneoach}|
````
## Notes

## References