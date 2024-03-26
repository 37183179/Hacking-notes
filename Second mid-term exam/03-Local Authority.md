## Goal
Can you get the flag?Go to this [website](http://saturn.picoctf.net:50920/) and see what you can discover.
## Hints
How is the password checked on this website?
## Solution
+ Open the link, I notice that there is a login formulary with 2 fields, the first  and the second field are for username and password. I type in a random username and password.
+ The login formulary moves us to another page. In this page I see a text that contains this string: Illegal character in username or password.
+ I open the inspector mode on the web browser, I move to sources section, you will find three files, click on the JavaScript file.
+ You are going to find this function. In this function you are going to find the deafault username and password to access the flag.
	function checkPassword(username, password)
	{
	  if( username === 'admin' && password === 'strongPassword098765' )
	  {
	    return true;
	  }
	  else
	  {
	    return false;
	  }
	}
+ I return the login formulary and type the deafault username and password
+ I get the flag
+ picoCTF{j5_15_7r4n5p4r3n7_05df90c8}

## Notes

## References