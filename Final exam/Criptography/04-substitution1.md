## Goal
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://artifacts.picoctf.net/c/183/message.txt).
## Hints
+ Try a frequency attack
+ Do the punctuation and the individual words help you make any substitutions?
## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/substitution1]
└─$ wget https://artifacts.picoctf.net/c/183/message.txt 
--2024-05-05 03:37:34--  https://artifacts.picoctf.net/c/183/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.11, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[==================================>]     638  --.-KB/s    in 0s      

2024-05-05 03:37:35 (2.41 MB/s) - ‘message.txt’ saved [638/638]

                                                                                                    
┌──(kali㉿kali)-[~/picoCTF/Final_exam/substitution1]
└─$ cat message.txt 
LKOb (bwvek ove lgqkhej kwj osgx) gej g kyqj vo lvrqhkje bjlhetky lvrqjktktvu. Lvukjbkgukb gej qejbjukjz dtkw g bjk vo lwgssjuxjb dwtlw kjbk kwjte lejgktftky, kjlwutlgs (guz xvvxstux) bitssb, guz qevmsjr-bvsftux gmtstky. Lwgssjuxjb hbhgssy lvfje g uhrmje vo lgkjxvetjb, guz dwju bvsfjz, jglw ytjszb g bketux (lgssjz g osgx) dwtlw tb bhmrtkkjz kv gu vustuj blvetux bjeftlj. LKOb gej g xejgk dgy kv sjgeu g dtzj geegy vo lvrqhkje bjlhetky bitssb tu g bgoj, sjxgs juftevurjuk, guz gej wvbkjz guz qsgyjz my rguy bjlhetky xevhqb gevhuz kwj dvesz ove ohu guz qeglktlj. Ove kwtb qevmsjr, kwj osgx tb: qtlvLKO{OE3AH3ULY_4774LI5_4E3_L001_6J0659OM}
````
+ Download the text file
+ Read its contents
+ I copied and pasted the contents of the file into a tool known as [Mono-alphabetic Substitution](https://www.dcode.fr/monoalphabetic-substitution) so that it would attempt to decipher the ciphertext.
	CTFS (SHORT FOR CAPTURE THE FLAG) ARE A TYPE OF COMPUTER SECURITY COMPETITION. CONTESTANTS ARE PRESENTED WITH A SET OF CHALLENGES WHICH TEST THEIR CREATIVITY, TECHNICAL (AND GOOGLING) SKILLS, AND PROBLEM-SOLVING ABILITY. CHALLENGES USUALLY COVER A NUMBER OF CATEGORIES, AND WHEN SOLVED, EACH YIELDS A STRING (CALLED A FLAG) WHICH IS SUBMITTED TO AN ONLINE SCORING SERVICE. CTFS ARE A GREAT WAY TO LEARN A WIDE ARRAY OF COMPUTER SECURITY SKILLS IN A SAFE, LEGAL ENVIRONMENT, AND ARE HOSTED AND PLAYED BY MANY SECURITY GROUPS AROUND THE WORLD FOR FUN AND PRACTICE. FOR THIS PROBLEM, THE FLAG IS: PICOCTF{FR3QU3NCY_4774CK5_4R3_C001_6E0659FB}
## Notes

## References