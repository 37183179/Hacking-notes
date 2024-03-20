
## Goal

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.
## Solution

```bash
greygods-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
--2024-02-28 02:13:37--  https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                  100%[=======================>]  14.21K  --.-KB/s    in 0s      

2024-02-28 02:13:37 (292 MB/s) - 'file' saved [14551/14551]

greygods-picoctf@webshell:~$ ls
convertme.py  file
greygods-picoctf@webshell:~$ file file 
file: ASCII text, with very long lines (4200)
greygods-picoctf@webshell:~$ grep -e "picoCTF{" file 
picoCTF{grep_is_good_to_find_things_5af9d829}
greygods-picoctf@webshell:~$
````


## Notes

The `grep -e` command is used to search for text patterns in files. Here's a breakdown of what each part does:

- `grep`: This is the main command itself. It's responsible for searching for patterns in text.
- `-e`: This is an option flag for `grep`. The `-e` flag tells `grep` that the following argument is the pattern to search for.
## References

[Grep Gnu manual](https://www.gnu.org/software/grep/manual/grep.html)
