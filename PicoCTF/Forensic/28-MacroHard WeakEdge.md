## Goal

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics%20is%20fun.pptm)
## Solution

```bash
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ wget https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics%20is%20fun.pptm
--2024-03-20 01:11:41--  https://mercury.picoctf.net/static/9a7436948cc502e9cacf5bc84d2cccb5/Forensics%20is%20fun.pptm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100093 (98K) [application/octet-stream]
Saving to: ‘Forensics is fun.pptm’

Forensics is fun.pp 100%[================>]  97.75K  --.-KB/s    in 0.08s   

2024-03-20 01:11:41 (1.26 MB/s) - ‘Forensics is fun.pptm’ saved [100093/100093]

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ ls
'Forensics is fun.pptm'
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ file Forensics\ is\ fun.pptm 
Forensics is fun.pptm: Microsoft PowerPoint 2007+
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ unzip Forensics\ is\ fun.pptm 

                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ ls                    
'[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ code .                
                                                                             
┌──(kali㉿kali)-[~/picoCTF/Forensic/MacroHard WeakEdge]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
                                                                        

````
## Notes

### What is PPTM file format?

PPTM is a file format for PowerPoint files that have been saved in the macro-enabled format. This format allows users to create presentations that contain macros, which are programs that can automate certain tasks. It is most commonly used in businesses and educational settings.
### PPTM File Info

PPTM stands for PowerPoint Macro-Enabled Presentation. It is a file format used for presentations created in Microsoft PowerPoint. These files contain macros, which are small programs written in Visual Basic for Applications (VBA) language and which can automate tasks in PowerPoint. They can include features such as custom animations, transitions, and audio/video clips. PPTM files are similar to PPTX files, but they are not compatible with other presentation software programs.
### What does PPTM file format stand for?

PPTM stands for PowerPoint Presentation.
## References

[PPTM](https://kb.fileformat.app/extension/pptm-file-info/#:~:text=PPTM%20stands%20for%20PowerPoint%20Macro,can%20automate%20tasks%20in%20PowerPoint.)