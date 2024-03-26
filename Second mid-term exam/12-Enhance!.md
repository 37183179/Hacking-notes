## Goal
Download this image file and find the flag.
- [Download image file](https://artifacts.picoctf.net/c/100/drawing.flag.svg)
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Forensic/Enhance]
└─$ wget https://artifacts.picoctf.net/c/100/drawing.flag.svg
--2024-03-21 11:18:35--  https://artifacts.picoctf.net/c/100/drawing.flag.svg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4149 (4.1K) [application/octet-stream]
Saving to: ‘drawing.flag.svg’

drawing.flag.svg    100%[================>]   4.05K  --.-KB/s    in 0s      

2024-03-21 11:18:44 (165 MB/s) - ‘drawing.flag.svg’ saved [4149/4149]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/Enhance]
└─$ code .
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/Enhance]
└─$ cat drawing.flag.svg | grep "</tspan>"
         id="tspan3748">p </tspan><tspan
         id="tspan3754">i </tspan><tspan
         id="tspan3756">c </tspan><tspan
         id="tspan3758">o </tspan><tspan
         id="tspan3760">C </tspan><tspan
         id="tspan3762">T </tspan><tspan
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         id="tspan3752">c 3 d _ a a b 7 2 9 d d }</tspan></text>
     picoCTF{ 3 n h 4 n c 3 d _ a a b 7 2 9 d d }
````
## Notes

## References