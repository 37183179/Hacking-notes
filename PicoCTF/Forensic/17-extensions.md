## Goal

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
## Hints
+ How do operating systems know what kind of file it is? (It's not just the ending!
+ Make sure to submit the flag as picoCTF{XXXXX}

## Solution

```bash
┌──[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
--2024-03-10 21:59:05--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt            100%[===================>]   9.75K  --.-KB/s    in 0s      

2024-03-10 21:59:06 (196 MB/s) - ‘flag.txt’ saved [9984/9984]

┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $file flag.txt 
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $mv flag.txt flag.png
┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $ls
flag.png  garden.jpg
[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $open flag.png 
[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $picoCTF{now_you_know_about_extensions}
````


## Notes

## References