
**VLSI Physical Design for ASICs**

The objective of VLSI (Very Large Scale Integration) physical design for ASICs (Application-Specific Integrated Circuits) is to transform a logical design description (RTL - Register Transfer Level) into a physical layout that can be fabricated as an integrated circuit. This involves translating the high-level functional representation of the circuit into a physical implementation that meets design constraints, performance targets, and manufacturability requirements.

   **ISA (Instruction Set Archhitecture)**
        
  ISA defines the interface between a computer's hardware and its software, specifically how the processor and its components interact with the software instructions that drive the execution of tasks.
        It encompasses a set of instructions, addressing modes, data types, registers, memory organization, and the mechanisms for executing and managing instructions.

   **RISC-V (Reduced Instruction Set Computing - Five)**.
       
  It is an open-source Instruction Set Architecture (ISA) that has gained significant attention and adoption in the world of computer architecture and semiconductor design.
        RISC architectures simplify the instruction set by focusing on a smaller set of instructions, each of which can be executed in a single clock cycle. This approach usually leads to faster execution of individual instructions.
# pes_asic_class
![kk](https://github.com/KushalR17/pes_asic_class/assets/142383052/43b12409-0fe3-4721-ac02-3bd342965195)![Uploading kk.png…]()
From Apps to Hardware

 Apps: Application software, often referred to simply as "applications" or "apps," is a type of computer software that is designed to perform specific tasks or functions for end-users.

System software: System software refers to a category of computer software that acts as an intermediary between the hardware components of a computer system and the user-facing application software. It provides essential services, manages hardware resources, and enables the execution of application programs. System software plays a critical role in maintaining the overall functionality, security, and performance of a computer system.'

Operating System: The operating system is a fundamental piece of software that manages hardware resources and provides various services for both users and application programs. It controls tasks such as memory management, process scheduling, file system management, and user interface interaction. Examples of operating systems include Microsoft Windows, macOS, Linux, and Android.

 Compiler: A compiler is a type of software tool that translates high-level programming code written by developers into assembly-level language.

Assembler: An assembler is a software tool that translates assembly language code into machine code or binary code that can be directly executed by a computer's processor.


RTL: RTL serves as an abstraction level in the design process that represents the behavior of a digital circuit in terms of registers and the operations that transfer data between them.

Hardware: Hardware refers to the physical components of a computer system or any electronic device. It encompasses all the tangible parts that make up a computing or electronic device and enable it to perform various tasks.

**Detail Description of Course Content**

Pseudo Instructions: Pseudo-instructions are used to simplify programming, improve code readability, and reduce the number of explicit instructions a programmer needs to write. They are especially useful for common programming patterns that involve multiple instructions. Ex: li, mv.

**Base Integer Instructions:** The term "base integer instructions" refers to the fundamental set of instructions that form the foundation for performing basic arithmetic, logical, and data movement operations. Ex: add, sub, and, or, xor, sll.

**Multiply Extension Intructions:**The RISC-V architecture includes a set of multiply and multiply-accumulate (MAC) extension instructions that enhance the instruction set to perform efficient multiplication and multiplication-accumulate operations.
 Ex: mul, mulh, mulhu, mulhsu.


**Single and Double Precision Floating Point Extension:** 
  The RISC-V architecture includes floating-point extensions that provide support for both single-precision (32-bit) and double-precision (64-bit) floating-point arithmetic operations. These extensions are often referred to as the "F" and "D" extensions, respectively. Floating-point arithmetic is essential for handling real numbers with fractional parts and for performing accurate calculations involving decimal values.


**Memory Allocation and Stack Pointer**

    Memory allocation refers to the process of assigning and managing memory segments for various data structures, variables, and objects used by a program. It involves allocating memory space from the system's memory pool and releasing it when it is no longer needed to prevent memory leaks.
    The stack pointer is a register used by a program to keep track of the current position of the program's execution on the call stack.
    
  ![sum1](https://github.com/KushalR17/pes_asic_class/assets/142383052/9ad2d9cf-1874-402a-ad35-6825f6eab990)
e gcc compiler, we compiled the program to get the output.
![p1](https://github.com/KushalR17/pes_asic_class/assets/142383052/d8b803e8-600c-485b-856a-610da1e9c0c8)
**RISCV GCC Compiler and Dissemble**

Using the riscv gcc compiler, we compiled the C program.

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

Using ls -ltr sum1ton.c, we can check that the object file is created.

To get the dissembled ALP code for the C program,

riscv64-unknown-elf-objdump -d sum1ton.o | less .

In order to view the main section, type /main.

Here, since we used -O1 optimisation, the number of instructions are 15.


![main](https://github.com/KushalR17/pes_asic_class/assets/142383052/4943ce47-fcf3-4c06-8154-0c239b86604e)
In order to view the different options available for these fields, use the following commands

go to the directory where riscv64-unkonwn-elf is present

    -O1 :  riscv64-unkonwn-elf --help=optimizer
    -mabi : riscv64-unknown-elf-gcc --target-help
    -march : riscv64-unknown-elf-gcc --target-help

For different instances,

    use the command riscv64-unknown-elf-objdump -d 1_to_N.o | less
    use  /instance to search for an instance
    press ENTER
    press n to search next occurance
    press N to search for previous occurance.
    use esc :q to quit
**Spike Simulation and Debug**

spike pk sum1ton.o is used to check whether the instructions produced are right to give the correct output.

![spike2](https://github.com/KushalR17/pes_asic_class/assets/142383052/c0c06a83-8ce5-46a1-995b-8c2e7dc59adc)
spike -d pk sum1ton.c is used for debugging.

The contents of the registers can also be viewed.

![spike1](https://github.com/KushalR17/pes_asic_class/assets/142383052/c2c84a2e-0e79-48e6-a481-6aea19a52869)
**Integer Number Representation**
**Unsigned Numbers**

    Unsigned numbers, also known as non-negative numbers, are numerical values that represent magnitudes without indicating direction or sign.
    Range: [0, (2^n)-1 ]

**Signed Numbers**

    Signed numbers are numerical values that can represent both positive and negative magnitudes, along with zero.
    Range : Positive : [0 , 2^(n-1)-1] Negative : [-1 to 2^(n-1)]
**Unsigned:**
    #include <stdio.h>
#include <math.h>

int main(){
	unsigned long long int max = (unsigned long long int) (pow(2,64) -1);
	unsigned long long int min = (unsigned long long int) (pow(2,64) *(-1));
	printf("lowest number represented by unsigned 64-bit integer is %llu\n",min);
	printf("highest number represented by unsigned 64-bit integer is %llu\n",max);
	return 0;
}



![pro22](https://github.com/KushalR17/pes_asic_class/assets/142383052/9fd8c800-3aaa-43e2-9fad-a2c45d4279d6)


**Signed:**
#include <stdio.h>
#include <math.h>

int main(){
	long long int max = (long long int) (pow(2,63) -1);
	long long int min = (long long int) (pow(2,63) *(-1));
	printf("lowest number represented by signed 64-bit integer is %lld\n",min);
	printf("highest number represented by signed 64-bit integer is %lld\n",max);
	return 0;
}
![program3](https://github.com/KushalR17/pes_asic_class/assets/142383052/9bd48167-434e-4f31-af7f-9f08b46b686e)


**DAY2 LAB WORK**

**Application Binary Interface
Introduction to ABI**

    An Application Binary Interface (ABI) is a set of rules and conventions that dictate how binary code interacts with and communicates with other binary code, typically at the level of machine code or compiled code. In simpler terms, it defines the interface between two software components or systems that are written in different programming languages, compiled by different compilers, or running on different hardware architectures.
    The ABI is crucial for enabling interoperability between different software components, such as different libraries, object files, or even entire programs. It allows components compiled independently and potentially on different platforms to work seamlessly together by adhering to a common set of rules for communication and data representation.

Memmory Allocation for Double Words

64-bit number (or any multi-byte value) can be loaded into memory in little-endian or big-endian. It involves understanding the byte order and arranging the bytes accordingly

    Little-Endian: In little-endian representation, you store the least significant byte (LSB) at the lowest memory address and the most significant byte (MSB) at the highest memory address.
    Big-Endian: In big-endian representation, you store the most significant byte (MSB) at the lowest memory address and the least significant byte (LSB) at the highest memory address.

   ** Load, Add and Store Instructions**
   
   Load, Add, and Store instructions are fundamental operations in computer architecture and assembly programming. They are often used to manipulate data within a computer's memory and registers.

    Load Instructions: Load instructions are used to transfer data from memory to registers. They allow you to fetch data from a specified memory address and place it into a register for further processing.

Example ld x6, 8(x5)

In this Example

    ld is the load double-word instruction.
    x6 is the destination register.
    8(x5) is the memory address pointed to by register x5 (base address + offset).

    Store Instructions: Store instructions are used to write data from registers into memory.They store values from registers into memory addresses

Example sd x8, 8(x9)

In this Example

    sd is the store double-word instruction.
    x8 is the source register.
    8(x9) is the memory address pointed to by register x9 (base address + offset).

    
    Add Instructions: Add instructions are used to perform addition operations on registers. They add the values of two source registers and store the result in a destination register.
    
   ** 32-Registers and their ABI Names**

The choice of the number of registers in a processor's architecture, such as the RISC-V RV64 architecture with its 32 general-purpose registers, involves a trade-off between various factors. While modern processors can have more registers but increasing the number of registers could lead to larger instructions, which would take up more memory and potentially slow down instruction fetch and decode.
ABI Names

ABI names for registers serve as a standardized way to designate the purpose and usage of specific registers within a software ecosystem. These names play a critical role in maintaining compatibility, optimizing code generation, and facilitating communication between different software components.
![image](https://github.com/KushalR17/pes_asic_class/assets/142383052/1cdaa957-9623-491b-996a-e6589da15aec)

**Labwork using ABI Function Calls**

Algorithm for C Program using ASM

    Incorporating assembly language code into a C program can be done using inline assembly or by linking separate assembly files with your C code.
    When you call an assembly function from your C code, the C calling convention is followed, including pushing arguments onto the stack or passing them in registers as required.
    The program executes the assembly function, following the assembly instructions you've provided.

Review ASM Function Calls

    We wrote C code in one file and your assembly code in a separate file.
    In the assembly file, we declared assembly functions with appropriate signatures that match the calling conventions of your platform.

 #include <stdio.h>

extern int load(int x, int y);

int main()
{
  int result = 0;
  int count = 9;
  result = load(0x0, count+1);
  printf("Sum of numbers from 1 to 9 is %d\n", result);
}

**Asseembly File load.s**

.section .text
.global load
.type load, @function

load:

add a4, a0, zero
add a2, a0, a1
add a3, a0, zero

loop:

add a4, a3, a4
addi a3, a3, 1
blt a3, a2, loop
add a0, a4, zero
ret

**Simulate C Program using Function Call**

**Compilation:** To compile C code and Asseembly file use the command

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o custom1to9.o custom1to9.c load.s

this would generate object file custom1to9.o.

Execution: To execute the object file run the command

spike pk custom1to9.o

![day2](https://github.com/KushalR17/pes_asic_class/assets/142383052/8fa408be-767c-4ac3-8f67-c99223f3d1a1)

**Lab to Run C-Program on RISCV-CPU**

git clone https://github.com/kunalg123/riscv_workshop_collaterals.git

cd riscv_workshop_collaterals

ls -ltr

cd labs

ls -ltr

chmod 777 rv32im.sh


./rv32im.sh




![day2a](https://github.com/KushalR17/pes_asic_class/assets/142383052/a3e822c9-699e-42ca-b91a-4645e4c91b2a)




