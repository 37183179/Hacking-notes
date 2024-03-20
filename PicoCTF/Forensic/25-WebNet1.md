## Goal
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Hints
+ Try using a tool like Wireshark.
+ How can you decrypt the TLS stream?

## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap 
--2024-03-19 22:12:33--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[================>]  90.36K  --.-KB/s    in 0.07s   

2024-03-19 22:12:34 (1.22 MB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2024-03-19 22:12:49--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key        100%[================>]   1.66K  --.-KB/s    in 0s      

2024-03-19 22:12:49 (48.0 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/WebNet1]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep picoCTF -A 2
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
Short read: -1295 bytes available (expecting 2)
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
       picoCTF{honey.roasted.peanuts}                                                               
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