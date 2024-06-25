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
+  To obtain the results use the command `./a.out`
  
![WhatsApp Image 2024-06-25 at 16 37 39_116cefac](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/09e2301c-7311-4d2c-9cd8-65be77632222)


### Conversion of the C program to RISC V instruction set

To convert the C program to RISC V instruction set, type `riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

![WhatsApp Image 2024-06-25 at 18 13 12_ade9c524](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/6704d4a1-6995-448c-aaca-0bb96268f06d)

Now, switch focus to executing the main function and performing calculations using this command: `riscv64-unknown-elf-objdump -d ticketterminal.o |less`

![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/782f66b9-83dc-404e-924b-77669d12f98a)

![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/93f53b72-77ab-44ec-aeca-125f09e7338a)

+ Calculation for o1 instruction
  
  ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/ecc75b6a-baa6-4a40-8483-740d9b4aed16)

+ To obtain the difference execute the same function using the -Ofast function like given below `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o ticketterminal.o ticketterminal.c`

  ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/fdd610fc-e7b9-4c92-84e8-7feca4c3bef4)
  
  ![image](https://github.com/prahanyamn/VSDSquadronmini/assets/173597769/ceaefe43-7f4e-4b1f-9a87-d2464811311e)

+ By comparing both main functions, we observe that the Ofast function has been optimized for fewer numbers.


The given C program effectively illustrates the essential functions of an Automated Parking Ticket Vending Machine. By employing basic functions and a console-based menu interface, the code offers a straightforward and user-friendly method for issuing parking tickets and handling their payments.



















