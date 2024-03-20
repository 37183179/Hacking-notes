
## Goal

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786
## Solution

+ I opened the link and inspected the code
+ I saw that the code was obfuscated on line 10, so I used a tool to form the code.
+ I found an array of strings that has the possible combinations.
+ In the verify method it indicates the positions of the array.
+ The indicated positions of the method in the array are concatenated.
+ The positions used were 8, 9, 1 and 0.
	picoCTF{not_this_again_ef49bf}
+ All this was done using the inspector mode of the browser to be used and the console that provides this mode.

## Notes

## References