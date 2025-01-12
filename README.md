# samsung-riscv
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

----------------------------------------------------------------------------------------------------------------

