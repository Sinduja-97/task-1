TASK-2
C PROGRAM FOR 7 SEGMENT DISPLAY

![7 SEGMENT C CODE ](https://github.com/Sinduja-97/task-1/assets/171498289/fb15afae-6f37-42e9-b2a1-c1c0ad882747)
THE BELOW IMAGE SHOWS THE OUTPUT

![OUTPUT](https://github.com/Sinduja-97/task-1/assets/171498289/13f5ae00-b0d2-4c2a-a0e3-1e9f9250fb54)

TASK-3 
SPIKE SIMULATION AND OBSERVATION WITH -O1 AND -OFAST

![CODE](https://github.com/Sinduja-97/task-1/assets/171498289/8f973f39-e373-4b3d-8aad-9cc40c67b540)

OUTPUT FROM RISC-V GCC AND C LANGUAGE VCC:

![RISC ](https://github.com/Sinduja-97/task-1/assets/171498289/46c7a5f8-1a4e-41c6-ad29-47dac10dc303)

OUTPUTS IN O1 MODE:

![O1](https://github.com/Sinduja-97/task-1/assets/171498289/f91f4cc4-21f4-4dfb-9c81-06fd48d7bc07)
![O1 MODE](https://github.com/Sinduja-97/task-1/assets/171498289/e5befbf9-5f38-451b-89ea-2aa59e87849f)

OFAST MODE:

![OFAST](https://github.com/Sinduja-97/task-1/assets/171498289/496cdc8b-e0d0-495a-af61-9d4b683a6242)
![OFASTT](https://github.com/Sinduja-97/task-1/assets/171498289/334d2f88-4e2f-4fa3-a7ff-557195423b33)


TASK-4
RISC-V Instructions: Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions
![riscv](https://github.com/Sinduja-97/task-1/assets/171498289/5ee76b0d-31a1-4e5f-a2b0-9e2765538adf)
![summary](https://github.com/Sinduja-97/task-1/assets/171498289/928ac971-ed32-476a-a96f-6b10fba0a763)

R-type Instruction
R-type is an operation without immediate. The immediate is the number that exists as an integer in the instructions.
The 7 bits from 0 to 6 are opcode (operation code), used to identify the type of instruction.
Bits 7 to 11 are the index of the rd register.rs1 and rs2 arefunc7(7-bit), combined with opcode and fun3, this field describes what operation to perform. called source registers. In most cases, instructions need to read the values of the two source registers for operations. The index of rs1 is in bits 15-19, and the index of rs2 is in bits 20-24.
This instruction requires opcode plus funct3, and sometimes funct7 together to determine the type of operation that this instruction allows the CPU to perform.
![risccc](https://github.com/Sinduja-97/task-1/assets/171498289/46bc187b-4cbd-47eb-bbef-1a955d8e9eee)

I-type Instruction
The upper 12 bits of I-type is an immediate number. The opcode is different from other instruction formats because the corresponding specific operations are different, and other parts are very similar to R-type.
![i ins](https://github.com/Sinduja-97/task-1/assets/171498289/ae3692db-0989-4c48-ae15-afa8fc355aa5)

S-type： The characteristic of S-type instruction is that there is no rd register. In this type of instruction, the immediate is divided into two parts, the first part is in bit11-5, and the second part is in bit4-0. The 5 bits of the immediate 4-0 occupy the position of rd in other instruction formats, and 5-11 occupy the position of funct7. Explain that the command format does not need to write back. That is, read the two values from the two registers and perform the operation together with the immediate, and write the result to the register after the operation is over.

 ![iii](https://github.com/Sinduja-97/task-1/assets/171498289/f9661b3c-0f98-439a-85be-365ae21d7154)

 U-Type: A 20-bit immediate is provided in the U-type instruction. The final operation result is related to the 20-bit immediate, and the result is written back to the rd register. The opcode determines the type of operation. There are no funct3, rs1, rs2, and funct7 in U-type. This type of instruction structure is very simple.

![uu](https://github.com/Sinduja-97/task-1/assets/171498289/d018e315-adc8-4ba3-b1f8-bfa1b1771a0b)

B-Type: B-type instructions are mainly used as branch instructions, but they are conditional Branch. It means to decide whether to jump or not need to depend on whether the condition is valid. The B-type machine code structure is shown in Figure 2-1. The instruction does not include rd register and funct7, but contains rs1, rs2, funct3 and immediate. The immediate is divided into two areas. The encoding of B-type instruction immediate is out of order. The reason is not described in detail here. There is a specific article on the official site explaining why it is out of order. In short, it has been verified that the effect on CPU operation function when the immediate number sequence is in this order is very well. But the immediate is disrupted, so it will be decoded when the CPU executes in the future. After decoding, the CPU needs to restore the disrupted immediate in order. For example, when the CPU gets a B-type instruction, the immediate in it is scrambled, and the CPU needs to arrange the immediate in the order of 12-1 to restore the immediate.

![bb](https://github.com/Sinduja-97/task-1/assets/171498289/e25ee2ff-b9ae-4f89-aade-4efdf8ab181b)

J-Type: The format of this instruction is very similar to U-type, it only have Rd register and immediate and opcode. At the same time, the immediate of J-type is also disrupted. That means that the CPU must first put the immediate numbers together to restore the original immediate numbers when decoding.


![jj](https://github.com/Sinduja-97/task-1/assets/171498289/f7fdc0b3-bee3-4cff-9891-453960791add)

32-bit pattern for the given instructions:

1 -> ADD r1, r2, r3 => 32 bit instruction: 0000000_00011_00010_000_00001_0110011

2 -> SUB r3, r1, r2 => 32 bit instruction: 0100000_00010_00001_000_00011_0110011

3 -> AND r2, r1, r3 => 32 bit instruction: 0000000_00011_00001_111_00010_0110011

4 -> OR r8, r2, r5 => 32 bit instruction: 0000000_00101_00010_110_01000_0110011

5 -> XOR r8, r1, r4 => 32 bit instruction: 0000000_00100_00001_100_01000_0110011

6 -> SLT r10, r2, r4 => 32 bit instruction: 0000000_00100_00010_010_01010_0110011

7 -> ADDI r12, r3, 5 => 32 bit instruction: 000000001001_00011_000_01100_0010011

8 -> SW r3, r1, 4 => 32 bit instruction: 0000000_00011_00001_010_00100_0100011

9 -> SRL r16, r11, r2 => 32 bit instruction: 0000000_00010_01011_101_10000_0110011

10 -> BNE r0, r1, 20 => 32 bit instruction: 0000001_00001_00000_001_01000_1100011

11 -> BEQ r0, r0, 15 => 32 bit instruction: 0000000_00000_00000_000_11110_1100011

12 -> LW r13, r11, 2 => 32 bit instruction: 000000000010_01011_010_01101_0000011

13 -> SLL r15, r11, r2 => 32 bit instruction: 0000000_00010_01011_001_01111_0110011












