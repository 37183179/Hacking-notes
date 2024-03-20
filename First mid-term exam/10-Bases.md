## Goal

What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
## Solution

```bash
greygods-picoctf@webshell:~$: echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
l3arn_th3_r0p35
greygods-picoctf@webshell:~$:
````


## Notes
- `base64`: This is another built-in shell command, but it requires the `-d` flag in this case.
- `-d`: This flag tells the `base64` command to **decode** the input data from Base64 format back to its original form.

## References
[Base64 command: ](https://ioflood.com/blog/base64-linux-command/)