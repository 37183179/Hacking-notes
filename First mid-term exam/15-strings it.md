
## Goal

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?
## Solution

```bash
greygods-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2024-02-28 02:26:44--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings               100%[=======================>] 757.84K  1.85MB/s    in 0.4s    

2024-02-28 02:26:44 (1.85 MB/s) - 'strings' saved [776032/776032]

greygods-picoctf@webshell:~$ strings strings > flag.txt
greygods-picoctf@webshell:~$ grep -e "picoCTF" flag.txt 
picoCTF{5tRIng5_1T_7f766a23}
greygods-picoctf@webshell:~$
````


## Notes

The `strings` command in Linux is a handy tool for peeking into the hidden world of binary files. Here's what it does:

- **Extracts printable strings:** Unlike the `cat` command that displays everything in a file, `strings` focuses on finding sequences of characters that can be read by humans. These are typically letters, numbers, and symbols that form words and messages.
- **Targets binary files:** `strings` is primarily designed to work with binary files, which are programs and other non-text files on your system. These files store information in a way computers understand, not directly readable by humans.
- **Uncovers hidden details:** By searching for printable strings, `strings` can reveal information embedded within binary files. This might include things like:
    - Function and variable names used within the program's code.
    - Error messages displayed by the program.
    - Configuration settings or text instructions stored in the binary.

## References

[Strings command](https://www.ibm.com/docs/en/aix/7.2?topic=s-strings-command)
