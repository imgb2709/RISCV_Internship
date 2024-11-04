
# Task 3

In this task, we learn more about RISC-V Instruction Set Architecture (ISA) by completing the further sub-tasks:

1. Learn and list about the various RISC-V instruction types.
2. To identify 15 unique RISC V instructions from riscv-objdump code of the chosen application code.
3. To identify and map the exact 32 bit instruction code in the instruction type format for 15 unique instructions.  


## 1. RISC-V ISA
RISC-V instructions like R, I, S, B, U, J has been discussed further.

**R-Type:**

- Here, 'R' stands for Register. Several arithmetic operations are performed using R-Type instructions.
- ADD, SUB, XOR, OR, SLL, SRL, SRA are some of the operations which can be performed here.
- rs1 and rs2 registers are source operands and the result is written into register rd. The funct7 and funct3 fields select the type of operation.
 ```http
 |funct7 (7 bits)|rs2 (5 bits)|rs1 (5 bits)|funct3 (3 bits)|rd (5 bits)|opcode (7 bits)|

```
**I-Type:**

- Here, 'I' stands for Instruction. 
- ADDI, SLTI, XORI, ORI are some of the operations which can be performed here.
- rs1 and rd registers are source and destination operands. The funct3 field selects the type of operation.
 ```http
 |imm (12 bits)|rs1 (5 bits)|funct3 (3 bits)|rd (5 bits)|opcode (7 bits)|

```
**S-Type:**

- Here, 'S' stands for Store. 
- Used to store a value in register and memory.
- rs2 and rs1 registers are source and base.
 ```http
 |imm[11:5] (7 bits)|rs2 (5 bits)|rs1 (5 bits)|funct3 (3 bits)|imm[4:0] (5 bits)|opcode (7 bits)|

```
**B-Type:**

- Here, 'B' stands for Branch. 
- BEQ, BNE, BLT, BGE are some of the operations which can be performed here.
- rs1 and rs2 registers are source operands. The funct3 field selects the type of operation.
 ```http
 |imm[12|10:5] (7 bits)|rs2 (5 bits)|rs1 (5 bits)|funct3 (3 bits)|imm[4:1|11] (5 bits)|opcode (7 bits)|

```

**U-Type:**

- Here, 'U' stands for Upper Immediate type. 
- LUI, AUIPC are some of the operations which can be performed here.
- rd is the destination register here.
 ```http
 |imm (20 bits)|rd (5 bits)|opcode (7 bits)|

```

**J-Type:**

- Here, 'J' stands for Jump. 
- JAL, JALR are some of the operations which can be performed here.
- rs1 and rd registers are source and destination operands. The funct3 field selects the type of operation.
 ```http
|[20] |imm[10:1] (10 bits)|[11]|imm[19:12] (8 bits)|rd (5 bits)|opcode (7 bits)|

```



## 2. Identifying 15 unique RISC-V instructions:
The assembly code of the application Up-Down counter is analysed in riscv-objdump format.

- addi 
- sd
- li
- lui 
- sraw
- andi
- addiw
- jal
- bne
- beq
- j
- bge
- sub 
- auipc
- beqz
## 3. Mapping instructions with 32 bit instruction code

1. addi:
- I Type instruction. 
- Opcode: fc010113 - 11111100000000010000000100010011
- imm[11:0] - 111111000000. rs1 - 00010. func3 - 000. rd - 00010. opcode - 0010011.

2. sd:
- S Type instruction.
- Opcode: 02913423 - 00000010100100010011010000100011
- imm[11:5] - 0000001. rs2 - 01001. rs1 - 00010. func3 - 011. imm[4:0] - 01000. opcode - 0100011.

3. li:
- I Type instruction.
- Opcode: 00100993 - 00000000000100000000100110010011
- imm[11:0] - 000000000001. rs1 - 00000. func3 - 000. rd - 10011. opcode - 0010011.  

4. lui:
- U Type instruction.
- Opcode: 00021ab7 - 00000000000100000000100110010011
- imm[31:12] - 00000000000100000000. rd - 10011. opcode - 0010011.

5. sraw:
- R Type instruction.
- Opcode: 4084d5bb - 01000000100001001101010110111011
- func7 - 0100000. rs2 - 01000. rs1 - 01001. func3 - 101. rd - 01011. opcode - 0111011.

6. andi:
- I Type instruction.
- Opcode: 0015f593 - 01000000100001001101010110111011
- imm[11:0] - 010000001000. rs1 - 01001. func3 - 101. rd - 01011. opcode -  0111011.

7. addiw:
- I Type instruction.
- Opcode: fff4041b - 11111111111101000000010000011011
- imm[11:0] - 111111111111. rs1 - 01000. func3 - 000. rd - 01000. opcode -  0011011.

8. jal:
- J Type instruction.
- Opcode: 3c8000ef - 00111100100000000000000011101111
- imm[20] - 0. imm[10:1] - 011110010. imm[11] - 0. imm[19:12] - 00000000. rd - 00001. opcode - 1101111.

9. bne
- B Type instruction.
- Opcode: ff2416e3 - 11111111001001000001011011100011
- imm[12] - 1. imm[10:5] - 111111. rs2 - 10010. rs1 - 01000. func3 - 001. imm[4:1] - 0110. imm[11] - 1. opcode - 1100011.

10. beq
- B Type instruction.
- Opcode: 01498c63 - 00000001010010011000110001100011
- imm[12] - 0. imm[10:5] - 000000. rs2 - 10100. rs1 - 10011. func3 - 000. imm[4:1] - 1100. imm[11] - 0. opcode - 1100011.

11. bge 
- B Type instruction.
- Opcode: fc9b50e3 - 11111100100110110101000011100011
- imm[12] - 1. imm[10:5] - 11111. rs2 - 00100. rs1 - 11011. func3 - 010. imm[4:1] - 1000. imm[11] - 1. opcode - 1100011.

12. sub 
- R Type instruction.
- Opcode: 40a60633 - 01000000101001100000011000110011
- func7 - 0100000. rs2 - 01010. rs1 - 01100. func3 - 000. rd - 01100. opcode - 0110011.

13. auipc
- U Type instruction.
- Opcode: 00014617 - 00000000000000010100011000010111
- imm[31:12] - 00000000000000010100. rd - 01100. opcode - 0010111.

14. beqz
- B Type instruction.
- Opcode: 00078863 - 00000000000001111000100001100011
- imm[12] - 0. imm[10:5] - 000000. rs2 - 00000. rs1 - 01111. func3 - 000. imm[4:1] - 1000. imm[11] - 0. opcode - 1100011.

15. j 
- J Type instruction.
- Opcode: fc9ff06f - 11111100100111111111000001101111
- imm[20] - 1. imm[10:1] - 111110010. imm[11] - 0. imm[19:12] - 11111111. rd - 10000. opcode - 1101111.



