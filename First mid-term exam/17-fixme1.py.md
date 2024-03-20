
## Goal

Fix the syntax error in this Python script to print the flag.[Download Python script](v)

## Solution

```bash
greygods-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/27/fixme1.py
--2024-03-01 23:52:01--  https://artifacts.picoctf.net/c/27/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py             100%[=======================>]     837  --.-KB/s    in 0s      

2024-03-01 23:52:01 (396 MB/s) - 'fixme1.py' saved [837/837]

greygods-picoctf@webshell:~$ nano fixme1.py 
greygods-picoctf@webshell:~$ cat fixme1.py 

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
  print('That is correct! Here\'s your flag: ' + flag)

greygods-picoctf@webshell:~$ nano fixme1.py 
greygods-picoctf@webshell:~$ cat fixme1.py 

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

greygods-picoctf@webshell:~$ python3 fixme1.py 
That is correct! Here is your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
greygods-picoctf@webshell:~$ 

````

## Notes

## References