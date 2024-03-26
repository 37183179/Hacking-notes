## Goal
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

## Hints
Download the file and search for the flag based on the known prefix.
## Solution

```bash
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/Lookey here]
└─$ wget https://artifacts.picoctf.net/c/125/anthem.flag.txt 
--2024-03-21 11:25:32--  https://artifacts.picoctf.net/c/125/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt     100%[================>] 106.12K  --.-KB/s    in 0.1s    

2024-03-21 11:25:41 (1.01 MB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/Lookey here]
└─$ strings anthem.flag.txt | grep pico         
      we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
````
## Notes

## References