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

  # What is RISC-V? 
  RISC-V (pronounced "risk-five") is an open standard instruction set architecture (ISA) that was created at the University of California, Berkeley, in 2010. Unlike proprietary ISAs, RISC-V is free and open, which means that anyone can use, modify, and implement it without paying royalties. This has led to its rapid adoption in both academic research and commercial applications. Here are a few key points about RISC-V:

**Simplicity and Efficiency:** RISC-V is designed with a reduced instruction set computing (RISC) philosophy, which emphasizes simplicity and efficiency in hardware and software design.

**Modularity:** RISC-V is highly modular, allowing designers to choose and customize the extensions they need. This flexibility makes it suitable for a wide range of applications, from microcontrollers to high-performance computing.

**Growing Ecosystem:** There is a growing ecosystem around RISC-V, including hardware implementations, software development tools, and educational resources. This has been supported by organizations like the RISC-V Foundation, which promotes and supports the adoption of the architecture.

**Industry Adoption:** Major tech companies, including NVIDIA, Western Digital, and Google, have shown interest in RISC-V and are incorporating it into their products.

**Open Source:** Being open-source, RISC-V promotes innovation and collaboration in the hardware community, lowering barriers for entry and enabling a more inclusive technological landscape.

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
  <summary><b>Task 4:</b>Perform a functional simulation of the given RISC-V Core Verilog netlist and 
testbench. </summary>
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
![WhatsApp Image 2025-01-25 at 23 33 00_c7f9fab2](https://github.com/user-attachments/assets/8f64cc8a-8a2a-4fb9-bc3c-50e5b93adc48)


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
![IMG-20250125-WA0023](https://github.com/user-attachments/assets/defbce2c-f8b1-483d-a4b8-ab809619bc31)

# The output waveform :
As shown in the figure below, all the instructions in the given verilog file is hard-coded. Hard-coded means that instead of following the RISCV specifications bit pattern, the designer has hard-coded each instructions based on their own pattern. 
![Screenshot 2025-01-25 235439](https://github.com/user-attachments/assets/162ecf6a-86b8-4e7f-9a06-471be341934b)

## Analysis of output waveforms
The waveform includes the following key signals:

clk: The clock signal driving the design.

NPC [31:0]: The next program counter value.

WB_OUT [31:0]: The write-back output signal.

RN: A register or control signal (usage depends on your design).

**1. add r6,r1,r2**
  ![IMG-20250125-WA0022](https://github.com/user-attachments/assets/f8682a06-6156-4285-a0c1-ef90e3a700db)


**2. sub r7,r1,r2**
    ![IMG-20250125-WA0028](https://github.com/user-attachments/assets/af07ba30-429c-4d53-8053-0b9a082a491a)

**3. and r8,r1,r3**
   ![IMG-20250125-WA0029](https://github.com/user-attachments/assets/b0b3e007-9e69-49ca-b8b8-56e514757c28)

**4. or r9,r2,r5**
   ![IMG-20250125-WA0030](https://github.com/user-attachments/assets/631fc2a4-b4fa-4cdd-a65f-4a21cb6dba63)

**5. xor r10,r1,r4**
  ![IMG-20250125-WA0031](https://github.com/user-attachments/assets/a239fecf-b113-4b1c-9fa3-c28a18cb3ee4)

**6. slt r11,r2,r4**
   ![IMG-20250125-WA0033](https://github.com/user-attachments/assets/3c3dafc3-e45c-496a-9c1d-81e261d93d66)

**7. addi r12,r4,5**
![IMG-20250125-WA0032](https://github.com/user-attachments/assets/ab29bb20-8b41-48c8-a13f-e0a34627b43e)

**8. sw r3,r1,2**
  ![IMG-20250125-WA0037](https://github.com/user-attachments/assets/00d16135-2877-48e3-b073-bf0ab8456033)

**9.  lw r13,r1,2**
    ![IMG-20250125-WA0035](https://github.com/user-attachments/assets/dbabb3e0-bccc-4946-b734-579782a3be13)

**10.  beq r0,r0,15**
   ![IMG-20250125-WA0035](https://github.com/user-attachments/assets/fef71909-bfc4-40b3-a4b6-18384d99f734)

**11.  add r14,r2,r2**
    ![IMG-20250125-WA0036](https://github.com/user-attachments/assets/d7d00e70-13c9-4d31-b820-f41bbb87d2dc)

</details>

----------------------------------------------------------------------------------------------------------------
<details>
<summary><b>Task 5:</b>Full adders are essential in digital systems as they serve as fundamental building blocks for creating more complex arithmetic circuits, such as multi-bit binary adders used in CPUs and ALUs for performing arithmetic operations. They are also crucial in digital multipliers, binary counters, digital signal processors (DSPs), and memory address calculations. Their versatile applications make full adders indispensable in modern electronic devices, ensuring precise and efficient arithmetic computations.</summary> 
  

# Full Adder implementation using VSDSquadron Mini RISC-V Board

### Project Overview
A **Full Adder** is a digital circuit designed to compute the sum of three binary digits: two significant bits (A and B) and a carry-in bit (Cin). It outputs a sum bit (S) and a carry-out bit (Cout).

#### Features
**Logical Operations:** Utilizes XOR gates for the sum and AND/OR gates for the carry.

**Cascadability:** Multiple full adders can be connected to form multi-bit adders.

**Versatility:** Widely used in arithmetic circuits, such as CPUs, ALUs, and digital multipliers.

**Efficiency:** Enables precise and efficient arithmetic computations in digital systems.

### Required Components
<table>
<tr><th>Component</th><th>quantity</th><th>Description</th></tr>
 <tr><td>VSDSquadron Mini Board</td><td>1</td><td>RISC-V SoC-based development board</td></tr>
  <tr><td>LEDs</td><td>2</td><td>Indicates Truth table</td></tr>
  <tr><td>Breadboard</td><td>1</td><td>For circuit connections</td></tr>
 <tr><td>USB Cable</td><td>1</td><td>Power and programming</td></tr>
  <tr><td>Jumper Wires</td><td>-</td><td>Jumper Wires</td></tr>
  <tr><td>Push Buttons</td><td>3</td><td>For input</td></tr>

</table>


### Pin Connections
<table>
<tr><th>Component</th><th>Board Pin</th><th>Purpose</th></tr>
 <tr><td>led1</td><td>PC4</td><td>represent output</td></tr>
  <tr><td>led2</td><td>PC5</td><td>represent output</td></tr>
  <tr><td>push button 1</td><td>PC1</td><td>represent input</td></tr>
<tr><td>push button 2</td><td>PC2</td><td>represent input</td></tr>
  <tr><td>push button 3</td><td>PC3</td><td>represent input</td></tr>


</table>

### PIN DIAGRAM 
![Screenshot 2025-02-17 224700](https://github.com/user-attachments/assets/c0704f41-6357-46a5-9104-5fdd95e79ed2)

### Working 
**Input Bits:**  The full adder takes three binary inputs: A, B, and Cin (carry-in).

**Sum Calculation:** The sum bit (S) is calculated using the XOR (exclusive OR) operation on the three input bits. The formula is:
                  sum= A⊕B⊕Cin
The XOR operation produces a '1' if an odd number of input bits are '1', otherwise it produces a '0'.

**Carry-Out Calculation:** The carry-out bit (Cout) is calculated using a combination of AND and OR gates. The formula is:
        Cout=(A.B)+(B.Cin)+(A.Cin)
The AND operations find the cases where any two of the input bits are '1', and the OR operation combines these cases to determine if a carry-out is needed.

**Output:** The full adder outputs the sum bit (S) and the carry-out bit (Cout), which can be used as input to another full adder in a multi-bit adder setup.

</details>

----------------------------------------------------------------------------------------------------------------
<details>
<summary><b>Task 6: </b>A full adder is a digital circuit that computes the sum of three binary bits: two significant bits (A and B) and a carry-in bit (Cin). It produces a sum bit (S) and a carry-out bit (Cout). Full adders are essential components for building arithmetic circuits, such as multi-bit adders.</summary>

## Project Implementation
**Hardware Setup:** Connect three input push buttons to the GPIO pins of the VSDSquadron Mini for binary data input. Connect two LEDs to display the sum and carry-out outputs1.

**Software Development:** Write the code to implement the full adder logic using digital gates (AND, OR, XOR) in the PlatformIO IDE. Configure the GPIO pins for input and output operations.

**Testing and Verification:** Use a truth table to verify the correct operation of the full adder circuit. The truth table for a full adder is as follows:
<table>
<tr><th>A</th><th>B</th><th>Cin</th><th>Sum</th><th>Cout</th></tr>
  <tr><td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> </tr>
  <tr><td>0</td> <td>0</td> <td>1</td> <td>1</td> <td>0</td> </tr>
  <tr><td>0</td> <td>1</td> <td>0</td> <td>1</td> <td>0</td> </tr>
  <tr><td>0</td> <td>1</td> <td>1</td> <td>0</td> <td>1</td> </tr>
  <tr><td>1</td> <td>0</td> <td>0</td> <td>1</td> <td>0</td> </tr>
  <tr><td>1</td> <td>0</td> <td>1</td> <td>0</td> <td>1</td> </tr>
  <tr><td>1</td> <td>1</td> <td>0</td> <td>0</td> <td>1</td> </tr>
  <tr><td>1</td> <td>1</td> <td>1</td> <td>1</td> <td>1</td> </tr>
</table>

**Execution:** Run the program on the VSDSquadron Mini and observe the LEDs displaying the sum and carry-out results based on the input combinations

**This project demonstrates the practical application of digital logic and RISC-V architecture in executing arithmetic operations.**

## Code Implementation
 ```sh
#include<stdio.h>
#include<debug.h>
#include<ch32v00x.h>

// Defining the Logic Gate Function 
int and(int bit1, int bit2)
{
    int out = bit1 & bit2;
    return out;
}
int or(int bit1, int bit2)
{
    int out = bit1 | bit2;
    return out;
}
int xor(int bit1, int bit2)
{
    int out = bit1 ^ bit2;
    return out;
}

// Configuring GPIO Pins
void GPIO_Config(void)
{
    GPIO_InitTypeDef GPIO_InitStructure = {0}; // structure variable used for GPIO configuration
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE); // to enable the clock for port D
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE); // to enable the clock for port C
    
    // Input Pins Configuration
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_1 | GPIO_Pin_2 | GPIO_Pin_3;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Defined as Input Type
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    //Output Pins Configuration
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_4 | GPIO_Pin_5;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP; // Defined Output Type
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz; // Defined Speed
    GPIO_Init(GPIOC, &GPIO_InitStructure);
}

// The MAIN function responsible for the execution of program
int main()
{
    uint8_t A, B, Cin, Sum, Carry; // Declared the required variables
    uint8_t p, q, r, s, t; 
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    while(1)
    {
        A = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_1);
        B = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_2);
        Cin = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_3);
        s = xor(A, B);
        Sum = xor(Cin, s);
        p = and(A, B);
        q = and(B, Cin);
        r = and(Cin, A);
        t = or(p, q);
        Carry = or(r, t);

        /* SUM */
        if(Sum == 0)
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_4, SET);
        }
        else
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_4, RESET);
        }

        /* CARRY */
        if(Carry == 0)
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_5, SET);
        }
        else
        {
            GPIO_WriteBit(GPIOC, GPIO_Pin_5, RESET);
        }
    }
}


   ```

## Demonstration Vedio
[https://drive.google.com/file/d/1_lYlIaUTtjNy1c9X6w4urD6A8rkqNnxj/view?usp=sharing](https://drive.google.com/uc?id=1YoKYuwS8Y0-aJuFBZaeMQHQL1sCFXXal&export=download)


## Applications
**Arithmetic Operations:** Full adders are used to construct multi-bit binary adders, such as ripple-carry adders and carry-lookahead adders, which perform arithmetic operations like addition and subtraction in CPUs and ALUs (Arithmetic Logic Units).

**Multiplication:** In digital multipliers, full adders are employed to sum partial products, facilitating binary multiplication in processors and digital signal processors (DSPs).

**Digital Counters:** Full adders are used in the design of binary counters, which count in binary sequences and are fundamental components in timing and control circuits.

**ALUs (Arithmetic Logic Units):** ALUs, which are part of the CPU, utilize full adders to perform arithmetic and logical operations. They are crucial for executing instructions in microprocessors and microcontrollers.

**Digital Signal Processing:** Full adders are used in DSP algorithms for various signal processing tasks, such as filtering, modulation, and encoding.

**FPGA and ASIC Design:** Full adders are used in custom hardware design, such as Field-Programmable Gate Arrays (FPGAs) and Application-Specific Integrated Circuits (ASICs), where custom arithmetic logic is implemented for specific applications.

**Error Detection and Correction:** Full adders are utilized in the design of circuits for error detection and correction, such as Hamming code generators and parity checkers, to ensure data integrity in communication systems.

**Memory Address Calculation:** Full adders are used in memory address calculation circuits for accessing and managing memory locations in computer systems.

**Control Systems:** Full adders play a role in control systems for robotics, automation, and embedded systems, where precise arithmetic computations are required.

</details>

----------------------------------------------------------------------------------------------------------------
<details>
<summary><b> CONCLUSION: </b>In this internship led by Kunal Ghosh Sir, I gained hands-on experience with RISC-V architecture and VLSI chip design using open-source tools. The tasks ranged from compiling C code, simulating RISC-V programs, and understanding RISC-V instructions to performing functional simulations and understanding and implementation using VSDSquadron Mini RISC-V Board.
</summary>
