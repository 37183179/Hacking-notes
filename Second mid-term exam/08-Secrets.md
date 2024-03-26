## Goal
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:64727/).
## Hints
folders folders folders
## Solution
+ I opened the link
+ I inspected the code and I got this file: src="secret/assets/DX1KYM.jpg".
+ I added the address /secret/ to the link and I was directed to another page.
+ I checked the page again and I got this file: /hidden/file.css
+ I added the following address to the link: /secret/hidden/
+ Redirects you to another page and repeats the same process again: /secret/hidden/superhidden/
+ I inspect the code 
	picoCTF{succ3ss_@h3n1c@10n_790d2615}
## Notes

## References
