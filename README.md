# Samsung-RISCV
The program focuses on the RISC-V architecture and leverages open-source tools to educate participants about VLSI chip design and RISC-V. The internship is led by Kunal Ghosh Sir.
               
# Basic Details

Name: Vidyashree P

College: Vidyavardhaka College of Engineering

Email ID: vidyaachar35@gmail.com

GitHub Profile: [Vidyashree0P](https://github.com/Vidyashree0P)

LinkedIN Profile:[Vidya Shree.P](https://www.linkedin.com/in/vidya-shree-p-87ba6425a/)


----------------------------------------------------------------------------------------------------------------

<details>
 <summary><b>  
Task 1:</b> Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler</summary>

## C Language based LAB
## C and RISC-V Based Labs

This repository demonstrates the processes involved in compiling C programs and generating assembly code using both a standard GCC compiler and a RISC-V GCC compiler. It includes comprehensive steps and explanations to guide users through each stage of the compilation and debugging workflow.

### C Language-Based Lab

#### Steps to Compile a .c File on Your Machine:

1. Open the bash terminal and navigate to the directory where you want to create your file.
2. Use the following command to create and edit a new .c file:
   ```sh
   leafpad sum1ton.c


#### Steps to Compile a .c File on our Machine:
 ```sh
 gcc sum1ton.c
 ./a.out
```

 
 ## Compilation and execution complete.
 
![ccode](https://github.com/user-attachments/assets/451c7c72-8325-47ee-8570-fde44a00eba9)


)
### RISC-V Based Lab

#### Steps to Compile Using RISC-V GCC Compiler:
// Ensure the RISC-V GCC compiler is installed and accessible on your system. 
// Verify the .c file contents using the cat command:
   ```sh
   cat sum1ton.c


// Compile the C program for RISC-V architecture using 01 option:
 ```sh
riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
// Disassemble the object file to view its assembly code using:
 ```sh
riscv64-unknown-elf-objdump -d sum1ton.o
```
//minimize the assembly by using following code:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
 a)we extract main function's assembly code by using:
   ```sh
/main
```
// Use /main in the terminal to locate the main function in the assembly output.
![O1](https://github.com/user-attachments/assets/f06511eb-04c9-4820-8d11-65a84a7bc2a5)

)

//Compile the C program for RISC-V architecture using ofast option:
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
commans: ![terminal](https://github.com/user-attachments/assets/7578dd03-f928-4103-8566-d8a3a48669cb)

follow the steps as prevoious
//Use /main in the terminal to locate the main function in the assembly output.
![4](https://github.com/user-attachments/assets/a8cf86d0-0954-4ad8-a923-ffe519db5115)
)


### Explanation of Key Commands and Options: 
1. -mabi=lp64: Specifies the Application Binary Interface (ABI) for 64-bit integers, pointers, and long data types, suitable for 64-bit RISC-V architecture.

2. -march=rv64i: Indicates the 64-bit RISC-V base integer instruction set architecture.

3. -O1: Enables basic optimization for better performance without significantly increasing compilation time.

4. -Ofast: Optimize the code aggressively for the best possible speed.

5. riscv64-unknown-elf-objdump: A tool for disassembling RISC-V binaries to examine the code structure and debug it effectively.
   
</details>

----------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task2</b>:SPIKE Simulation and Compile the C program using RISC-V GCC/SPIKE with the above optimization options.  </summary>

# SPIKE SIMULATION
![spike(factn)](https://github.com/user-attachments/assets/19dae9c1-7e5a-4911-bce8-2c01c19cf2b3)

## Steps to Compile and run ./a.out thing in riscv
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
```sh
spike pk sum1ton.c
```
## Steps to Debug RISC-V architecture
```sh
spike -d pk sum1ton.c
```
//debuger will open as shown above 

//Run untill the starting address of main using the command
```sh
untill pc 0 100b0
//previous value of register
reg 0 a2
//do enter and after the update value of a2 is
reg 0 a2
```
// addi sp,sp,-16 means the address of sp is subtracted by 16 to check that
```sh
until pc 0 100b8
reg 0 sp
q//to quit
```


### The values store in the 64 bits as shown below for the command lui (Load Upper Immediate) "lui a2, 0x376"
![WhatsApp Image 2025-01-12 at 23 01 01_08654899](https://github.com/user-attachments/assets/15ceeffb-e9f9-45c9-874c-455d212d01ec)

### Explanation of Key Commands:
 1. spike: This is the RISC-V ISA simulator (an instruction set simulator). Spike is commonly used for simulating and testing RISC-V programs. It emulates a RISC-V processor, running programs in a controlled environment.
 2. -d: This flag is for debugging mode. It tells Spike to run in debug mode, allowing step-by-step execution, inspecting registers, memory, etc. Useful for identifying issues and analyzing program behavior.
 3. pk: This refers to the proxy kernel, which acts as a lightweight operating system for RISC-V. The proxy kernel handles system calls and facilitates program execution in the simulated environment.
 4. addi (Add Immediate): addi sp,sp,-16
    Adds an immediate value (-16) to the value in register sp and stores the result in register sp.
 5. lui (Load Upper Immediate): lui a2, 0x31
    The value in 31 is shifted left by 12 bits and stored in the upper portion of the destination register.   

<details>
<summary><b>Compile the C program using RISC-V GCC/SPIKE with the above optimization options.</b></summary>

## C compilation of Factorial of N numbers
![factn c](https://github.com/user-attachments/assets/2548dc42-a9ff-4c54-8233-a2870c4d1a2f)

## riscv compilation of factorial of N numbers
![riscv(factn)](https://github.com/user-attachments/assets/d9402407-e666-4008-920d-7d25acc906e7)

//Compile the C program for RISC-V architecture using ofast option:
![ofast(factn)](https://github.com/user-attachments/assets/6ceaedd0-dd52-42cb-b707-7bed5298d11a)

## Spike Simulation
![spike(factn)](https://github.com/user-attachments/assets/0eb8bc44-7034-466b-aa79-14395af7b2f6)

</details>
</details>

----------------------------------------------------------------------------------------------------------------
<details><summary><b>
Task 3: </b>undestanding the R,I,S,B,U and J Instructions</summary>


  # Introduction to Instruction of RISC-V64
In the realm of computer architecture, RISC-V stands out as a highly flexible and streamlined instruction set architecture (ISA). Within the RISC-V RV64G (64-bit) architecture, various instruction types have been ingeniously designed to optimize different computational tasks. These instruction types—including R-Type, I-Type, S-Type, B-Type, U-Type, and J-Type—each serve unique functions, from arithmetic and logical operations to memory storage and conditional branching. Understanding these instructions provides a key to unleashing the full potential of RISC-V’s modular and efficient architecture.

## Types of RISC-V Instructions
**1. R-Type Instructions:** These are Register-Register operations. They perform arithmetic and logical operations.

**2. I-Type Instructions:** Used for Immediate values typically in data transfer and arithmetic

**3. S-Type Instructions:** Store operations that utilize both a base register and an immediate offset.

**4. U-Type Instructions:** Used for Upper immediate instructions, which load large constants.

**5. B-Type Instructions:** Branch operations that allow conditional jumps.

**6. J-Type Instructions:** Jump instructions for long-range jumps.

```sh
//R-Type Instructions
opcode | rd | funct3 | rs1 | rs2 | funct7

//I-Type Instructions
opcode | rd | funct3 | rs1 | imm[11:0]

//S-Type Instructions
opcode | imm[11:5] | funct3 | rs1 | rs2 | imm[4:0]

//U-Type Instructions
opcode | rd | imm[31:12]

//B-Type Instructions
opcode | imm[12|10:5] | funct3 | rs1 | rs2 | imm[4:1|11]

//J-Type Instructions
opcode | rd | imm[20|10:1|11|19:12]
```

<details>
<summary><b>R-type Instructions</b>
  In the RISC-V architecture, the R-type (Register) instruction format is used for arithmetic and logical operations that involve registers.</summary> 
  
  Let's break down the R-type instruction format for the riscv64 (64-bit RISC-V architecture):

   ## R-type Instruction Format
 The R-type instruction format follows a specific structure consisting of six fields:
1. opcode (7 bits): Specifies the operation to be performed.
2. rd (5 bits): The destination register where the result of the operation will be stored.
3 funct3 (3 bits): Used in combination with the opcode and funct7 fields to define the exact operation.
4. rs1 (5 bits): The first source register operand.
5. rs2 (5 bits): The second source register operand.
6. funct7 (7 bits): Further refines the operation, often used to differentiate between variations of an operation.

  ### Structure
  ```sh
| funct7  | rs2  | rs1  | funct3 | rd   | opcode |
| 7 bits  | 5 bits | 5 bits | 3 bits | 5 bits | 7 bits |
```
### Example (ADD Instruction)
    add x5, x1, x2
### Instruction Breakdown
opcode (7 bits): 0110011 – Identifies the instruction as an R-type.

rd (5 bits): 00101 – Destination register x5 (in binary, register 5 is 00101).

funct3 (3 bits): 000 – Specifies the add operation.

rs1 (5 bits): 00001 – Source register x1 (in binary, register 1 is 00001).

rs2 (5 bits): 00010 – Source register x2 (in binary, register 2 is 00010).

funct7 (7 bits): 0000000 – Defines the basic add operation.
#### Detailed Bit Representation
Here's how each part fits into the 32-bit instruction format:
```sh    
| 31:25 (funct7) | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (rd) |  6:0  (opcode) |
| 0000000        | 00010       | 00001       | 000            | 00101    | 0110011       |
// The hex representation of this add x5, x1, x2 instruction is
0x002080b3
```
</details>

<details><summary><b>I-type Instruction</b>
In the RISC-V architecture, the I-type (Immediate) instruction format is used for operations involving immediate values (constants) along with registers. This format is often used for load instructions, arithmetic operations with immediate values, and other instructions that require a constant operand.</summary>

## I-type Instruction Format
Similar to the R-type, the I-type format consists of six fields, structured slightly differently to accommodate the immediate value:

opcode (7 bits): Specifies the operation to be performed.

rd (5 bits): The destination register where the result of the operation will be stored.

funct3 (3 bits): Used in combination with the opcode to define the exact operation.

rs1 (5 bits): The source register operand.

imm (12 bits): The immediate value (constant).

### Structure
Here's a breakdown of the bit fields:
```sh
| imm[11:0]     | rs1     | funct3 | rd      | opcode  |
| 12 bits       | 5 bits  | 3 bits | 5 bits  | 7 bits  |

```

### Example (ADDI Instruction)
For instance, an ADDI (add immediate) instruction in RISC-V might look like this:
#### Instruction Breakdown
opcode (7 bits): 0010011 – Identifies this as an I-type immediate instruction.

rd (5 bits): 00101 – The destination register x5 (in binary, register 5 is 00101).

funct3 (3 bits): 000 – Indicates add immediate operation.

rs1 (5 bits): 00001 – The source register x1 (in binary, register 1 is 00001).

imm (12 bits): 000000000010 – The immediate value 10 (in binary, 10 is 000000000010).
#### Detailed Bit Representation
```sh
| 31:20 (imm[11:0]) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (rd) | 6:0 (opcode) |
| 000000000010      | 00001       | 000            | 00101    | 0010011      |
// hex representation
0x00208113
```
</details>

<details><summary><b> S-Type Instruction</b>
The S-type (Store) instruction format in the RISC-V architecture is used for store operations. These instructions move data from a register to memory, using an immediate value as an offset to calculate the address.</summary>
  
## S-type Instruction Format
The S-type format consists of six fields:

opcode (7 bits): Specifies the operation.

imm[4:0] (5 bits): Immediate value (least significant 5 bits).

funct3 (3 bits): Specifies the exact operation.

rs1 (5 bits): Source register (base address).

rs2 (5 bits): Source register (value to be stored).

imm[11:5] (7 bits): Immediate value (most significant 7 bits).

### Structure
Here's the bit layout for an S-type instruction:
```sh
| imm[11:5] | rs2   | rs1   | funct3 | imm[4:0] | opcode  |
| 7 bits    | 5 bits| 5 bits| 3 bits | 5 bits   | 7 bits  |
```

### Example (SW Instruction)
the sw (store word) instruction in RISC-V
sw x5, 10(x1)
This command stores the value from register x5 into the memory address calculated by adding 10 (the immediate) to the base address in x1.

#### Breaking Down the Example:

opcode (7 bits): 0100011 – Indicates an S-type store instruction.

imm[4:0] (5 bits): 01010 – The least significant 5 bits of the immediate value 10.

funct3 (3 bits): 010 – Specifies the store word operation.

rs1 (5 bits): 00001 – The base address register x1.

rs2 (5 bits): 00101 – The source register x5.

imm[11:5] (7 bits): 0000000 – The most significant 7 bits of the immediate value 10.

#### Detailed Bit Representation
```sh
| 31:25 (imm[11:5]) | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:7 (imm[4:0]) | 6:0 (opcode) |
| 0000000           | 00101       | 00001       | 010            | 01010           | 0100011      |
// hex representation
0x0050a023
```
</details>

<details><summary><b>B-Type Instructions:</b> B-type (Branch) instructions in the RISC-V architecture are used for conditional branching. These instructions compare two registers and, based on the result, adjust the program counter to branch to a different part of the program.</summary>

## B-type Instruction Format
The B-type format consists of six key fields:

opcode (7 bits): Specifies the operation.

imm[12|10:5] (7 bits): Immediate value (most and middle significant bits).

rs1 (5 bits): First source register.

rs2 (5 bits): Second source register.

funct3 (3 bits): Specifies the exact branch condition.
   
imm[4:1|11] (5 bits): Immediate value (least significant and sign bit).

#### Structure
```sh
| imm[12] | imm[10:5] | rs2    | rs1    | funct3 | imm[4:1] | imm[11] | opcode  |
|---------|-----------|--------|--------|--------|----------|---------|---------|
| 1 bit   | 6 bits    | 5 bits | 5 bits | 3 bits | 4 bits   | 1 bit   | 7 bits  |

```

#### Example (BEQ Instruction)
Let's consider the beq (branch if equal) instruction:
##### beq x1, x2, label
This instructs the program to branch to a specific label if the values in registers x1 and x2 are equal.
#### Breaking Down the Example:
 opcode (7 bits): 1100011 – Indicates a B-type branch instruction.

imm[12] (1 bit): Most significant bit of the immediate offset.

imm[10:5] (6 bits): Next part of the immediate.

funct3 (3 bits): 000 – Specifies the branch if equal condition.

rs1 (5 bits): 00001 – The first source register x1.

rs2 (5 bits): 00010 – The second source register x2.

imm[4:1] (4 bits): Least significant bits of the immediate.

imm[11] (1 bit): Sign bit of the immediate.

##### Detailed Bit Representation
```sh
| 31 (imm[12]) | 30:25 (imm[10:5])    | 24:20 (rs2) | 19:15 (rs1) | 14:12 (funct3) | 11:8 (imm[4:1]) | 7 (imm[11]) | 6:0 (opcode) |
| 0            | 000000               | 00010       | 00001       | 000            | 0010            | 0           | 1100011      |
//hex representation
0x00410263

```

</details>
<details><summary><b> U-Type Instruction:</b>The U-type (Upper immediate) format is one of the instruction formats in the RISC-V architecture.</summary>

  ## Important U-Type Instructions in RISC-V:
  ##### 1. LUI (Load Upper Immediate):
  This instruction loads the 20-bit immediate value given in the instruction into the top 20 bits of a register. The lower 12 bits 
  are set to zero.
   
##### Format:

```sh
31-12	                | 11-7	                    | 6-0
20-bit immediate value|	rd (destination register)	| opcode
```
Opcode: 0010111

rd: The destination register to which the result of the addition will be stored.
##### example LUI x5, 0x12345
This instruction will load the immediate value 0x12345 into register x5. The lower 12 bits are set to zero, so effectively 0x12345 << 12 is loaded into x5.
```sh
31-12	                       | 11-7	                      | 6-0
20-bit immediate value       |	rd (destination register)	| opcode
000 0001 0010 0011 0100 0101 | 00101                      | 0110111JAL (Jump and Link) Instruction
```

##### Instruction Breakdown:

Opcode: The LUI instruction has an opcode of 0110111 (binary) which is 0x37 (hexadecimal).

Immediate Value: The immediate value provided in the instruction is 0x12345.

Destination Register: The register to be loaded with the immediate value here is x5

##### 2.AUIPC (Add Upper Immediate to PC): 
This adds the 20-bit immediate value to the program counter and places the result in a register. Essentially, this helps in generating PC-relative addresses.
##### Format:
```sh
31-12                   |	11-7	                      | 6-0
20-bit immediate value	| rd (destination register)	  |   opcode
```
Opcode: 0010111

rd: The destination register to which the result of the addition will be stored.

##### Example: AUIPC x5, 0x12345
This instruction adds the immediate value 0x12345 << 12 to the current value of the PC (Program Counter) and stores the result in register x5. This is useful for generating PC-relative addresses.

</details>
<details>
<summary><b> J-Type Instruction:</b> The J-type (Jump) format is another instruction format in the RISC-V architecture, and it’s used primarily for jump instructions that enable control flow changes.</summary>

  ## JAL (Jump and Link) Instruction
  ### Format:
 ```sh
  31	  | 30-21     |	20      |	19-12       |	11-7 |	6-0
imm[20] |	imm[10:1]	|imm[11]	| imm[19:12]  |	rd	 |  opcode
```
Opcode: 1101111

rd: The destination register where the return address will be stored.

imm: Immediate value representing the offset to jump to, with the final address being the PC plus this offset.
##### Example JAL x1, 2048
This instruction makes the processor jump to the PC plus the offset 2048 bytes and stores the return address (i.e., the address of the next instruction) in the register x1.
 ```sh
  31	     | 30-21      |	20       |	19-12        |	11-7  |	6-0
imm[20]    |	imm[10:1]	| imm[11]	 | imm[19:12]    |	rd	  |  opcode
0000000000 | 0          | 00000001 | 0             | 00001  |      1101111

```
Opcode (7 bits): 1101111

Destination Register (5 bits): 00001

Immediate/Target Address (20 bits): 2048 in binary is 00000001000000000000.
##### Breaking it Down:

Offset Calculation: The immediate value in J-type instructions is spread across multiple fields in the instruction encoding.

imm[20] bit is at position 31.

imm[10:1] bits are at positions 30-21.

imm[11] bit is at position 20.

imm[19:12] bits are at positions 19-12.

These fields are extracted and combined to form a 21-bit signed immediate value, which is then shifted left by one bit to align with even byte boundaries (since instruction addresses are word-aligned).

</details>

#  32-bit instruction code for 15 unique RISC-V instructions. 

![WhatsApp Image 2025-01-22 at 23 46 08_2d5e79a7](https://github.com/user-attachments/assets/01136393-0bd0-4c88-aa25-4c49c164b267)

<table>
<tr><th> Address </th><th>Instructions</th><th>type</th><th>binary representation</th></tr>
<tr><td> 10184 </td><td> addi sp, sp, -32 </td><td> I-type </td><td> 1111 1110 0000 0001 0000 0001 0001 0011</td></tr>
<tr><td> 10188 </td><td> sd ra, 24(sp) </td><td> S-type </td><td> 0000 0000 0001 0001 0011 1100 0010 0011
 </td></tr>
<tr><td> 1018C </td><td> sd s0, 16(sp) </td><td> S-type </td><td> 0000 0000 1000 0001 0011 1000 0010 0011
 </td></tr>
<tr><td> 10190 </td><td> sd s1, 8(sp) </td><td> S-type </td><td> 0000 0000 1001 0001 0011 0100 0010 0011
 </td></tr>
<tr><td> 10194 </td><td> li a1, 1 </td><td> I-type </td><td> 0000 0000 0001 0000 0000 0101 1001 0011
 </td></tr>
<tr><td> 10198 </td><td> li s0, 1 </td><td> I-type </td><td> 0000 0000 0001 0000 0000 0100 0001 0011
 </td></tr>
<tr><td> 1019C </td><td> li s1, 11 </td><td> I-type </td><td> 0000 0000 1011 0000 0000 0100 1001 0011 </td></tr>
<tr><td> 101A0 </td><td> mv a0, s0 </td><td> R-type </td><td> 0000 0000 0000 0100 0000 0101 0001 0011
 </td></tr>
<tr><td> 101A4 </td><td> jal ra, 101e0 </td><td> J-type </td><td> 0000 0011 1100 0000 0000 0000 1110 1111
 </td></tr>
<tr><td> 101A8 </td><td> sext.w a1, a0 </td><td> R-type </td><td> 0000 0000 0000 0101 0000 0101 1001 1011
 </td></tr>
<tr><td> 101AC </td><td> addiw s0, s0, 1 </td><td> I-type </td><td> 0000 0000 0001 0100 0000 0100 0001 1011
 </td></tr>
<tr><td> 101B0 </td><td>  bne s0, s1, 101a0	</td><td> B-type </td><td> 1111 1110 1001 0100 0001 1000 1110 0011
 </td></tr>
<tr><td> 101B4 </td><td> mv a2, a1 </td><td> R-type </td><td> 0000 0000 0000 0101 1000 0110 0001 0011
 </td></tr>
<tr><td> 101B8 </td><td> li a1, 10 </td><td> I-type </td><td> 0000 0000 1010 0000 0000 0101 1001 0011
 </td></tr>
<tr><td> 101BC </td><td> lui a0, 0x21 </td><td> U-type </td><td> 0000 0000 0000 0010 0001 0101 0011 0111
 </td></tr>
<tr><td> 101C0 </td><td> addi a0, a0, 432 </td><td> I-type </td><td> 0001 1011 0000 0101 0000 0101 0001 0011 </td></tr>
</table>

</details>

----------------------------------------------------------------------------------------------------------------
<details>
  <summary><b>Task 4:</b> Functional Simulation of RISC-V Core</summary>
  Functional simulation of RISC-V cores involves verifying that the core behaves correctly according to its design specifications. This process includes testing all possible instructions, ensuring compliance with the RISC-V instruction set architecture (ISA), and checking for any security vulnerabilities or malicious logic

  # About iverilog and gtkwave
1. Icarus Verilog is an implementation of the Verilog hardware description language.
2. GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

**Step 1: installation of iverilog and gtkwave**
   using the below commands in ubuntu
   ```sh
   $   sudo apt get update
   $   sudo apt get install iverilog gtkwave
   ```


  **Step 2: clone the repository and download the netlist files for simulation by entering the following commands in terminal.**
  ```sh
   $ git clone https://github.com/vinayrayapati/iiitb_rv32i
   $ cd iiitb_rv32i
   $ gedit iiitb_rv32i.v
   $ gedit iiitb_rv32i_tb.v
   ```
 **Step 3: To simulate and run the verilog code , enter the following commands in your terminal.**
  ```sh
 $ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
 $ ./iiitb_rv32i
   ```
**Step 4:To see the output waveform in gtkwave, enter the following commands in your terminal.**
 ```sh
 $ gtkwave iiitb_rv32i.vcd
   ```


</details>
