## Goal

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
## Hint

+ Try using a tool like Wireshark
+ What are streams?
## Solution

```bash
┌─[parrot@parrot]─[~/picoCTF]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2024-03-10 23:55:07--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[===================>] 233.84K   999KB/s    in 0.2s    

2024-03-10 23:55:08 (999 KB/s) - ‘capture.pcap’ saved [239455/239455]

┌─[parrot@parrot]─[~/picoCTF]
└──╼ $wireshark capture.pcap 
````

+ I opened wireshark, in the packet captures part I right clicked, went to Follow->UDP Stream.
+ The only thing I had to do was to change the Stream value to 6

picoCTF{StaT31355_636f6e6e}
## Notes

A so called TCP or UDP 'stream' is **a representation of a transport layer connection between two nodes**. These connections are defined by their network layer source and destination addresses and transport layer ports, and for TCP by their state. Wireshark assigns an index number to each of these streams it sees
## References

[UDP or TCP stream](https://ask.wireshark.org/question/26728/how-could-wireshark-pick-out-the-streams-of-udp-or-tcp/#:~:text=A%20so%20called%20TCP%20or,of%20these%20streams%20it%20sees)
