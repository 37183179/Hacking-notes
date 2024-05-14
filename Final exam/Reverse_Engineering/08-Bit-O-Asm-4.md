## Goal
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).
## Hints
+ Not everything in this disassembly listing is optimal.
## Solution
disassembler-dump0_d content:
````
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret

````

1. `<+0>: endbr64`: This instruction is used for control flow enforcement in modern x86-64 processors. It indicates the end of a 64-bit code sequence and helps prevent certain types of control flow hijacking attacks.
    
2. `<+4>: push rbp`: This instruction pushes the current value of the base pointer (`rbp`) onto the stack. It's a standard procedure at the beginning of a function to save the current state of the base pointer before modifying it.
    
3. `<+5>: mov rbp,rsp`: This instruction moves the value of the stack pointer (`rsp`) into the base pointer (`rbp`). It establishes a new stack frame for the current function by setting `rbp` to the current position of the stack.
    
4. `<+8>: mov DWORD PTR [rbp-0x14],edi`: This instruction moves the value of the `edi` register (usually containing function arguments) into the memory location `[rbp-0x14]`, likely representing the storage of a function parameter.
    
5. `<+11>: mov QWORD PTR [rbp-0x20],rsi`: Similar to the previous line, this instruction moves the value of the `rsi` register (another register often used for function arguments) into the memory location `[rbp-0x20]`, presumably storing another function parameter.
    
6. `<+15>: mov DWORD PTR [rbp-0x4],0x9fe1a`: This instruction moves the hexadecimal value `0x9fe1a` into the memory location `[rbp-0x4]`. It's storing a constant value in memory.
    
7. `<+22>: cmp DWORD PTR [rbp-0x4],0x2710`: This instruction compares the value stored in the memory location `[rbp-0x4]` with the hexadecimal value `0x2710` (10000 in decimal).
    
8. `<+29>: jle 0x55555555514e <main+37>`: This is a conditional jump instruction. It jumps to the memory address `0x55555555514e`, corresponding to `<main+37>`, if the previous comparison (`cmp`) resulted in a "less than or equal" condition (`jle`).
    
9. `<+31>: sub DWORD PTR [rbp-0x4],0x65`: This instruction subtracts the hexadecimal value `0x65` (101 in decimal) from the value stored in the memory location `[rbp-0x4]`.
    
10. `<+35>: jmp 0x555555555152 <main+41>`: This is an unconditional jump instruction. It jumps to the memory address `0x555555555152`, corresponding to `<main+41>`.
    
11. `<+37>: add DWORD PTR [rbp-0x4],0x65`: This instruction adds the hexadecimal value `0x65` (101 in decimal) to the value stored in the memory location `[rbp-0x4]`.
    
12. `<+41>: mov eax,DWORD PTR [rbp-0x4]`: This instruction moves the value stored in the memory location `[rbp-0x4]` into the `eax` register. It's likely preparing a value to be returned from the function.
    
13. `<+44>: pop rbp`: This instruction pops the value from the stack into the base pointer (`rbp`), restoring the previous state of the base pointer before the function call.
    
14. `<+45>: ret`: This instruction signifies the end of the function. It returns control to the calling function and pops the return address from the stack, effectively returning execution to the caller.
0x2710 > 0x9fe1a
eax = 0x9fe1a - 0x65
eax = 0x9FDB5 = 654773
## Notes

## References