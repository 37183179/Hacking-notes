## Goal

There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
## Hint

There is data encoded somewhere... there might be an online decoder.
## Solution

```bash
[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2024-03-10 23:32:15--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png           100%[=============================>] 610.57K  1.88MB/s    in 0.3s    

2024-03-10 23:32:16 (1.88 MB/s) - ‘buildings.png’ saved [625219/625219]

┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $zsteg -a buildings.png | grep picoCTF
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"

````

## Notes

**Steganography** is the practice of representing information within another message or physical object, in such a manner that the presence of the information is not evident to human inspection. In computing/electronic contexts, a [computer file](https://en.wikipedia.org/wiki/Computer_file "Computer file"), message, image, or video is concealed within another file, message, image, or video. 
## References

+ [Zsteg](https://github.com/zed-0xff/zsteg)
+ [Steganography](https://en.wikipedia.org/wiki/Steganography)