# VSDSquadron mini internship

The VSDSquadron Mini is a compact development board designed around the RISC-V architecture. It is particularly geared towards hobbyists, students, and developers who are interested in exploring and developing on the RISC-V platform.

## FEATURES:
#### RISC-V Processor:
The board is equipped with a RISC-V processor core, likely a 32-bit (RV32I) or 64-bit (RV64I) variant, depending on the specific model.

#### Compact Design:
Its small form factor makes it highly portable and easy to integrate into various projects.

#### Memory:
Includes onboard RAM and possibly flash memory for storage of firmware and applications.

#### Connectivity:
Features a range of I/O options, which typically include:
+ GPIO (General-Purpose Input/Output) pins
+ UART (Universal Asynchronous Receiver-Transmitter)
+ SPI (Serial Peripheral Interface)
+ I2C (Inter-Integrated Circuit)

#### Programming and Debugging:
Supports standard RISC-V development tools and toolchains such as GCC, LLVM, and various RISC-V IDEs (Integrated Development Environments).
Likely includes a JTAG (Joint Test Action Group) interface for debugging purposes.

# TASK 1

Write a C program to execute of sum 1 to N.

To proceed with the C code first install the virtual box. Then open a VDI file in Ubuntu using VirtualBox.

### 1. Virtual Box has been installed
![Virtual box installation](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/f8f0f23e-8b3a-4d4e-8b80-44c21a942189)

### 2. Ubuntu has been installed.
![Installation of Ubuntu](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/b0ff7e87-2ba4-41bf-88d2-e5b1ae820dfe)

### 3. Open the terminal window.
![Terminal](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/1dd93461-bcf0-4718-8057-f4a1e8d0f4e1)

### 4. C program to execute the sum of numbers from 1 to N

+ First install leafpad using the command: `sudo snap install leafpad`
+ Create the file using leafpad with the help of following command: `leafpad sum1ton.c &`
+ Write the program and save the same.

![C Program for Sum of 1 to N](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/8827f669-9a6a-4646-a3be-e45cbbb19321)

### 5. Output of the C program

+ Compile the C-program using the command: `gcc sum1ton.c`
+ To obtain the results use the command `./a.out`

![Fast Instruction](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/080b0214-3d89-4766-a3ec-9c0a1a4e98d8)

### 6. Conversion of the C program to RISC V instruction set

+ To convert the C program to RISC V instruction set, type `riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c`

![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/0b89f63c-f0d7-4660-b672-6e12d7cd73cc)
![Main Function](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/229957e4-ddaa-4f9c-9025-b6ff7ec0e6d9)

### 7. Calculation RISC-V instruction

![Calculation of riscv instruction](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/286eee27-b2dd-4d70-807c-ec2ce03865b8)







