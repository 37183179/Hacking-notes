## Goal

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solution

+ Open the file with the command wireshark capture.pcap
+ Press a **ctr + alt + shft+ u** to view the udp streams
+ I saw the content, in stream 32 I got a packet with the word **start** and in **stream 60** I also got a packet with the word **end**, what they had in common is that these packets went out on **port 22**.
+ I applied a filter that only showed me the packets that went out on **port 22**: **udp.dstport == 22**  I applied a filter that only showed me the packets that went out on **port 22**.
+ In the information section we see that they are all greater than 5000, we can deduce that if we subtract the 5000 from each packet, it will give us an ascii character.
+ Select all the packets and export them to a text file in wireshark. The file name is as follows: **"flag.txt "**
+ Run this command at the address where we have our text file: **cat flag.txt | grep UDP | awk '{print $7}' | cut -c2- | grep -v 000**
+ The result I copied and pasted it in [cyberchef](https://gchq.github.io/CyberChef/), I generated the flag
   picoCTF{p1LLf3r3d_data_v1a_st3g0}


Translated with DeepL.com (free version)

```bash
┌─[parrot@parrot]─[~/picoCTF]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
--2024-03-15 01:04:22--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap        100%[===================>] 109.69K   726KB/s    in 0.2s    

2024-03-15 01:04:22 (726 KB/s) - ‘capture.pcap’ saved [112318/112318]

┌─[parrot@parrot]─[~/picoCTF]
└──╼ $ls
capture.pcap
┌─[parrot@parrot]─[~/picoCTF]
└──╼ $wireshark capture.pcap 
┌─[parrot@parrot]─[~/picoCTF]
└──╼ $cat flag.txt | grep UDP | awk '{print $7}' | cut -c2- | grep -v 000
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125
````

## Notes

## References