
## Goal

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.
## Solution

```bash
greygods-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 > flag.txt && grep picoCTF flag.txt
picoCTF{digital_plumb3r_5ea1fbd7}
greygods-picoctf@webshell:~$
````

## Notes

## References
