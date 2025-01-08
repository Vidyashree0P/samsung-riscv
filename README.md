# samsung-riscv
The program focuses on the RISC-V architecture and leverages open-source tools to educate participants about VLSI chip design and RISC-V. The internship is led by Kunal Ghosh Sir.
# installation of virtualbox to windows
![installation](https://github.com/user-attachments/assets/aa383b29-34ec-4b4e-b630-6c34f93cd1b6)


# Task 1: Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler

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
1. -O1: Enables basic optimization for better performance without significantly increasing compilation time.

2. -Ofast: Optimize the code aggressively for the best possible speed.

