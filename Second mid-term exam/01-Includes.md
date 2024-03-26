## Goal
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58519/) and see what you can discover.
## Solution

+ I open the link, then I press the shortcut  CTR + U to use the inspector mode on web browser
+ The code is a html tag code, on code I see 2 files, the first one is .css file y and last one is a .js file. When click on each one, you see one part of the flag on each one
+ JavaScript file
	function greetings()
	{
	  alert("This code is in a separate file!");
	}
	
	//  f7w_2of2_b8f4b022}
+ CSS file
	 body {
	  background-color: lightblue;
	}
	
	/*  picoCTF{1nclu51v17y_1of2_  */

	picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}

## Notes

## References