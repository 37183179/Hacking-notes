## Goal
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
## Hints
+ Try using a tool like Wireshark.
+ How can you decrypt the TLS stream?

## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
--2024-03-19 21:46:17--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[================>]  12.85K  --.-KB/s    in 0s      

2024-03-19 21:46:17 (501 MB/s) - ‘capture.pcap’ saved [13163/13163]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
--2024-03-19 21:46:35--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key        100%[================>]   1.66K  --.-KB/s    in 0s      

2024-03-19 21:46:35 (55.5 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet0]
└─$ ls
capture.pcap  picopico.key
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep picoCTF -A 2
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
 picoCTF{nongshim.shrimp.crackers}
````
## Notes

+ ### TLS
	**Transport Layer Security** (**TLS**) is a [cryptographic protocol](https://en.wikipedia.org/wiki/Cryptographic_protocol "Cryptographic protocol") designed to provide communications security over a computer network. The [protocol](https://en.wikipedia.org/wiki/Communication_protocol "Communication protocol") is widely used in applications such as [email](https://en.wikipedia.org/wiki/Email "Email"), [instant messaging](https://en.wikipedia.org/wiki/Instant_messaging "Instant messaging"), and [voice over IP](https://en.wikipedia.org/wiki/Voice_over_IP "Voice over IP"), but its use in securing [HTTPS](https://en.wikipedia.org/wiki/HTTPS "HTTPS") remains the most publicly visible.
	
	The TLS protocol aims primarily to provide security, including [privacy](https://en.wikipedia.org/wiki/Privacy "Privacy") (confidentiality), integrity, and authenticity through the use of [cryptography](https://en.wikipedia.org/wiki/Cryptography "Cryptography"), such as the use of [certificates](https://en.wikipedia.org/wiki/Public_key_certificate "Public key certificate"), between two or more communicating computer applications. It runs in the [presentation layer](https://en.wikipedia.org/wiki/Presentation_layer "Presentation layer") and is itself composed of two layers: the TLS record and the TLS [handshake protocols](https://en.wikipedia.org/wiki/Handshake_(computing) "Handshake (computing)")
 + ### ssldump
		_ssldump_ is an SSL/TLS network protocol analyzer. It identifies TCP connections on the chosen network interface and attempts to interpret them as SSL/TLS traffic. When it identifies SSL/TLS traffic, it decodes the records and displays them in a textual form to stdout. If provided with the appropriate keying material, it will also decrypt the connections and display the application data traffic.
## References
+ [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security)
+ [ssldump](https://linux.die.net/man/1/ssldump)