
**VLSI Physical Design for ASICs**

The objective of VLSI (Very Large Scale Integration) physical design for ASICs (Application-Specific Integrated Circuits) is to transform a logical design description (RTL - Register Transfer Level) into a physical layout that can be fabricated as an integrated circuit. This involves translating the high-level functional representation of the circuit into a physical implementation that meets design constraints, performance targets, and manufacturability requirements.

**Skill Outcomes**

    Architectural Design
    RTL Design / Behavioral Modeling
    Floorplanning
    Placement
    Clock Tree Synthesis
    Routing

**Installation**

You can find the necessary materials and scripts for this course on this GitHub repository. To get started:

    Download the run.sh script.
    Open your terminal.
    Navigate to your "Downloads" directory using the cd Downloads command.
    Run the script using ./run.sh.

# TABLE OF CONTENTS
## DAY 1 
**Introduction to RISCV ISA and GNU Compiler Toolchain**
+ [Introduction to Basic Keywords](#introduction-to-basic-keywords)
  - Introduction
  - From Apps to Hardware
  - Detail Description of Course Content
+ [Labwork for RISCV Toolchain](#labwork-for-riscv-toolchain)
  - C Program
  - RISCV GCC Compiler and Dissemble
  - Spike Simulation and Debug
+ [Integer Number Representation](#integer-number-representation) 
  - 64-bit Unsigned Numbers
  - 64-bit Signed Numbers
  - Labwork For Signed and Unsigned Numbers

## DAY 2 
**Introduction to ABI and Basic Verification Flow**
+ [Application Binary Interface](#application-binary-interface)
  - Introduction to ABI
  - Memory Allocation for Double Words
  - Load, Add and Store Instructions
  - 32-Registers and their ABI Names
+ [Labwork using ABI Function Calls](#labwork-using-abi-function-calls)
  - Algorithm for C Program using ASM
  - Review ASM Function Calls
  - Simulate C Program using Function Call
  - Lab to Run C-Program On RISCV-CPU

## DAY 3
**Introduction to Verilog RTL design and Synthesis**
+ [Introduction to Open-Source Simulator iVerilog](#introduction-to-open-source-simulator-iverilog)
   - Introduction to iVerilog Design Testbench
+ [Labs using iVerilog and GTKwave](#labs-using-iverilog-and-gtkwave)
   - Introduction to Lab
   - iVerilog GTKwave Part-1
   - iVerilog GTKwave Part-2
+ [Introduction to Yosys and Logic synthesis](#introduction-to-yosys-and-logic-synthesis)
   - Introduction to Yosys
   - Introduction to Logic Synthesis
+ [Labs using Yosys and Sky130 PDKs](#labs-using-yosys-and-sky130-pdks)
   - Yosys good mux
 
## DAY 4
**Timing Libs, Hierarchical vs Flat Synthesis and Efficient Flop Coding Styles**
+ [Introduction to Timing Dot Libs](#introduction-to-timing-dot-libs)
  - Introduction to Dot Lib
+ [Hierarchical vs Flat Synthesis](#hierarchical-vs-flat-synthesis)
  - Hierarchical Synthesis Flat Synthesis 
+ [Various Flop Coding Styles and Optimization](#various-flop-coding-styles-and-optimization)
  - Why Flops and Flop Coding Styles
  - Lab Flop Synthesis Simulations
  - Interesting Optimisations

## DAY 5
**Combinational and Sequential Optmizations**
+ [Introduction to Optimisations](#introduction-to-optimisations)
+ [Combinational Logic Optimisations](#combinational-logic-optimisations)
+ [Sequential Logic Optimisations](#sequential-logic-optimisations)
+ [Sequential Optimisations for Unused Outputs](#sequential-optimisations-for-unused-outputs)

## DAY 6
**GLS, Blocking vs Non-Blocking and Synthesis-Simulation Mismatch**
+ [GLS Synthesis-Simulation Mismatch and Blocking Non-Blocking Statements](#gls-synthesis-simulation-mismatch-and-blocking-non-blocking-statements)
  - GLS Concepts And Flow Using Iverilog
  - Synthesis Simulation Mismatch
  - Blocking And Non Blocking Statements In Verilog
  - Caveats With Blocking Statements
+ [Labs on GLS and Synthesis-Simulation Mismatch](#labs-on-gls-and-synthesis-simulation-mismatch)
+ [Labs on Synth-Sim Mismatch for Blocking Statement](#labs-on-synth-sim-mismatch-for-blocking-statement)






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

**DAY 3 LAB WORK**

**Introduction to open-source simulator iverilog**

**Simulato**r: RTL design is checked for adherence to the spec by simulating the design. Simulator is the tool used for simulating the design

**Design:** Design is the actual verilog codeor set of verilog codes which has the intended functionality to meet with the required specification
   
   iVerilog is an open-source Verilog simulator that facilitates testing and simulation of digital circuit designs described in the Verilog hardware description language (HDL). The simulator takes both the design and testbench as input and generates a vcd (value change dump) file. To visualize the vcd file's waveforms, we utilize a tool called GTKwave. 
![DAY31](https://github.com/KushalR17/pes_asic_class/assets/142383052/75c32850-4aa5-421d-ae24-c136f1b54d53)

**Testbench**: Testbench is the setup to apply stimulus to the design to check its functionality
How do simulator works?

   -> It looks for the changes in input signal
   ->upon change to the input the out put is evaluated
 ![DAY32](https://github.com/KushalR17/pes_asic_class/assets/142383052/06901daa-3223-4879-8602-f2349d45352b)

 **Labs using iverilog and gtkwave**

**Introduction to lab**

    Make new directory mkdie VSD
    git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
    This should create a folder sky130RTLDesignAndSynthesisWorkshop in VDS directory
    You could see two folders under sky130RTLDesignAndSynthesisWorkshop
        my_lib: It contains all the standard cell libraries and verilog module
        verilog_files: It contains all the source code and testbench required for the lab
![3a1](https://github.com/KushalR17/pes_asic_class/assets/142383052/0bdea365-9b4a-434b-8ba6-1dd2d31f160e)
![3a2](https://github.com/KushalR17/pes_asic_class/assets/142383052/d4956acf-4e7a-443a-8017-6074f756c82d)

**Introduction iverilog gtkwave**

    Go to verilog_files directory
    Load Design and Testbench using the command iverilog good_mux.v tb_good_mux.v

**good_mux.v**

module good_mux (input i0 , input i1 , input sel , output reg y);
always @ (*)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule

**tb_good_mux.v**

timescale 1ns / 1ps
module tb_good_mux;
	// Inputs
	reg i0,i1,sel;
	// Outputs
        wire y;

        // Instantiate the Unit Under Test (UUT)
	good_mux uut (
		.sel(sel),
		.i0(i0),
		.i1(i1),
		.y(y)
	);

	initial begin
	$dumpfile("tb_good_mux.vcd");
	$dumpvars(0,tb_good_mux);
	// Initialize Inputs
	sel = 0;
	i0 = 0;
	i1 = 0;
	#300 $finish;
	end

always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
endmodule
![3a3](https://github.com/KushalR17/pes_asic_class/assets/142383052/abebc936-2847-410d-b116-b48b561d0cbb)

    Upon loading sucessfully a.out will be generated
    Execute the generated file it would dump gtkwave tb_good_mux.vcd file
    Load the vcd file to simulator using the command gtkwave tb_good_mux.vcd
   ![3a4](https://github.com/KushalR17/pes_asic_class/assets/142383052/4f8cde6e-da83-497a-8c61-80bf52be81f4)
   
   **Introduction to Yosys and Logic synthesis**
   
**Introduction to yosys**

Yosys is an synthesizer which is used to convert RTL to netlist

 ![3a5](https://github.com/KushalR17/pes_asic_class/assets/142383052/b84d8a9d-eb62-4b6d-b6eb-47fba380b378)
 
 netlist is the representation of DESIGN in the form of standard cells present in .lib

    To verify synthesis Netlist need to be fed to iverilog along with testbench
    vcd file generated from iverilog need to be fed to gtkwave simulator
    The output we get should be same as the output we got during RTL simulator
![3a6](https://github.com/KushalR17/pes_asic_class/assets/142383052/619ff7d8-f801-4bcf-8225-4d322150a459)

**Introduction to logic synthesis**

Logic synthesis is a vital step in digital circuit design where high-level descriptions of circuits are transformed into specific implementations using logic gates. It optimizes circuits for factors like performance, area, power, and cost. The process includes library mapping, optimization, technology mapping, timing analysis, and verification. It's an iterative process often done with specialized software tools, enabling efficient hardware design.

.lib:

    Logic synthesis tools use a library of standard cells. These cells are predefined logic gates with different functionalities and characteristics
    It will also contain fast and slow version of same gate

why fast and slow version of same gate?

Fast and slow versions of gates are essential in digital circuit design to balance between clock frequency and timing constraints. Fast gates have shorter propagation delays and are used to reduce setup and hold time violations, allowing for higher clock frequencies. Slow gates, with longer delays, can be used to intentionally slow down critical paths or address timing issues. The Tclk formula helps calculate the maximum clock frequency while considering these factors


![3a7](https://github.com/KushalR17/pes_asic_class/assets/142383052/238dfab6-330c-441e-91b4-08f116df457a)


    t_setup: The setup time is the minimum time before the clock edge when the input data must be stable.
    t_hold: The hold time is the minimum time after the clock edge during which the input data must remain stable.
    t_propagation: This term represents the propagation delay of the logic gates in the critical path.
    Tcq: This term represents the clock-to-q delay of the flip-flops or registers used in the design. It's often a fixed value based on the chosen flip-flop technology.

**Lab using Yosys and Sky130 PDKs**

Steps to realize good_mux(design) in terms of standard cells avilable in library sky130_fd_sc_hd__tt_025C_1v80.lib

    Go to verilog_files directory

    once you get to verilog_files directory, Invoke yosys by using the command yosys
    

![3a8](https://github.com/KushalR17/pes_asic_class/assets/142383052/91c36086-d6c8-4a18-bc00-26fa2eea7ff9)

Read library: read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
Read design: read_verilog good_mux.v

![3a9](https://github.com/KushalR17/pes_asic_class/assets/142383052/86625627-e6ba-4d09-b41f-2d2297469fe0)

Synthesis: synth -top good_mux

![3a10](https://github.com/KushalR17/pes_asic_class/assets/142383052/63691b73-27ca-4d82-b0de-8adaac1fcace)

Generate netlist: abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

![3a11](https://github.com/KushalR17/pes_asic_class/assets/142383052/4cee9633-4df8-4dba-9619-f67ab0970173)

Logic realized: show

![3a12](https://github.com/KushalR17/pes_asic_class/assets/142383052/6f2b61c1-984b-43d7-a699-b1093c97f0c6)

Write netlist: write_verilog -noattr good_mux_netlist.v, !gvim good_mux_netlist.v

![3a13](https://github.com/KushalR17/pes_asic_class/assets/142383052/cc399c9e-335d-4828-80e5-3602c26c0a03)

**good_mux_netlist.v**

/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module good_mux(i0, i1, sel, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  input i0;
  wire i0;
  input i1;
  wire i1;
  input sel;
  wire sel;
  output y;
  wire y;
  sky130_fd_sc_hd__mux2_1 _4_ (
    .A0(_0_),
    .A1(_1_),
    .S(_2_),
    .X(_3_)
  );
  assign _0_ = i0;
  assign _1_ = i1;
  assign _2_ = sel;
  assign y = _3_;
endmodule

**DAY4 LAB WORK**

**Introduction to timing dot libs**

sky130_fd_sc_hd__tt_025C_1v80.lib

    sky130: This indicates that the library is associated with the SkyWater 130nm process technology. Process technology refers to the manufacturing process used to create integrated circuits (ICs) and determines factors like transistor size and performance characteristics.

    fd_sc_hd: These letters likely stand for different aspects of the library. "fd" might refer to "Foundation," suggesting that this library contains fundamental building blocks for digital IC design. "sc" could stand for "Standard Cells," which are pre-designed logic gates used in IC design. "hd" could refer to "high-density" libraries, which typically contain smaller, more compact cell designs for achieving higher logic density in ICs.

    tt_025C: This part of the name could refer to the library's operating conditions or temperature and voltage settings. "tt" might stand for "typical temperature," and "025C" could refer to 25 degrees Celsius, a common temperature for IC specifications. These conditions are important for characterizing the library's performance.

    1v80: This likely represents the supply voltage for the library. In this case, "1v80" indicates a supply voltage of 1.8 volts, which is a common voltage level for digital ICs.

**Libraries contain**

    Standard Cells: This library is likely to include a variety of standard cells, which are pre-designed building blocks for digital logic. Standard cells consist of logic gates (e.g., AND, OR, XOR), flip-flops, latches, multiplexers, and other fundamental digital components. These cells are characterized for the specific process technology (in this case, SkyWater 130nm) and operating conditions (temperature and voltage).

    Timing Information: The library will provide timing information for each standard cell. This information includes parameters like propagation delay, setup time, hold time, and other timing characteristics. Designers use this data to ensure that signals propagate correctly through the logic gates.

    Power Characteristics: Power consumption data is crucial for estimating the energy usage of a design. The library will typically include information on dynamic power (power consumed when the circuit is switching) and static power (power consumed when the circuit is idle).

    Pin and I/O Information: The library will specify the input and output pins for each standard cell, including pin names, directions (input or output), and electrical characteristics.

    Library Files: These library files often come in various formats, including Liberty (.lib) files, which contain detailed timing and power information, and Verilog models, which allow designers to use these standard cells in their digital designs.

    Characterization Data: The library may include data characterizing how the standard cells perform under different operating conditions, including variations in temperature and supply voltage. This helps designers account for variability in their designs.

    Technology Files: These files might also include information about the specific characteristics of the SkyWater 130nm process technology, such as transistor models, interconnect information, and other process-related data.

  
   **Lib files**
**commands used in terminal :**

gvim /path to the .lib file/

commands used in vim:

syn off // Switches off the highlighting of the syntax

se un  // used to enable the line numbers

/cell  // used to find a word cell

vsp   // Opens another window of the same file

**it contains:-**

    Conditions of PVT(Pressure Voltage Temperature) for proper working
    Default values/units
    time_unit : "1ns"; ** voltage_unit : "1V"; ** leakage_power_unit : "1nW"; ** current_unit : "1mA"; ** pulling_resistance_unit : "1kohm"; ** capacitive_load_unit(1.0000000000, "pf"); ** default_operating_conditions : "tt_025C_1v80";
    Standard cells
    Leakage powers of all the cells for different inputs
    About the technology("CMOS")


**.lib file:**

![3B20](https://github.com/KushalR17/pes_asic_class/assets/142383052/30ccd154-3b02-4838-8477-a322baf51a05)

**Different versions of the and2 gate:-**

**and2_0 :**

![3B21](https://github.com/KushalR17/pes_asic_class/assets/142383052/a3f10a92-4acd-4d12-8e47-8bb1b75ebd02)

**and2_2:**

![3B22](https://github.com/KushalR17/pes_asic_class/assets/142383052/a1d8e56b-9516-4ebf-8b98-203781daa5ad)

**and2_4:**

![3B23](https://github.com/KushalR17/pes_asic_class/assets/142383052/095136e0-2c73-4f75-bb97-4bf123077c36)

**Observation:-**

    In terms of area and power :- and2_4 > and2_2 > and2_0
    Wider cells occupy high area and consume high power and the delay is low
    smaller cells occupy low area and consume low power and the delay is high


**Hierarchical vs Flat Synthesis**

**Hierarchical Synthesis**

    Hierarchical synthesis involves dividing the design into logical modules or blocks and synthesizing each module separately.
    These modules can have their own hierarchies, and they communicate through well-defined interfaces
    It enhances reusability, as individual modules can be reused in other designs.
    Supports better scalability for large, complex designs.

**Steps to Hierarchical Synthesis**

    Go to verilog_files directory

    once you get to verilog_files directory, Invoke yosys by using the command yosys

    once yosys is invoked follow the above sequence of commands

    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
    read_verilog multiple_modules.v
    synth -top multiple_modules
    abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    show multiple_modules
    write_verilog -noattr multiple_modules_hier.v
    !gvim multiple_modules_hier.v
  ![3a14](https://github.com/KushalR17/pes_asic_class/assets/142383052/1057197d-fc33-4658-a4b4-4def82ad4013)
 
   
**multiple_modules_hier.v**

/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module multiple_modules(a, b, c, y);
  input a;
  wire a;
  input b;
  wire b;
  input c;
  wire c;
  wire net1;
  output y;
  wire y;
  sub_module1 u1 (
    .a(a),
    .b(b),
    .y(net1)
  );
  sub_module2 u2 (
    .a(net1),
    .b(c),
    .y(y)
  );
endmodule

module sub_module1(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__and2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

module sub_module2(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__or2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

**Flat Synthesis**

    In flat synthesis, the entire design is synthesized as a single, monolithic entity.
    All modules, submodules, and logic are flattened into a single level of hierarchy.
    This means that all components, regardless of their intended functionality, are combined into a single giant netlist
    Best suited for simple designs where complexity is low and maintainability isn't a significant concern.

**Steps to Flat Synthesis**

    Go to verilog_files directory

    once you get to verilog_files directory, Invoke yosys by using the command yosys

    once yosys is invoked follow the above sequence of commands

    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
    read_verilog multiple_modules.v
    synth -top multiple_modules
    abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    flatten
    show
    write_verilog -noattr multiple_modules_flat.v
    !gvim multiple_modules_flat.v


/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module multiple_modules(a, b, c, y);
  input a;
  wire a;
  input b;
  wire b;
  input c;
  wire c;
  wire net1;
  output y;
  wire y;
  sub_module1 u1 (
    .a(a),
    .b(b),
    .y(net1)
  );
  sub_module2 u2 (
    .a(net1),
    .b(c),
    .y(y)
  );
endmodule

module sub_module1(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__and2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

module sub_module2(a, b, y);
  wire _0_;
  wire _1_;
  wire _2_;
  input a;
  wire a;
  input b;
  wire b;
  output y;
  wire y;
  sky130_fd_sc_hd__or2_0 _3_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  assign _1_ = b;
  assign _0_ = a;
  assign y = _2_;
endmodule

**Flat Synthesis**

    In flat synthesis, the entire design is synthesized as a single, monolithic entity.
    All modules, submodules, and logic are flattened into a single level of hierarchy.
    This means that all components, regardless of their intended functionality, are combined into a single giant netlist
    Best suited for simple designs where complexity is low and maintainability isn't a significant concern.

**Steps to Flat Synthesis**

    Go to verilog_files directory

    once you get to verilog_files directory, Invoke yosys by using the command yosys

    once yosys is invoked follow the above sequence of commands

    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
    read_verilog multiple_modules.v
    synth -top multiple_modules
    abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    flatten
    show
    write_verilog -noattr multiple_modules_flat.v
    !gvim multiple_modules_flat.v
![3a15](https://github.com/KushalR17/pes_asic_class/assets/142383052/fba24d97-c95c-4698-beb5-e2c53a426f8f)

  
 multiple_modules_flat.v

/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module multiple_modules(a, b, c, y);
  wire _0_;
  wire _1_;
  wire _2_;
  wire _3_;
  wire _4_;
  wire _5_;
  input a;
  wire a;
  input b;
  wire b;
  input c;
  wire c;
  wire net1;
  wire \u1.a ;
  wire \u1.b ;
  wire \u1.y ;
  wire \u2.a ;
  wire \u2.b ;
  wire \u2.y ;
  output y;
  wire y;
  sky130_fd_sc_hd__and2_0 _6_ (
    .A(_1_),
    .B(_0_),
    .X(_2_)
  );
  sky130_fd_sc_hd__or2_0 _7_ (
    .A(_4_),
    .B(_3_),
    .X(_5_)
  );
  assign _4_ = \u2.b ;
  assign _3_ = \u2.a ;
  assign \u2.y  = _5_;
  assign \u2.a  = net1;
  assign \u2.b  = c;
  assign y = \u2.y ;
  assign _1_ = \u1.b ;
  assign _0_ = \u1.a ;
  assign \u1.y  = _2_;
  assign \u1.a  = a;
  assign \u1.b  = b;
  assign net1 = \u1.y ;
endmodule

**Various Flop Coding Styles and optimization**

**Flop coding styles**

**Asynchronous Reset D Flip-Flop**

    When an asynchronous reset input is activated (set to '1'), regardless of the clock signal, the stored value is forced to '0'.
    Otherwise, on the positive edge of the clock signal, the stored value is updated with the data input.

dff_asyncres_syncres.v

module dff_asyncres_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
always @ (posedge clk , posedge async_reset)
begin
	if(async_reset)
		q <= 1'b0;
	else if (sync_reset)
		q <= 1'b0;
	else	
		q <= d;
end
endmodule

**Asynchronous Set D Flip-Flop**

    When an asynchronous set input is activated (set to '1'), regardless of the clock signal, the stored value is forced to '1'.
    Otherwise, on the positive edge of the clock signal, the stored value is updated with the data input.

dff_async_set.v

module dff_async_set ( input clk ,  input async_set , input d , output reg q );
always @ (posedge clk , posedge async_set)
begin
	if(async_set)
		q <= 1'b1;
	else	
		q <= d;
end
endmodule

**Synchronous Reset D Flip-Flop**

    When a synchronous reset input is activated (set to '1') at the positive edge of the clock signal, the stored value is forced to '0'.
    Otherwise, on the positive edge of the clock signal, the stored value is updated with the data input.

dff_syncres.v

module dff_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
always @ (posedge clk )
begin
	if (sync_reset)
		q <= 1'b0;
	else	
		q <= d;
end
endmodule

**D Flip-Flop with Asynchronous Reset and Synchronous Reset**

    This flip-flop combines both asynchronous and synchronous reset features.
    When the asynchronous reset input is activated (set to '1'), the stored value is immediately forced to '0'.
    When the synchronous reset input is activated (set to '1') at the positive edge of the clock signal, the stored value is forced to '0'.
    Otherwise, on the positive edge of the clock signal, the stored value is updated with the data input.

dff_asyncres_syncres.v

module dff_asyncres_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
always @ (posedge clk , posedge async_reset)
begin
	if(async_reset)
		q <= 1'b0;
	else if (sync_reset)
		q <= 1'b0;
	else	
		q <= d;
end
endmodule

Flop synthesis simulations

Asynchronous Reset D Flip-Flop

**Simulation**

Go to verilog_files directory where the design and test_bench are present

Run the following commands to simulate dff_asyncres.v

iverilog dff_asyncres.v tb_dff_asyncres.v
./a.ot
gtkwave tb_dff_asyncres.vcd

![3a15](https://github.com/KushalR17/pes_asic_class/assets/142383052/a098cb26-eaad-4602-ba01-1e07c0616336)
![3a16](https://github.com/KushalR17/pes_asic_class/assets/142383052/22a57aae-31cf-4122-b5f8-1063ddbaf8b5)

**Synthsis**

Go to verilog_files directory and invoke yosys

Once you invoke yosys, Run following commands to Synthsis dff_asyncres

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_asyncres.v
  synth -top dff_asyncres
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show

![3a17](https://github.com/KushalR17/pes_asic_class/assets/142383052/997bc0fc-7972-4dfa-9867-fdce91178b2b)

**Asynchronous set D Flip-Flop**

**Simulation**

Go to verilog_files directory where the design and test_bench are present

Run the following commands to simulate dff_async_set.v

iverilog dff_async_set.v tb_dff_async_set.v
./a.ot
gtkwave tb_dff_async_set.vcd

![3a18](https://github.com/KushalR17/pes_asic_class/assets/142383052/738b9856-fae3-4e8d-9d29-1e8fdc937575)

**Synthsis**

Go to verilog_files directory and invoke yosys

Once you invoke yosys, Run following commands to Synthsis dff_async_set

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_async_set.v
  synth -top dff_async_set
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
  

![3a19](https://github.com/KushalR17/pes_asic_class/assets/142383052/415b978d-e7e1-4958-95f9-d98d9d55297f)

**Asynchronous Reset D Flip-Flop**

Simulation

Go to verilog_files directory where the design and test_bench are present

Run the following commands to simulate dff_syncres.v

iverilog dff_asyncres.v tb_dff_syncres.v
./a.ot
gtkwave tb_dff_syncres.vcd

![3a20](https://github.com/KushalR17/pes_asic_class/assets/142383052/88872bc0-fcb2-4ee0-9781-7d14b0fe50dd)

**Synthsis**

Go to verilog_files directory and invoke yosys

Once you invoke yosys, Run following commands to Synthsis dff_syncres

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_syncres.v
  synth -top dff_syncres
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
![3a21](https://github.com/KushalR17/pes_asic_class/assets/142383052/746761ee-cebf-46b9-bfd2-99c9c7d8d071)

**Interesting optimisations**

**mult_2.v**

module mul2 (input [2:0] a, output [3:0] y);
	assign y = a * 2;
endmodule

Synthsis

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog mult_2.v
synth -top mul2
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
write_verilog -noattr mul2_netlist.v
!gvim mul2_netlist.v

![3a22](https://github.com/KushalR17/pes_asic_class/assets/142383052/d1506de4-8f53-434e-b736-dd670d6f2ac5)

**mul2_netlist.v**

/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module mul2(a, y);
  input [2:0] a;
  wire [2:0] a;
  output [3:0] y;
  wire [3:0] y;
  assign y = { a, 1'h0 };
endmodule

**mult_8.v**

module mult8 (input [2:0] a , output [5:0] y);
	assign y = a * 9;
endmodule

**Synthesis**

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog mult_2.v
synth -top mult8
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
write_verilog -noattr mult8_netlist.v
!gvim mult8_netlist.v

![3a23](https://github.com/KushalR17/pes_asic_class/assets/142383052/d5793a18-9ed3-4759-beb3-fe699d362fb8)

**mult8_netlist.v**

/* Generated by Yosys 0.32+51 (git sha1 6405bbab1, gcc 12.3.0-1ubuntu1~22.04 -fPIC -Os) */

module mult8(a, y);
  input [2:0] a;
  wire [2:0] a;
  output [5:0] y;
  wire [5:0] y;
  assign y = { a, a };
endmodule

**DAY 5**
**Introduction to optimizations**

**Combinational optimization**
    
Combinational optimization is a branch of mathematical optimization that focuses on selecting the best combination of discrete options to optimize a given function.
        
	   Two methods within computational optimization are:
            Constant Propagation: This technique identifies and replaces variables or expressions with their constant values, reducing redundancy in code and improving performance.
            Boolean Optimization: This method simplifies boolean expressions or logic circuits by reducing the number of logical gates or terms while preserving the same logical behavior, which is useful in digital circuit design and                                         logical reasoning.

**Sequential logic optimization**

Sequential logic optimization is the process of enhancing the performance and efficiency of digital circuits containing flip-flops and state elements.

Methods under this optimization umbrella include:
     Sequential Constant Propagation: Identifies and propagates constant values through flip-flops to reduce redundant state transitions.
     State Optimization: Reduces the number of states in finite state machines (FSMs) by merging equivalent states, simplifying the circuit.
     Sequential Logic Cloning: Replicates portions of sequential logic to alleviate bottlenecks and improve circuit throughput.
     Retiming: Adjusts the placement of flip-flops within a circuit to optimize timing, balance critical paths, and enhance overall performance.

**Combinational logic optimizations**

**opt_check.v**

module opt_check (input a , input b , output y);
	assign y = a?b:0;
endmodule

**Synthesis**

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog opt_check.v
synth -top opt_check
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
![3a24](https://github.com/KushalR17/pes_asic_class/assets/142383052/9cff10d0-9c52-487a-aed3-e2864426e094)

**opt_check2.v**

module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
endmodule

**synthesis**

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog opt_check2.v
synth -top opt_check2
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
![3a25](https://github.com/KushalR17/pes_asic_class/assets/142383052/5d178cda-4ed0-4f1f-961c-bb1bda355dcd)

**multiple_module_opt.v**

module sub_module1(input a , input b , output y);
 assign y = a & b;
endmodule


module sub_module2(input a , input b , output y);
 assign y = a^b;
endmodule


module multiple_module_opt(input a , input b , input c , input d , output y);
wire n1,n2,n3;

sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
sub_module2 U3 (.a(b), .b(d) , .y(n3));

assign y = c | (b & n1); 


endmodule

**Synthesis**

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
read_verilog multiple_module_opt.v
synth -top multiple_module_opt
flatten
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

![3a26](https://github.com/KushalR17/pes_asic_class/assets/142383052/539cee25-c321-4fd0-96db-199341104a15)

**Sequential logic optimizations**

**dff_const1.v**

module dff_const1(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b0;
	else
		q <= 1'b1;
end

endmodule

Simulate

iverilog dff_const1.v tb_dff_const1.v
./a.out
gtkwave tb_dff_const1.vcd

![3a27](https://github.com/KushalR17/pes_asic_class/assets/142383052/7ec70de9-53f2-4e17-b8d1-68c3db275b99)
![3a27](https://github.com/KushalR17/pes_asic_class/assets/142383052/422ef24b-3736-4dc1-806a-21d33daac2ad)

 **Synthesis**

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_const1.v
  synth -top dff_const1
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show

![3a28](https://github.com/KushalR17/pes_asic_class/assets/142383052/72ca54e9-9a7d-44ba-88dc-4bd615fc6e9c)

**dff_const2.v**

module dff_const2(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end

endmodule

Simulate

iverilog dff_const1.v tb_dff_const2.v
./a.out
gtkwave tb_dff_const2.vcd

![3a29](https://github.com/KushalR17/pes_asic_class/assets/142383052/125076b0-5332-4ebf-8451-43f50d92f03d)

**Synthesis**

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_const2.v
  synth -top dff_const2
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
![3a30](https://github.com/KushalR17/pes_asic_class/assets/142383052/9468275e-9718-49be-9135-3d78ad263b6f)

**dff_const3.v**

module dff_const3(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule

Simulate

iverilog dff_const3.v tb_dff_const2.v
./a.out
gtkwave tb_dff_const3.vcd

![3a31](https://github.com/KushalR17/pes_asic_class/assets/142383052/b37d32df-9289-4ee2-9d91-1b2b742742f8)

**Synthesis**

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog dff_const3.v
  synth -top dff_const3
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
![3a32](https://github.com/KushalR17/pes_asic_class/assets/142383052/242eb0df-d58d-4b11-94f0-c85e0f6331d3)

**Sequential optimzations for unused outputs**

**counter_opt.v**

module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = count[0];

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule

Synthesis

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog counter_opt.v
  synth -top counter_opt
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
  
![3a33](https://github.com/KushalR17/pes_asic_class/assets/142383052/685f79a8-8d4b-4d15-bfe3-b6956891e71c)

**counter_opt2.v**

module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = (count[2:0] == 3'b100);

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule

**Synthesis**

  read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  
  read_verilog counter_opt2.v
  synth -top counter_opt
  dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
  abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  show
![3a34](https://github.com/KushalR17/pes_asic_class/assets/142383052/53955a0b-6c73-43a7-9a3e-bfa443025abf)

**DAY-6**

**GLS Synthesis-Simulation mismatch and Blocking Non-blocking statements**

**GLS Concepts And Flow Using Iverilog**

**Gate level simulation**

    Gate-level simulation is a method used in electronics design to test and verify digital circuits at the level of individual logic gates and flip-flops.
    It's crucial for checking functionality, timing, power consumption, and generating test patterns for integrated circuits.
    It operates at a lower abstraction level than higher-level simulations and is essential for debugging and ensuring circuit correctness.

**To perform gate-level simulation using Icarus Verilog (iverilog):**

    Write RTL code.
    Synthesize to generate gate-level netlist.
    Create a testbench in Verilog.
    Compile both netlist and testbench.
    Run simulation with compiled files.Debug and iterate as needed.
    Perform timing analysis if necessary.
    Generate test vectors for manufacturing tests.

**Synthesis-Simulation mismatch**

    Synthesis-simulation mismatch is when there are differences between how a digital circuit behaves in simulation at the RTL level and how it behaves after gate-level synthesis.
    This can occur due to optimization, clock domain issues, library differences, or other factors.
    To address it, ensure consistent tool versions, check synthesis settings, debug with simulation tools, and follow best practices in RTL coding and design.
    Resolving these mismatches is crucial for reliable hardware implementation.

**Blocking And Non-Blocking Statements**

**Blocking Statements**

    Blocking statements execute sequentially in the order they appear within a procedural block or always block.
    When a blocking assignment or operation is encountered, the simulation halts and waits for it to complete before moving on to the next statement.
    Blocking assignments are typically used to describe combinational logic, where the order of execution doesn't matter, and each assignment depends on the previous one.

Example (Blocking Assignment): a = b + c; // b and c must be known before calculating 'a'

**Non-Blocking Statements**

    Non-blocking statements allow concurrent execution within a procedural block or always block, making them suitable for describing synchronous digital circuits.
    When a non-blocking assignment or operation is encountered, the simulation does not wait for it to complete. Instead, it schedules the assignments to occur in parallel.
    Non-blocking assignments are typically used to model sequential logic, like flip-flops and registers, where parallel execution is required.

Example (Non-Blocking Assignment):

always @(posedge clk)
  begin
    b <= a; // Concurrently scheduled assignment
    c <= b; // Concurrently scheduled assignment
  end

**Caveats With Blocking Statements**

Caveats with blocking statements in hardware description languages like Verilog include:

    Sequential Execution: Blocking statements execute sequentially, which may not accurately represent concurrent hardware behavior in the design.

    Order Dependency: The order of blocking statements can affect simulation results, leading to race conditions or unintended behavior.

    Combinational Logic Only: Blocking statements are primarily used for modeling combinational logic, making them less suitable for sequential or synchronous logic.

    Limited for Testbenches: In testbench code, excessive use of blocking statements can lead to simulation race conditions that don't reflect real-world hardware behavior.

    Initialization Issues: In some cases, initializing variables with blocking assignments can lead to unexpected results due to order-dependent initialization.

To mitigate these issues, designers often use non-blocking statements for modeling sequential logic and adopt good coding practices to minimize order dependencies and improve code clarity.
Labs on GLS and Synthesis-Simulation Mismatch

**ternary_operator_mux.v**

module ternary_operator_mux (input i0 , input i1 , input sel , output y);
	assign y = sel?i1:i0;
endmodule

**RTL Simulation**

iverilog ternary_operator_mux.v tb_ternary_operator_mux.v
./a.out
gtkwave tb_ternary_operator_mux.vcd

![3b1](https://github.com/KushalR17/pes_asic_class/assets/142383052/daa48f11-54a7-4b62-8af1-06a61db70c8d)
![3a35](https://github.com/KushalR17/pes_asic_class/assets/142383052/404d4d79-b4ed-4349-99dc-7a5b06708d6e)

Synthesis

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog ternary_operator_mux.v
synth -top ternary_operator_mux
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
write_verilog -noattr ternary_operator_mux_netlist.v
show

![3a36](https://github.com/KushalR17/pes_asic_class/assets/142383052/d33092e4-519e-4aee-b107-f7b17847b1d8)

**GLS**  To to Gate level simulation, Invoke iverilog with verilog modules

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_netlist.v tb_ternary_operator_mux.v
./a.out
gtkwave tb_ternary_operator_mux.vcd
![3a37](https://github.com/KushalR17/pes_asic_class/assets/142383052/365ae318-e6ce-455d-81a4-8492d1b64712)

**bad_mux.v**

module bad_mux (input i0 , input i1 , input sel , output reg y);
always @ (sel)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule

**RTL Simulation**

iverilog bad_mux.v tb_bad_mux.v
./a.out
gtkwave tb_bad_mux.vcd

![3a38](https://github.com/KushalR17/pes_asic_class/assets/142383052/eed69300-2baa-437f-ac72-367792e1eb80)

Synthesis

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog bad_mux.v
synth -top bad_mux
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
write_verilog -noattr bad_mux_netlist.v
show
![3a39](https://github.com/KushalR17/pes_asic_class/assets/142383052/d46bb015-6761-4d7c-88d5-08cd896d0800)

**GLS** To to Gate level simulation, Invoke iverilog with verilog modules

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_netlist.v tb_bad_mux.v
./a.out
gtkwave tb_bad_mux.vcd

![3a40](https://github.com/KushalR17/pes_asic_class/assets/142383052/a707ba7b-a6e2-44c9-b453-0708849623db)

**Labs on synth-sim mismatch for blocking statement**

blocking_caveat.v

module blocking_caveat (input a , input b , input  c, output reg d); 
reg x;
always @ (*)
begin
	d = x & c;
	x = a | b;
end
endmodule

RTL Simulation

iverilog blocking_caveat.v tb_blocking_caveat.v
./a.out
gtkwave tb_blocking_caveat.vcd

![3b12](https://github.com/KushalR17/pes_asic_class/assets/142383052/d39e229e-38d9-449b-8df4-8055afe155d2)
![3a41](https://github.com/KushalR17/pes_asic_class/assets/142383052/4be23e61-9d81-40b9-87af-10388428e6cc)

Synthesis

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog blocking_caveat.v
synth -top blocking_caveat
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
write_verilog -noattr blocking_caveat_netlist.v
show
![3a42](https://github.com/KushalR17/pes_asic_class/assets/142383052/cd9b6cf6-a9e0-4363-a568-96d00bab12bd)

**GLS To** to Gate level simulation, Invoke iverilog with verilog modules

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_netlist.v tb_blocking_caveat.v
./a.out
gtkwave tb_blocking_caveat.vcd

![3a43](https://github.com/KushalR17/pes_asic_class/assets/142383052/bae462f5-3534-4456-a561-286383b2ff49)





   






