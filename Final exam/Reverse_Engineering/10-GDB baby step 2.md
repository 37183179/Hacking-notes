## Goal
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).
## Hints
+ You could calculate `eax` yourself, or you could set a breakpoint for after the calculcation and inspect `eax` to let the program do the heavy-lifting for you.

## Solution

```bash
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 2]
└─$ wget https://artifacts.picoctf.net/c/520/debugger0_b
--2024-05-14 11:22:45--  https://artifacts.picoctf.net/c/520/debugger0_b
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.3, 3.161.225.60, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: ‘debugger0_b’

debugger0_b                                                100%[========================================================================================================================================>]  15.92K  --.-KB/s    in 0s      

2024-05-14 11:22:55 (217 MB/s) - ‘debugger0_b’ saved [16304/16304]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 2]
└─$ file debugger0_b 
debugger0_b: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=95b0203be2982e75dbc01d1cc25b1309f7aec5f7, for GNU/Linux 3.2.0, not stripped
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 2]
└─$ sudo chmod +x debugger0_b              
[sudo] password for kali: 
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 2]
└─$ gdb --args ./debugger0_b
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./debugger0_b...
(No debugging symbols found in ./debugger0_b)
(gdb)  disassemble main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
   0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x1e0da,-0x4(%rbp)
   0x000000000040111c <+22>:    movl   $0x25f,-0xc(%rbp)
   0x0000000000401123 <+29>:    movl   $0x0,-0x8(%rbp)
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    -0x8(%rbp),%eax
   0x000000000040112f <+41>:    add    %eax,-0x4(%rbp)
   0x0000000000401132 <+44>:    addl   $0x1,-0x8(%rbp)
   0x0000000000401136 <+48>:    mov    -0x8(%rbp),%eax
   0x0000000000401139 <+51>:    cmp    -0xc(%rbp),%eax
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    -0x4(%rbp),%eax
   0x0000000000401141 <+59>:    pop    %rbp
   0x0000000000401142 <+60>:    ret
End of assembler dump.
(gdb) b *(main+59)
Breakpoint 1 at 0x401141
(gdb) run
Starting program: /home/kali/picoCTF/Final_exam/GDB baby step 2/debugger0_b 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x0000000000401141 in main ()
(gdb) print $eax
$1 = 307019
(gdb) 
````

1. `wget https://artifacts.picoctf.net/c/520/debugger0_b`: This command downloads the `debugger0_b` binary from the specified URL.

2. `file debugger0_b`: This command checks the type of the `debugger0_b` binary. In this case, it identifies it as an ELF 64-bit executable for x86-64 architecture.

3. `sudo chmod +x debugger0_b`: This command grants execute permission to the `debugger0_b` binary, allowing you to run it.

4. `gdb --args ./debugger0_b`: This command starts the GNU Debugger (GDB) and loads the `debugger0_b` binary with command-line arguments passed to it. Here, you're preparing to debug the binary.

5. `disassemble main`: This command disassembles the `main` function of the binary, showing the assembly instructions. You're inspecting the assembly code to understand the program's logic.

6. `b *(main+59)`: This command sets a breakpoint at the address corresponding to the 59th instruction within the `main` function.

7. `run`: This command starts the execution of the binary within GDB. It will pause at the breakpoint set previously.

8. `print $eax`: This command prints the value of the `eax` register, which likely contains the return value of the `main` function. In this case, it shows `307019`.
## Notes

## References