
## Goal

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Solution

```bash
greygods-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-03-02 00:58:18--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py.1'

runme.py.1            100%[=======================>]     270  --.-KB/s    in 0s      

2024-03-02 00:58:18 (108 MB/s) - 'runme.py.1' saved [270/270]

greygods-picoctf@webshell:~$ python3 runme.py 
picoCTF{run_s4n1ty_run}
greygods-picoctf@webshell:~$ 

````

## Notes

## References