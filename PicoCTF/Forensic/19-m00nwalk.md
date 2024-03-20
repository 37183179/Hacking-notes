## Goal

Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.
# Hints
+ How did pictures from the moon landing get sent back to Earth?
+ What is the CMU mascot?, that might help select a RX option
## Solution

```bash
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ wget https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav
--2024-03-13 14:23:08--  https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav         100%[================>]  10.55M  7.68MB/s    in 1.4s    

2024-03-13 14:23:10 (7.68 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ ls
message.wav
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ file message.wav 
message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ sstv -d message.wav -o message.png 
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [###########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ ls
message.png  message.wav
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/m00nwalk]
└─$ open message.png 
picoCTF{beep_boop_im_in_space}

````


## Notes

 ### **SSTV**
 **Slow-scan television** (**SSTV**) is a picture transmission method, used mainly by [amateur radio operators](https://en.wikipedia.org/wiki/Amateur_radio_operators "Amateur radio operators"), to transmit and receive static pictures via radio in [monochrome](https://en.wikipedia.org/wiki/Monochrome "Monochrome") or color.

A literal term for SSTV is [narrowband television](https://en.wikipedia.org/wiki/Narrow-bandwidth_television "Narrow-bandwidth television"). Analog [broadcast](https://en.wikipedia.org/wiki/Broadcasting "Broadcasting") television requires at least 6 MHz wide channels, because it transmits 25 or 30 picture frames per second (see [ITU analog broadcast standards](https://en.wikipedia.org/wiki/Broadcast_television_systems#ITU_standards "Broadcast television systems")), but SSTV usually only takes up to a maximum of 3 kHz of [bandwidth](https://en.wikipedia.org/wiki/Bandwidth_(signal_processing) "Bandwidth (signal processing)"). It is a much slower method of still picture transmission, usually taking from about eight seconds to a couple of minutes, depending on the mode used, to transmit one image frame.

Since SSTV systems operate on [voice frequencies](https://en.wikipedia.org/wiki/Voice_frequency "Voice frequency"), amateurs use it on [shortwave](https://en.wikipedia.org/wiki/Shortwave "Shortwave") (also known as [HF](https://en.wikipedia.org/wiki/High_frequency "High frequency") by [amateur radio](https://en.wikipedia.org/wiki/Amateur_radio "Amateur radio") operators), [VHF](https://en.wikipedia.org/wiki/Very_high_frequency "Very high frequency") and [UHF](https://en.wikipedia.org/wiki/Ultra_high_frequency "Ultra high frequency") radio.

## References

[SSTV](https://en.wikipedia.org/wiki/Slow-scan_television)
[SSTV decoder](https://github.com/colaclanth/sstv)
