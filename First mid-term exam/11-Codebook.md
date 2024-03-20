
## Goal

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Solution

```bash
greygods-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2024-02-28 01:57:33--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py               100%[=======================>]   1.25K  --.-KB/s    in 0s      

2024-02-28 01:57:33 (439 MB/s) - 'code.py' saved [1278/1278]

greygods-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2024-02-28 01:58:13--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt          100%[=======================>]      27  --.-KB/s    in 0s      

2024-02-28 01:58:13 (12.8 MB/s) - 'codebook.txt' saved [27/27]

greygods-picoctf@webshell:~$ ls
code.py  codebook.txt
greygods-picoctf@webshell:~$ nano code.py 
greygods-picoctf@webshell:~$ python3 code.py 
picoCTF{c0d3b00k_455157_197a982c}
greygods-picoctf@webshell:~$ 
````

