## Goal

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Hint 
+ Try fixing the file header
+ Magic bytes
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery       
--2024-03-13 14:42:46--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery             100%[================>] 198.18K  1.28MB/s    in 0.2s    

2024-03-13 14:42:47 (1.28 MB/s) - ‘mystery’ saved [202940/202940]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ ls
mystery
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ file mystery       
mystery: data
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ xxd -l 100  mystery
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ cp mystery flag
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ xxd -l 100  flag   
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag 
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ cp mystery flag.png
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag.png 
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ file flag.png 
flag.png: data
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3)

File: flag.png (202940 bytes)
  invalid chunk name "C" DR (43 22 44 52)
ERRORS DETECTED in flag.png
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag.png        
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ file flag.png             
flag.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ open message.png
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in flag.png
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag.png  
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ open message.png    
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in flag.png
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag.png  
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ pngcheck -v flag.png
zlib warning:  different version (expected 1.2.13, using 1.3)

File: flag.png (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  invalid chunk name "�DET" (ffffffab 44 45 54)
ERRORS DETECTED in flag.png
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ hexeditor flag.png  
                                                                                                                      
┌──(kali㉿kali)-[~/picoCTF/Forensic/corrupt]
└─$ open message.png    

````


## Notes

### Magic bytes

This is a list of [file signatures](https://en.wikipedia.org/wiki/File_format#Magic_number "File format"), data used to identify or verify the content of a file. Such signatures are also known as [magic numbers](https://en.wikipedia.org/wiki/Magic_number_(programming)#In_files "Magic number (programming)") or Magic Bytes.

Many file formats are not intended to be read as text. If such a file is accidentally viewed as a text file, its contents will be unintelligible. However, some file signatures can be recognizable when interpreted as text. The column **ISO 8859-1** shows how the file signature appears when interpreted as text in the common [ISO 8859-1](https://en.wikipedia.org/wiki/ISO_8859-1 "ISO 8859-1") encoding, with unprintable characters represented as the control code abbreviation or symbol, or codepage 1252 character where available, or a box otherwise. In some cases the space character is shown as ␠ for clarity.

## References
[Files signatures](https://en.wikipedia.org/wiki/List_of_file_signatures)
