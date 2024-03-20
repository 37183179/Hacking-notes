## Goal

There is some interesting information hidden around this site [http://mercury.picoctf.net:39491/](http://mercury.picoctf.net:39491/). Can you find it?


## Solution
+ We open the link to the page
+ ctr + u
	 Here's the first part of the flag:
	<!-- Here's the first part of the flag: picoCTF{t -->
+ Click on mycss.css, it will redirect us to the file, scroll down and the second part of the flag will not appear until below: 
	/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
+ Click on myjs.js, it will redirect us to the myjs.js file and give us this hint: 
	/* How can I keep Google from indexing my website? */
	+ To the link of the page we remove myjs.js and add robots.txt
	It will give us the last part of the flag:
	User-agent: *
	Disallow: /index.html
	 Part 3: t_0f_pl4c
	 I think this is an apache server... can you Access the next flag?
 + In the same address above we remove robots.txt and add .htaccess, it will give us the fourth part of the flag: 
	 Part 4: 3s_2_lO0k
	 I love making websites on my Mac, I can Store a lot of information there.
 
 + In the same address above we remove .htaccess and add .DS_Store, it will give us the fifth part of the flag: 

Congrats! You completed the scavenger hunt. Part 5: _f7ce8828}

picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_f7ce8828}

## Notes

## .robots.txt

A robots.txt file is a text file that tells web crawlers which pages on your site they can and can't crawl. This file is important for SEO because it can help you control how your site is indexed by search engines.

To create a robots.txt file, you simply need to create a text file with the name "robots.txt" and place it in the root directory of your website. The file should contain a list of directives that tell crawlers which pages to crawl and which pages to avoid.
## .htaccess

An .htaccess file is a configuration file that can be used to control how your web server handles requests for files on your site. This file can be used to do things like redirect pages, set up password protection, and more.

To create an .htaccess file, you simply need to create a text file with the name ".htaccess" and place it in the directory where you want the changes to apply.

## .DS_Store

.DS_Store files are not typically visible to users, but they can be made visible by changing the Finder preferences.

It is generally not necessary to delete .DS_Store files, but they can be deleted if you want to save space or if you are concerned about privacy.

## References
- [.DS_Store Files and Why You Should Know](https://buildthis.com/ds_store-files-and-why-you-should-know-about-them/)
- [Apache HTTP Server Tutorial: .htaccess files](https://httpd.apache.org/docs/current/howto/htaccess.html)
- [How to write and submit a robots.txt file](https://developers.google.com/search/docs/crawling-indexing/robots/create-robots-txt)
