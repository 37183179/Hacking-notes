## Goal
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).s
## Hints
+ Not everything in this disassembly listing is optimal.
## Solution
disassembler-dump0_c content:
````
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
````

1. `<+0>:     endbr64`: This instruction is used for control flow enforcement in modern x86-64 processors. It indicates the end of a 64-bit code sequence and helps prevent certain types of control flow hijacking attacks.

2. `<+4>:     push   rbp`: This instruction pushes the value of the base pointer register (`rbp`) onto the stack. This is commonly done at the beginning of a function to save the caller's base pointer.

3. `<+5>:     mov    rbp,rsp`: This instruction moves the value of the stack pointer (`rsp`) into the base pointer register (`rbp`). This sets up the base pointer for the current function, commonly used for accessing function arguments and local variables.

4. `<+8>:     mov    DWORD PTR [rbp-0x14],edi`: This instruction moves the value of the `edi` register (the first function argument in the x86 calling convention) into the memory location at `[rbp-0x14]`, which likely represents a local variable in the function.

5. `<+11>:    mov    QWORD PTR [rbp-0x20],rsi`: Similar to the previous line, this instruction moves the value of the `rsi` register (the second function argument) into the memory location at `[rbp-0x20]`, which could be another local variable.

6. `<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a`: This instruction moves the immediate value `0x9fe1a` into the memory location at `[rbp-0xc]`, possibly initializing another local variable.

7. `<+22>:    mov    DWORD PTR [rbp-0x8],0x4`: Similarly, this instruction initializes another local variable with the value `0x4`, storing it at `[rbp-0x8]`.

8. `<+29>:    mov    eax,DWORD PTR [rbp-0xc]`: This instruction moves the value stored at `[rbp-0xc]` into the `eax` register.

9. `<+32>:    imul   eax,DWORD PTR [rbp-0x8]`: This instruction multiplies the value in the `eax` register by the value stored at `[rbp-0x8]`, using signed multiplication.

10. `<+36>:    add    eax,0x1f5`: This instruction adds the immediate value `0x1f5` to the value in the `eax` register.

11. `<+41>:    mov    DWORD PTR [rbp-0x4],eax`: This instruction moves the result (stored in `eax`) into the memory location at `[rbp-0x4]`, possibly storing the function's return value.

12. `<+44>:    mov    eax,DWORD PTR [rbp-0x4]`: This instruction moves the value stored at `[rbp-0x4]` (possibly the function's return value) into the `eax` register.

13. `<+47>:    pop    rbp`: This instruction pops the value of the base pointer (`rbp`) from the stack, restoring the previous base pointer value.

14. `<+48>:    ret`: This instruction returns control flow to the calling function, using the value in the `eax` register as the return value.
eax = 0x9fe1a x 0x4
eax = 0x27f868 + 0x1f5
eax = 0x27fa5d = 2619997

## Notes

## References