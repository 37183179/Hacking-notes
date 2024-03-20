
## Goal

Can you convert the number 42 (base 10) to binary (base 2)?
## Solution

```bash
greygods-picoctf@webshell:~$ echo "obase=2;42" | bc
101010
greygods-picoctf@webshell:~$
```

## Notes

- `echo`: Prints the following string to the standard output.
- `"obase=2;`: Sets the output base to 2 (binary) within `bc`.
- `42`: The decimal value to be converted.
- `| bc`: Pipes the output of `echo` to the `bc` calculator for evaluation.
## References
[Obase and bc commands:](https://www.networkworld.com/article/971677/converting-numbers-on-linux-among-decimal-hexadecimal-octal-and-binary.html)
