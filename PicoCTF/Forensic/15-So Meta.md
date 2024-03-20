## Goal

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).
## Solution

```bash
[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
--2024-03-10 22:10:21--  https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png            100%[=============================>] 106.25K  --.-KB/s    in 0.1s    

2024-03-10 22:10:22 (719 KB/s) - ‘pico_img.png’ saved [108795/108795]

┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $file pico_img.png 
pico_img.png: PNG image data, 600 x 600, 8-bit/color RGB, non-interlaced
┌─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $open pico_img.png 
─[parrot@parrot]─[~/picoCTF/foresinc]
└──╼ $exiftool pico_img.png 
ExifTool Version Number         : 12.57
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 18:38:23+00:00
File Access Date/Time           : 2024:03:10 22:10:22+00:00
File Inode Change Date/Time     : 2024:03:10 22:10:22+00:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
````

## Notes

**Metadata** (or **metainformation**) is "[data](https://en.wikipedia.org/wiki/Data "Data") that provides information about other data", but not the content of the data itself, such as the text of a message or the image itself.
## References

[Metadata](https://en.wikipedia.org/wiki/Metadata)
