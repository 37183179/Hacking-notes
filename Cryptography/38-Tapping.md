## Goal
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.

## Hints
+ What kind of encoding uses dashes and dots?
+ The flag is in the format PICOCTF{}
## Solution
+ Enter this command to initiate a connection: nc jupiter.challenges.picoctf.org 48247
+ The connection gave me a string with dashes and dots.
+ Apparently it is morse code, so I went to Cyberchef
+ In Cyberchef I selected From Morse, so that it would decipher the code.
+ PICOCTFM0RS3C0D31SFUN1261438181 

```bash
┌──(kali㉿kali)-[~/picoCTF/Criptography/Tapping]
└─$ nc jupiter.challenges.picoctf.org 48247
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- } 

````
## Notes

## References