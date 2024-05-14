## Goal
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 6057` [playfair.py](https://mercury.picoctf.net/static/a48f79c95043804d1f43d5bfbffd324a/playfair.py)
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Vigenere]
└─$ nc mercury.picoctf.net 6057
Here is the alphabet: meiktp6yh4wxruavj9no13fb8d027c5glzsq
Here is the encrypted message: y7bcvefqecwfste224508y1ufb21ld
What is the plaintext message? wd9bukbspdtj7skd3kl8d6oa3f03g0
Congratulations! Here's the flag: 2e71b99fd3d07af3808f8dff2652ae0e
````

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/Vigenere]
└─$python3
Python 3.12.3 (tags/v3.12.3:f6650f9, Apr  9 2024, 14:05:25) [MSC v.1938 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> "WD9BUKBSPDTJ7SKD3KL8D6OA3F03G0".lower()
'wd9bukbspdtj7skd3kl8d6oa3f03g0'
```

+ I use a [play fair decoder](https://www.dcode.fr/playfair-cipher)
	+ Text encrypted: y7bcvefqecwfste224508y1ufb21ld
	+ Alphabet or key: meiktp6yh4wxruavj9no13fb8d027c5glzsq
	+ Output: WD9BUKBSPDTJ7SKD3KL8D6OA3F03G
+ Flag: 2e71b99fd3d07af3808f8dff2652ae0e
## Notes
## References