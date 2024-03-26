## Goal
Download the packet capture file and use packet analysis software to find the flag.
- [Download packet capture](https://artifacts.picoctf.net/c/195/network-dump.flag.pcap)
## Hints

Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.
## Solution

+ Just download the file and open it with wireshark
+ And follow the streams

```bash
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Packets Primer]
└─$ wget https://artifacts.picoctf.net/c/195/network-dump.flag.pcap
--2024-03-25 21:49:42--  https://artifacts.picoctf.net/c/195/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.p 100%[================>]     778  --.-KB/s    in 0s      

2024-03-25 21:49:43 (15.0 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Packets Primer]
└─$ wireshark network-dump.flag.pcap   
p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ b 9 d 5 3 7 6 5 }
````
## Notes

## References