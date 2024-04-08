## Goal
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Solution

+ I downloaded png file and I opened it 
+ The image has this string: "16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14}"
+ I noticed that these numbers represents a letter from alphabet
+ I used a [web application](https://www.boxentriq.com/code-breaking/numbers-to-letters) converts numbers to letters
+ picoctfthenumbersmason

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/The Numbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2024-04-04 20:34:32--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png     100%[================>]  98.36K  --.-KB/s    in 0.07s   

2024-04-04 20:34:32 (1.46 MB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Criptography/The Numbers]
└─$ open the_numbers.png 

16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14}
picoctfthenumbersmason
````
## Notes

## References