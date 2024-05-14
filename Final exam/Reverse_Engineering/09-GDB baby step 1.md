## Goal
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).
## Hints
+ gdb is a very good debugger to use for this problem and many others!
+ `main` is actually a recognized symbol that can be used with gdb commands.

## Solution

```bash
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 1]
└─$ wget https://artifacts.picoctf.net/c/512/debugger0_a                                       
--2024-05-14 11:13:28--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.60, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16472 (16K) [application/octet-stream]
Saving to: ‘debugger0_a’

debugger0_a               100%[==================================>]  16.09K  --.-KB/s    in 0.003s  

2024-05-14 11:13:34 (5.78 MB/s) - ‘debugger0_a’ saved [16472/16472]

                                                                                                     
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 1]
└─$ file debugger0_a   
debugger0_a: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=15a10290db2cd2ec0c123cf80b88ed7d7f5cf9ff, for GNU/Linux 3.2.0, not stripped
                                                                                                     
┌──(kali㉿kali)-[~/picoCTF/Final_exam/GDB baby step 1]
└─$ gdb debugger0_a 
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

--Type <RET> for more, q to quit, c to continue without paging--
For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) disassemble main
Dump of assembler code for function main:                                                                                                                                                                                                   
   0x0000000000001129 <+0>:     endbr64                                                                                                                                                                                                     
   0x000000000000112d <+4>:     push   %rbp                                                                                                                                                                                                 
   0x000000000000112e <+5>:     mov    %rsp,%rbp                                                                                                                                                                                            
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)                                                                                                                                                                                      
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)                                                                                                                                                                                     
   0x0000000000001138 <+15>:    mov    $0x86342,%eax                                                                                                                                                                                        
   0x000000000000113d <+20>:    pop    %rbp                                                                                                                                                                                                 
   0x000000000000113e <+21>:    ret                                                                                                                                                                                                         
End of assembler dump.                                                                                                                                                                                                                      
(gdb)                     
````

1. `0x0000000000001129 <+0>:     endbr64`: This instruction is `endbr64`, indicating the end of a 64-bit code sequence. It's a control flow enforcement mechanism that helps prevent certain types of control flow hijacking attacks.

2. `0x000000000000112d <+4>:     push   %rbp`: This line pushes the value of the base pointer register (`rbp`) onto the stack. It's a common practice at the beginning of a function to save the current state of `rbp`.

3. `0x000000000000112e <+5>:     mov    %rsp,%rbp`: This instruction moves the value of the stack pointer register (`rsp`) into the base pointer register (`rbp`). It establishes a new stack frame by setting `rbp` to the current position of the stack.

4. `0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)`: This line moves the value of the `edi` register (typically used for function arguments) into the memory location `[rbp-0x4]`, which likely represents a function parameter.

5. `0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)`: Similarly to the previous line, this instruction moves the value of the `rsi` register (another register used for function arguments) into the memory location `[rbp-0x10]`, likely representing another function parameter.

6. `0x0000000000001138 <+15>:    mov    $0x86342,%eax`: This instruction moves the hexadecimal value `0x86342` into the `eax` register. It's likely preparing a value to be returned from the function.

7. `0x000000000000113d <+20>:    pop    %rbp`: This line pops the value from the stack into the base pointer register (`rbp`), restoring the previous state of the base pointer before the function call.

8. `0x000000000000113e <+21>:    ret`: Finally, this instruction signifies the end of the function. It returns control to the calling function and pops the return address from the stack, effectively returning execution to the caller.

Finally in register eax is stored the hexadecimal value $0x86342
## Notes

## References