## Goal
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849
## Solution

+ I opened the link
+ Inspect all parts of the site, it mentions you have a sql error, you probably have errors in your database, so the way to enter would be by SQL Injection
+ The default user name is admin
+ When you login, a sql query is made to the database, so as it is not protected against these types of attacks, we tried to do the same as the previous challenge, but it is protected.
+ So we tried with a very used password which is "password", but it didn't work, so for the username query we also added a very common user which is "admin", we added a simple comma to ignore the name verification:
		'username: admin';
		password: password
		# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_fa983901}
## Notes

## References

