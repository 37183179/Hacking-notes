## Goal
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)
## Hints
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/Mind your Ps and Qs]
└─$ wget https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values
--2024-04-16 21:57:40--  https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                     100%[========================================>]     205  --.-KB/s    in 0s      

2024-04-16 21:57:40 (234 MB/s) - ‘values’ saved [205/205]

                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Mind your Ps and Qs]
└─$ file values 
values: ASCII text
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Mind your Ps and Qs]
└─$ cat values    
Decrypt my super sick RSA:
c: 240986837130071017759137533082982207147971245672412893755780400885108149004760496
n: 831416828080417866340504968188990032810316193533653516022175784399720141076262857
e: 65537   
````

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/Mind your Ps and Qs/RsaCtfTool]
└─$ python3 RsaCtfTool.py -n 831416828080417866340504968188990032810316193533653516022175784399720141076262857 -e 65537 --decrypt 240986837130071017759137533082982207147971245672412893755780400885108149004760496
private argument is not set, the private key will not be displayed, even if recovered.
['/tmp/tmpt7p7g8__']

[*] Testing key /tmp/tmpt7p7g8__.
attack initialized...
attack initialized...
[*] Performing nonRSA attack on /tmp/tmpt7p7g8__.
[+] Time elapsed: 0.0073 sec.
[*] Performing pastctfprimes attack on /tmp/tmpt7p7g8__.
[+] loading prime list file data/visa_emv.txt...
100%|██████████████████████████████████████████████████████████| 2/2 [00:00<00:00, 57456.22it/s]
[+] loading prime list file data/pastctfprimes.txt...
100%|████████████████████████████████████████████████████| 121/121 [00:00<00:00, 1158700.42it/s]
[+] loading prime list file data/ti_rsa_signing_keys.txt...
100%|██████████████████████████████████████████████████████| 34/34 [00:00<00:00, 1159401.11it/s]
[+] Time elapsed: 0.0098 sec.
[*] Performing fibonacci_gcd attack on /tmp/tmpt7p7g8__.
100%|███████████████████████████████████████████████████| 9999/9999 [00:00<00:00, 310750.19it/s]
[+] Time elapsed: 0.0329 sec.
[*] Performing factordb attack on /tmp/tmpt7p7g8__.
[*] Attack success with factordb method !
[+] Total time elapsed min,max,avg: 0.0073/0.0329/0.0167 sec.

Results for /tmp/tmpt7p7g8__:

Decrypted data :
HEX : 0x007069636f4354467b736d6131315f4e5f6e305f67306f645f32333534303336387d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639592405461024281868413
INT (little endian) : 3711855727927123105065790587654259834295257120566283383168470090892271133448040448
utf-8 : picoCTF{sma11_N_n0_g0od_23540368}
utf-16 : 瀀捩䍯䙔獻慭ㄱ也湟弰で摯㉟㔳〴㘳紸
STR : b'\x00picoCTF{sma11_N_n0_g0od_23540368}'

````
## Notes

## References