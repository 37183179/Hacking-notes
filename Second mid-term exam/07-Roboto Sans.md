## Goal

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:56615/) out.
## Solution
+ I opened the link.
+ I added to the URL /robots.txt to access this file, it redirected me to the file.
	User-agent *
	Disallow: /cgi-bin/
	Think you have seen your flag or want to keep looking.
	
	ZmxhZzEudHh0;anMvbXlmaW
	anMvbXlmaWxlLnR4dA==
	svssshjweuiwl;oiho.bsvdaslejg
	Disallow: /wp-admin/
+ The first two strings are in Base64, user [Base64] converter(https://www.base64decode.org/) the second one gave me this: js/myfile.txt
+ To the original link I added the result of the conversion, it redirected me to another page with the flag.
		picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

## Notes

## References