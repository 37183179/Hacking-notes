
## Goal
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55793/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Solution

+ I open the link. You notice that there is a 3 string with name of 3 text files and field when type the name file, you are going to redirected to content of each file
+ I this case I type the next string  "../../../../../flag.txt" and I redirected to another file with the flag
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}

## Notes
 ../../../../../flag.txt, seems like a reference to a file named "flag.txt" that's eight directories above the current location.
## References