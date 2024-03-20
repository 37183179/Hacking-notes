## Goal

There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

## Solution

+ I opened the link
+ Inspect all parts of the site, it mentions you have a sql error, you probably have errors in your database, so the way to enter would be by SQL Injection
+ The default user name is admin
+ When you login, a sql query is made to the database, so as it is not protected against this kind of attacks, we add in the password part ' OR '1'='1.
+ We will be redirected to the site with the password.
	 Logged in!
	
	Your flag is: picoCTF{s0m3_SQL_c218b685}

## Notes

In computing, **SQL injection** is a [code injection](https://en.wikipedia.org/wiki/Code_injection "Code injection") technique used to [attack](https://en.wikipedia.org/wiki/Attack_(computing) "Attack (computing)") data-driven applications, in which malicious [SQL](https://en.wikipedia.org/wiki/SQL "SQL") statements are inserted into an entry field for execution (e.g. to dump the [database](https://en.wikipedia.org/wiki/Database "Database") contents to the attacker). SQL injection must exploit a [security vulnerability](https://en.wikipedia.org/wiki/Security_vulnerability "Security vulnerability") in an application's software, for example, when user input is either incorrectly filtered for [string literal](https://en.wikipedia.org/wiki/String_literal "String literal") [escape characters](https://en.wikipedia.org/wiki/Escape_sequence "Escape sequence") embedded in SQL statements or user input is not [strongly typed](https://en.wikipedia.org/wiki/Strongly-typed_programming_language "Strongly-typed programming language") and unexpectedly executed. SQL injection is mostly known as an [attack vector](https://en.wikipedia.org/wiki/Attack_vector "Attack vector") for websites but can be used to attack any type of SQL database.

## References
[Sql injection](https://en.wikipedia.org/wiki/SQL_injection#:~:text=SQL%20injection%20occurs%20when%20specially,SQL%20statement%20which%20is%20executed.)
