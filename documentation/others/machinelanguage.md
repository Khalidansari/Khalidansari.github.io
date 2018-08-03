---
layout: default
---
# Machine Language

A Processor will have limited number of instruction sets which processor will take in binary form. This basic binary form is machine language. Machine language and Assembly language are nearly at the same level as the difference is that in machine language the instruction set is in binary form while in assembly language it is in label form.

Instruction Set:
1. Arithmetic - 
        ADD R2, R3         : Assign the value of register R2 + value of register R3 to R2
        ADD R2, x            : Assign value of register R2 + value of x to register R2
        ADD x, R2            : Not valid as we can assign the value to some register only
        AND R4, R5, R2   : Assign result of bitwise and of R5 & R2 to register R4
        SUBR4 x               : Assign the value of register R4 - x to register R4
        ADD x                   : add the value of x to a special register called “accumulator” 

2. Memory Access - 
        Direct addressing         : LOAD R1, 67     - This will load the value at memory 67 to register R1
        Immediate addressing  : LOADI R1, 67     - This will load the value 67 to register R1
        Indirect addressing       : LOAD* R1, R2   - Take the value of R1. Treat this as memory address and fetch the value from this address. The value here is address to a different location.
                                                                           Get the value from there and push it to R1
3. Flow - 
        Repetition                     : Jump backward
        Conditional execution   : Jump forward
        Subroutine Calling        : Jump to a separate code segment

        To support the above there are two instruction sets provided - conditional jump and unconditional jump.

        Unconditional jump       : JMP foo              - Jump to label fooo unconditionally

        Conditional jump           : JGE R1, foo       - jump if R1>=0
                                             : JZR foo              - jump if result of previous command was 0