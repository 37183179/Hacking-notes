## Goal
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:65086/)
## Hints
How could you mirror the website on your local machine so you could use more powerful tools for searching?
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Second_exam/Search source]
└─$ wget -r http://saturn.picoctf.net:65086/

┌──(kali㉿kali)-[~/picoCTF/Second_exam/Search source]
└─$ grep -r picoCTF
saturn.picoctf.net:65086/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
````

## Notes

+ **-r**, **--recursive** Turn on [recursive](https://www.computerhope.com/jargon/r/recursive.htm) retrieving.
## References
+ [wget](https://www.computerhope.com/unix/wget.htm)
