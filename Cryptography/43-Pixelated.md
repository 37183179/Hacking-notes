## Goal
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png)
## Hints 
+ [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
+ Think of different ways you can "stack" images
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ wget https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png
--2024-04-16 22:10:14--  https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197171 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png             100%[========================================>] 192.55K  1.06MB/s    in 0.2s    

2024-04-16 22:10:14 (1.06 MB/s) - ‘scrambled1.png’ saved [197171/197171]

                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ wget https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png
--2024-04-16 22:10:27--  https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png             100%[========================================>] 192.55K  1.04MB/s    in 0.2s    

2024-04-16 22:10:27 (1.04 MB/s) - ‘scrambled2.png’ saved [197173/197173]

                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ open scrambled1.png 
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ pip install numpy
Defaulting to user installation because normal site-packages is not writeable
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 24.3 will enforce this behaviour change. A possible replacement is to use pip for package installation.. Discussion can be found at https://github.com/pypa/pip/issues/12330                                             
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 24.3 will enforce this behaviour change. A possible replacement is to use pip for package installation.. Discussion can be found at https://github.com/pypa/pip/issues/12330                              
Requirement already satisfied: numpy in /usr/lib/python3/dist-packages (1.24.2)                             
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ nano decryptImage.py
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ python3 decryptImage.py 
[[[114 205 167]
  [ 10 190  14]
  [174  11 103]
  ...
  [242  70 253]
  [251  39  81]
  [ 82  63  73]]

 [[237 105 244]
  [ 81 185  26]
  [ 67 147 251]
  ...
  [  4 187 189]
  [ 12 150  56]
  [214 228 185]]

 [[178 166  74]
  [220 157  54]
  [190 114 212]
  ...
  [117  19  28]
  [200 248  86]
  [234 209 115]]

 ...

 [[114 228 223]
  [140  23 203]
  [ 77 123  38]
  ...
  [ 38 232 223]
  [ 30 232  51]
  [109 103 118]]

 [[ 70 182 228]
  [108 199 182]
  [161 255  24]
  ...
  [ 43 109 139]
  [ 83 182 242]
  [ 12 135  49]]

 [[116 128 123]
  [173 130 215]
  [ 71 210 214]
  ...
  [179  31 212]
  [202 164  79]
  [197 152  40]]]
[[[141  50  88]
  [245  65 241]
  [ 81 244 152]
  ...
  [ 13 185   2]
  [  4 216 174]
  [173 192 182]]

 [[ 18 150  11]
  [174  70 229]
  [188 108   4]
  ...
  [251  68  66]
  [243 105 199]
  [ 41  27  70]]

 [[ 77  89 181]
  [ 35  98 201]
  [ 65 141  43]
  ...
  [138 236 227]
  [ 55   7 169]
  [ 21  46 140]]

 ...

 [[141  27  32]
  [115 232  52]
  [178 132 217]
  ...
  [217  23  32]
  [225  23 204]
  [146 152 137]]

 [[185  73  27]
  [147  56  73]
  [ 94   0 231]
  ...
  [212 146 116]
  [172  73  13]
  [243 120 206]]

 [[139 127 132]
  [ 82 125  40]
  [184  45  41]
  ...
  [ 76 224  43]
  [ 53  91 176]
  [ 58 103 215]]]
                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Criptography/Pixelated]
└─$ open new.png 

picoCTF{0542dc1d}
````
## Notes

## References