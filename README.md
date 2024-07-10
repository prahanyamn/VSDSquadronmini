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


By following these steps, you will establish a virtual environment with the RISC-V toolchain prepared for development. This configuration enables you to compile and test RISC-V programs.

# TASK 2

## PROJECT 1: Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine 

The given C program is a straightforward implementation of an Automated Parking Ticket Vending Machine. It includes features for issuing parking tickets, processing payments for the issued tickets, and presents a user interface via a console menu.

### Code
```
#include <stdio.h>
#include <stdlib.h>

int current_ticket = 0;

void issue_ticket() {
    current_ticket++;
    printf("Ticket issued: %d\n", current_ticket);
}

void pay_ticket(int ticket_number) {
    if (ticket_number <= current_ticket && ticket_number > 0) {
        printf("Ticket %d has been paid.\n", ticket_number);
    } else {
        printf("Invalid ticket number.\n");
    }
}

void show_menu() {
    printf("1. Issue Ticket\n");
    printf("2. Pay Ticket\n");
    printf("3. Exit\n");
}

int main() {
    int choice, ticket_number;

    while (1) {
        show_menu();
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                issue_ticket();
                break;
            case 2:
                printf("Enter ticket number to pay: ");
                scanf("%d", &ticket_number);
                pay_ticket(ticket_number);
                break;
            case 3:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}
```

+ The menu is displayed to the user.
+ The user enters a choice.
+ Based on the user's choice:
        A new ticket is issued.
        A specific ticket is marked as paid.
        The program exits.
        An error message is shown for invalid choices.
  
+ The loop continues until the user chooses to exit.
  
![WhatsApp Image 2024-06-25 at 16 18 09_a1e42721](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/f49d38df-435e-484f-be4b-75faf1d83f4b)

![WhatsApp Image 2024-06-25 at 16 18 09_f59f14a5](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/a70fb715-3941-416f-8360-e090403f8dc2)

This code serves as a fundamental illustration of how an automated ticket vending system can be implemented in C. It can be further enhanced with extra features such as ticket validation, payment processing, and database integration for a more comprehensive solution.

### Output

+ Compile the C-program using the command: `gcc ticketterminal.c`
+ To obtain the results use the command `./a.out`
  
![WhatsApp Image 2024-06-25 at 16 37 39_116cefac](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/09e2301c-7311-4d2c-9cd8-65be77632222)


### Conversion of the C program to RISC V instruction set

+ To convert the C program to RISC V instruction set, type `riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

   ![WhatsApp Image 2024-06-25 at 18 13 12_ade9c524](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/6704d4a1-6995-448c-aaca-0bb96268f06d)

+ Now, switch focus to executing the main function and performing calculations using this command: `riscv64-unknown-elf-objdump -d ticketterminal.o |less`

   ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/782f66b9-83dc-404e-924b-77669d12f98a)

   ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/93f53b72-77ab-44ec-aeca-125f09e7338a)

+ Calculation for o1 instruction
  
   ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/ecc75b6a-baa6-4a40-8483-740d9b4aed16)

+ To obtain the difference execute the same function using the -Ofast function like given below `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

   ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/fdd610fc-e7b9-4c92-84e8-7feca4c3bef4)
  
   ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/ceaefe43-7f4e-4b1f-9a87-d2464811311e)

+ By comparing both main functions, we observe that the Ofast function has been optimized for fewer numbers.


The given C program effectively illustrates the essential functions of an Automated Parking Ticket Vending Machine. By employing basic functions and a console-based menu interface, the code offers a straightforward and user-friendly method for issuing parking tickets and handling their payments.


# TASK 3

## SPIKE simulation and verification with -O1 and -OFast 

+ Execute the RISC-V program using the SPIKE RISC-V ISA simulator to perform a detailed simulation.

+ Test and verify the program's behavior under two different optimization levels:
  
O1: Apply basic optimizations that enhance performance while keeping compilation time reasonable.

Ofast: Apply aggressive optimizations to maximize performance, even if it means sacrificing strict standards compliance.

+ Utilize the RISC-V `objdump` tool to disassemble the program's binary, translating the machine code into a human-readable assembly format.

+ Compile your RISC-V program with the -O1 optimization level to apply basic optimizations that improve performance without significantly increasing compilation time.

`riscv64-unknown-elf-gcc -O1 -o program_O1 program.c`

+ Compile your RISC-V program with the -Ofast optimization level to apply aggressive optimizations for maximum performance, which might break strict standards compliance.

`riscv64-unknown-elf-gcc -Ofast -o program_Ofast program.c`

![Screenshot from 2024-06-27 11-28-13](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/84ead37d-304e-430c-ade3-5f4a10ac4b2a)

+ Command: `riscv64-unknown-elf-objdump -d ticketterminal.o |less`

![Screenshot from 2024-06-27 11-28-34](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/da3a3cfd-eae8-442d-9c16-d3a034b2f15b)

+ Command : `spike pk ticketterminal.o`

![Screenshot from 2024-06-27 11-27-57](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/30fa5f94-4ba5-4bfd-b1ad-93e33230cb6a)

+ To debug the spike, start with the following command: `spike -d pk ticketterminal.o`

+ Next, use the command `until pc 0 100b0`. This sets the program counter to run from 0 up to the address 100b0, which is the first line of the main function.

+ To find the contents of the code at this address, use the command: `reg 0 sp`

+ Initially, the value of the stack pointer (sp) is `0x0000003ffffffb40`. After the next step, the stack pointer value decreases by a hexadecimal amount, resulting in `0x0000003ffffffac0`.

+ By subtracting these two main function values, the result is `0x000000ffffffac0`.

![Screenshot from 2024-06-27 11-31-02](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/7a81121d-03f3-40b1-85fc-bc642ca073f3)

# TASK 4

## Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions

ADD r1, r2, r3

SUB r3, r1, r2

AND r2, r1, r3

OR r8, r2, r5

XOR r8, r1, r4

SLT r10, r2, r4

ADDI r12, r3, 5

SW r3, r1, 4

SRL r16, r11, r2

BNE r0, r1, 20

BEQ r0, r0, 15

LW r13, r11, 2

SLL r15, r11, r2

To identify and construct the 32-bit instruction codes for the given RISC-V instructions, we need to follow the RISC-V instruction format for each type (R, I, S, B, U, J). Here are the steps:

+ Identify the instruction type for each instruction.

+ Determine the opcode, funct3, and funct7 (if applicable) values for each instruction.

+ Fill in the fields (opcode, rd, funct3, rs1, rs2, funct7, imm) to construct the 32-bit binary instruction.

### Instruction Types and Fields

+ R-type: opcode[6:0] | rd[11:7] | funct3[14:12] | rs1[19:15] | rs2[24:20] | funct7[31:25]
+ I-type: opcode[6:0] | rd[11:7] | funct3[14:12] | rs1[19:15] | imm[31:20]
+ S-type: opcode[6:0] | imm[4:0][11:7] | funct3[14:12] | rs1[19:15] | rs2[24:20] | imm[11:5][31:25]
+ B-type: opcode[6:0] | imm[11][7] | imm[4:1][11:8] | funct3[14:12] | rs1[19:15] | rs2[24:20] | imm[10:5][31:25] | imm[12][31]
+ U-type: opcode[6:0] | rd[11:7] | imm[31:12]
+ J-type: opcode[6:0] | rd[11:7] | imm[19:12][20] | imm[10:1][11] | imm[31:21]

#### 1. ADD r1, r2, r3

Type: R

Opcode: 0110011

Funct3: 000

Funct7: 0000000

rs1: r2 = 00010

rs2: r3 = 00011

rd: r1 = 00001

32-bit: 0000000 00011 00010 000 00001 0110011

#### 2. SUB r3, r1, r2

Type: R

Opcode: 0110011

Funct3: 000

Funct7: 0100000

rs1: r1 = 00001

rs2: r2 = 00010

rd: r3 = 00011

32-bit: 0100000 00010 00001 000 00011 0110011

#### 3. AND r2, r1, r3

Type: R

Opcode: 0110011

Funct3: 111

Funct7: 0000000

rs1: r1 = 00001

rs2: r3 = 00011

rd: r2 = 00010

32-bit: 0000000 00011 00001 111 00010 0110011

#### 4. OR r8, r2, r5

Type: R

Opcode: 0110011

Funct3: 110

Funct7: 0000000

rs1: r2 = 00010

rs2: r5 = 00101

rd: r8 = 01000

32-bit: 0000000 00101 00010 110 01000 0110011

#### 5. XOR r8, r1, r4

Type: R

Opcode: 0110011

Funct3: 100

Funct7: 0000000

rs1: r1 = 00001

rs2: r4 = 00100

rd: r8 = 01000

32-bit: 0000000 00100 00001 100 01000 0110011

#### 6. SLT r10, r2, r4

Type: R

Opcode: 0110011

Funct3: 010

Funct7: 0000000

rs1: r2 = 00010

rs2: r4 = 00100

rd: r10 = 01010

32-bit: 0000000 00100 00010 010 01010 0110011

#### 7. ADDI r12, r3, 5

Type: I

Opcode: 0010011

Funct3: 000

rs1: r3 = 00011

rd: r12 = 01100

imm: 000000000101

32-bit: 000000000101 00011 000 01100 0010011

#### 8. SW r3, r1, 4

Type: S

Opcode: 0100011

Funct3: 010

rs1: r1 = 00001

rs2: r3 = 00011

imm: 0000000 | 4 (00000 | 00100)

32-bit: 0000000 00011 00001 010 00100 0100011

#### 9. SRL r16, r11, r2

Type: R

Opcode: 0110011

Funct3: 101

Funct7: 0000000

rs1: r11 = 01011

rs2: r2 = 00010

rd: r16 = 10000

32-bit: 0000000 00010 01011 101 10000 0110011

#### 10. BNE r0, r1, 20

Type: B

Opcode: 1100011

Funct3: 001

rs1: r0 = 00000

rs2: r1 = 00001

imm: 20 (00000 | 00101 | 0 | 0000)

32-bit: 00000 00101 000 00000 00001 1100011

#### 11. BEQ r0, r0, 15

Type: B

Opcode: 1100011

Funct3: 000

rs1: r0 = 00000

rs2: r0 = 00000

imm: 15 (0000 | 0011 | 1 | 0000)

32-bit: 00000 00111 000 00000 00000 1100011

#### 12. LW r13, r11, 2

Type: I

Opcode: 0000011

Funct3: 010

rs1: r11 = 01011

rd: r13 = 01101

imm: 000000000010

32-bit: 000000000010 01011 010 01101 0000011

#### 13. SLL r15, r11, r2

Type: R

Opcode: 0110011

Funct3: 001

Funct7: 0000000

rs1: r11 = 01011

rs2: r2 = 00010

rd: r15 = 01111

32-bit: 0000000 00010 01011 001 01111 0110011

## 32-bit instruction codes

```
ADD r1, r2, r3: 0000000 00011 00010 000 00001 0110011
SUB r3, r1, r2: 0100000 00010 00001 000 00011 0110011
AND r2, r1, r3: 0000000 00011 00001 111 00010 0110011
OR r8, r2, r5: 0000000 00101 00010 110 01000 0110011
XOR r8, r1, r4: 0000000 00100 00001 100 01000 0110011
SLT r10, r2, r4: 0000000 00100 00010 010 01010 0110011
ADDI r12, r3, 5: 000000000101 00011 000 01100 0010011
SW r3, r1, 4: 0000000 00011 00001 010 00100 0100011
SRL r16, r11, r2: 0000000 00010 01011 101 10000 0110011
BNE r0, r1, 20: 00000 00101 000 00000 00001 1100011
BEQ r0, r0, 15: 00000 00111 000 00000
 ```

# TASK 5

### RISC-V Core Verilog netlist and Testbench for Functional simulation

##### Acknowledgements Section :

`https://github.com/vinayrayapati/rv32i/`

I have developed a set of commands and achieved the desired output for my project. This was accomplished by referece above and the key sources, which provided valuable guidance and examples. These references were in understanding the required techniques and applying them effectively in my implementation.

### REFERENCE-DRIVEN DEVELOPMENT

+ Cloning is the process of making a local duplicate of a remote repository. This enables you to have a full copy of the repository on your local machine.
+ Command 1 : `git clone http://github.com/vinayrayapati/rv32i.git my_pticket_rv32i`
+ Command 2 : `cd my_pticket_rv32i`

  ![WhatsApp Image 2024-07-08 at 22 08 21_2eb938bb](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/06350337-8907-4545-bee5-dda2500e002b)

+ This will download the project into a local directory named my_pticket_rv32i.

+ Command 3 : `sudo apt update`
+ Command 4 : `sudo apt install inverilog gtkwave`

  ![WhatsApp Image 2024-07-08 at 22 08 21_39a144d3](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/83aa8d3c-96a7-41f5-91cf-4d50c86d584c)

  ![WhatsApp Image 2024-07-08 at 22 08 57_739d76b7](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/2f966fff-99b1-4f1d-a3e9-1a75c6338f84)

### OUTPUT

##### 1. ADD (r1,r2,r3)

![WhatsApp Image 2024-07-08 at 21 53 54_5a16b143](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/d6ed1a26-27e9-4990-81eb-5fca0118dceb)

##### 2. SUB (r3,r1,r2)

![WhatsApp Image 2024-07-08 at 21 53 55_febe4122](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/2f40ba19-d4c8-48ec-b834-ef34ee74ce51)

##### 3. AND (r2,r1,r3)

![WhatsApp Image 2024-07-08 at 21 53 54_3827bd8e](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/41e6c73e-3990-4042-82b2-996d8df185b6)

##### 4. OR (r8,r2,r5)

![WhatsApp Image 2024-07-08 at 21 53 55_b75bbd5a](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/093512bc-bc72-4f91-b086-4265d0821708)

##### 5. XOR (r8,r1,r4)

![WhatsApp Image 2024-07-08 at 21 53 56_1e70e0a0](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/02708dee-6911-4963-a331-b004ce02629c)

##### 6. SLT (r10,r2,r4)

![WhatsApp Image 2024-07-08 at 21 53 55_e116fac1](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/6c28a740-fe33-4ae2-9e68-43e0cf000c93)

##### 7. BEQ (r0,r0,15)

![WhatsApp Image 2024-07-08 at 21 53 55_d5b95de4](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/60f19ca7-880d-4995-b2cf-674c8ea88226)

##### 8. BNE (r0,r1,20)

![WhatsApp Image 2024-07-08 at 21 53 55_e357e9a1](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/f8805642-a73c-4920-9848-427f896e8f2b)

##### 9. SLL (r15,r11,r2)

![WhatsApp Image 2024-07-08 at 21 53 56_4068577a](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/76922407-c6b8-4c59-a458-b318f9805f1d)

##### 10. GTKWAVE WINDOW

![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/d3294079-1007-4cc3-94bb-ef6176ebcf0e)


# TASK 6

## PROJECT : Ticket Terminal Designer: Developing an Automated Parking Ticket Vending Machine

### Overview

The project involves designing an Automated Parking Ticket Vending Machine using the VSDSquadron mini microcontroller. The machine will automate the process of issuing parking tickets, managing payments, and controlling entry/exit barriers. The system will include components for user interaction, payment processing, ticket printing, and barrier control.

### Components Required

1. VSDSquadron mini: The core microcontroller for processing and control.

2. LCD Display: For displaying instructions, ticket details, and payment information.
Model: 16x2 or 20x4 character LCD.

3. Keypad: For user input, such as selecting options and entering data.
Model: 4x4 matrix keypad.

4. Thermal Printer: For printing parking tickets.
Model: 58mm or 80mm thermal printer.

5. Coin Acceptor: For accepting coin payments.
Model: Multi-coin acceptor.

6. Card Reader: For accepting card payments.
Model: Magnetic stripe or RFID card reader.

7. Real-Time Clock (RTC): For time-stamping tickets.
Model: DS3231.

8. Power Supply: To power all components.
Model: 12V/5A power supply.

9. Relay Module: To control high-power components like the barrier gate.
Model: 4-channel relay module.

10. Miscellaneous: Connectors, resistors, capacitors, and wiring.

### Pin Diagram

1. LCD Display:

   + RS: Digital Pin 2

   + EN: Digital Pin 3

   + D4: Digital Pin 4

   + D5: Digital Pin 5

   + D6: Digital Pin 6

   + D7: Digital Pin 7

2. Keypad:

   + R1: Digital Pin 8

   + R2: Digital Pin 9

   + R3: Digital Pin 10

   + R4: Digital Pin 11

   + C1: Digital Pin 12

   + C2: Digital Pin 13

   + C3: Digital Pin A0

   + C4: Digital Pin A1

3. Thermal Printer:

   + TX: Digital Pin A2

   + RX: Digital Pin A3

4. Coin Acceptor:

   + Signal: Digital Pin A4

5. Card Reader:

   + Data: Digital Pin A5

6. Barrier Gate:

   + Control: Relay Module (connected to Digital Pins 14-17 for 4-channel)

7. Real-Time Clock (RTC):

   + SDA: Digital Pin A6

   + SCL: Digital Pin A7
