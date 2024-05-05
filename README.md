# vsdsquadron-mini-internship

  **TASK 1**
  
**step1**: install oracle VM and set up ubuntu.

![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/s1.png)

**step2**: Install risc-v toolchain.
- Installation of necessary dependencies
sudo apt update
sudo apt install autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev

- Clone the repository to your preferred location
git clone https://github.com/riscv/riscv-gnu-toolchain

- Navigate to the riscv-gnu-toolchain directory and run the configure script with the installation prefix:
./configure --prefix=/opt/riscv


<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/riscv%20toolchain%20configure.png">

**step3**: Installation of yosys.

- sudo apt update
sudo apt install build-essential clang bison flex \
                 libreadline-dev gawk tcl-dev libffi-dev \
                 git mercurial graphviz xdot pkg-config \
                 python3 libboost-system-dev \
                 libboost-python-dev libboost-filesystem-dev


<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/yosys%20build.png">

- verification of yosys

<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/yosys%20build2.png">

**step4**: Installation of iverilog.

- sudo apt-get install iverilog

<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/iverilog.png">

**step5**:Installation of gtkwave.
- sudo apt update
sudo apt install gtkwave

<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave1.png">

- verification of gtwave

<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave2.png">


**TASK 2**

- Introduction
RISCV
RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computing (RISC) principles. It's designed to be simple, modular, and extensible, allowing for a wide range of implementations. RISC-V is gaining popularity in academia and industry due to its open nature, which enables anyone to design, manufacture, and sell RISC-V chips and software without paying royalties.

ISA and Non ISA
Basically, ISA refers to the instruction set architecture, which defines the interface between software and hardware, while "non-ISA" is not a standard term but could potentially refer to other aspects of system or processor design.

Privileged and unprivileged code
Code can execute as privileged or unprivileged. Unprivileged execution limits or excludes access to some resources. Privileged execution has access to all resources. Handler mode is always privileged. Thread mode can be privileged or unprivileged.
The microprocessors have two execution modes: Handler mode and Thread mode. The processor always enters the Handler mode when an interrupt or CPU exception is raised. The processor is in thread state when it is executing background (noninterrupt) code.

**First let us learn about the instruction types used in RISCV:**
RISC-V is a 32-bit instruction set architecture (ISA) that has six core instruction formats: B, I, S, SB, U, and J. These formats are used to encode different types of instructions, including register-register, register-immediate, store, branch, and jump instructions.
- R type:
  This is the register type, these instructions use register-]-register format where instruction specifies two registers and a function code. This performs arithematic code, logical and shift operations. Example- add, sub, null, & and.
  
- I type:
    Register immediate type. These have a register and an immediate value. Example- addi, slti, lui

    What are load and store instructions?
   1. Load: data is moved from memory to reg., data is read from memory to location and stored in a register for further process.
   2. Store: this operation involves transfer from register to memory; data is written from register to memory.

- J type:
These instructions ue jump format, where instruction specifies a target address; causes program control to a different part of pragram.
 Always executes jump instruction regargless of the conditions.

- B type:
 Transfers program control to specific memory address based on condition or flag. It ia a conditional instruction example- beq, bne

- S type:
 These use store format, instruction specifies register and memory address.

- U type:
These use load format, instruction soecifies reg., and memory address.


- **INSTRUCTIONS GIVEN TO US**

1)	add r6, r2, r1 :
In RISC-V assembly language, the instruction `add r6, r2, r1` performs an addition operation. Here's a breakdown of the instruction:
- `add`: This is the mnemonic for the addition operation.
- `r6`, `r2`, `r1`: These are registers in the RISC-V architecture. Registers are small, fast storage locations within the CPU. `r6` is the destination register where the result of the addition will be stored, and `r2` and `r1` are the source registers containing the values to be added.
So, the instruction `add r6, r2, r1` adds the values in registers `r2` and `r1` and stores the result in register `r6`.

<img src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/add.jpg" width="450">

32-bit code:
0000000 01001 01010 000 00110 0110011


2)	Sub r7,r1,r2 : 
This instruction subtracts the value in register `r2` from the value in register `r1` and stores the result in register `r7`. For example, if `r1` contains 10 and `r2` contains 5, then after this instruction, `r7` will contain 5 (10 - 5).

<img src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/sub.jpg" width="450">


32-bit code:
0000000 01010 01001 000 00111 0110011


similarly for the following instructions -

3)	And r8,r1,r3 : 
This instruction performs a bitwise AND operation between the values in registers `r1` and `r3`, and stores the result in register `r8`. Each bit in the result is 1 if and only if both corresponding bits in `r1` and `r3` are 1. For example, if `r1` contains 1010 (decimal 10) and `r3` contains 1100 (decimal 12), then `r8` will contain 1000 (decimal 8).

32-bit code:
0000000 00011 00001 111 00100 0110011

5)	Or r9,r2,r5 : 
This instruction performs a bitwise OR operation between the values in registers `r2` and `r5`, and stores the result in register `r9`. Each bit in the result is 1 if either or both corresponding bits in `r2` and `r5` are 1. For example, if `r2` contains 1010 (decimal 10) and `r5` contains 1100 (decimal 12), then `r9` will contain 1110 (decimal 14).

32-bit code:
0000000 00101 00010 110 01001 0110011

6) Xor r10,r1,r4 :
This instruction performs a bitwise XOR (exclusive OR) operation between the values in registers `r1` and `r4`, and stores the result in register `r10`. Each bit in the result is 1 if the corresponding bits in `r1` and `r4` are different, and 0 otherwise. For example, if `r1` contains 1010 (decimal 10) and `r4` contains 1100 (decimal 12), then `r10` will contain 0110 (decimal 6).

32-bit code:
0000000 00100 00001 100 01010 0110011

8) Slt r11,r2,r4 :
This instruction sets register `r11` to 1 if the value in register `r2` is less than the value in register `r4`, and sets it to 0 otherwise. This is a set-on-less-than operation. For example, if `r2` contains 5 and `r4` contains 7, then `r11` will be set to 1.

32-bit code:
0000000 00100 00010 010 01111 0110011

9) Addi r12,r4,5 :
This instruction adds immediate value 5 to the value in register `r4` and stores the result in register `r12`. For example, if `r4` contains 10, then after this instruction, `r12` will contain 15 (10 + 5).

32-bit code:
0000000 00000 00100 000 01100 0010011

10) Sw r3,r1,3 :
This instruction stores the value in register `r3` to the memory address calculated as the sum of the value in register `r1` and immediate value 3. This is a store word operation, where a word is typically 32 bits or 4 bytes.

32-bit code:
0000000 00001 00011 010 00000 0100011

11) Lq r13,r1,2 :
This instruction loads a quad-word (64 bits) from the memory address calculated as the sum of the value in register `r1` and immediate value 2, and stores it in register `r13`. This is a load quad-word operation.

32-bit code:
0000000 00010 00001 110 00000 0000011

12) Beq r0,r0,15 :
This instruction is a branch instruction that always branches to the instruction located 15 instructions ahead. This is a way to implement a jump or loop in the code.

32-bit code:
0000000 00000 00000 000 00000 1100011

13) Bne r0,r1,20 :
This instruction is a branch instruction that branches to the instruction located 20 instructions ahead if the values in registers `r0` and `r1` are not equal. This is a way to implement a conditional branch based on a comparison.

32-bit code:
0000000 00001 00000 001 01000 1100011

14) Sll r15,r1,r2(2) :
This instruction shifts the value in register `r1` left by the amount specified in the lower 5 bits of register `r2`, and stores the result in register `r15`. This is a logical left shift operation. The `(2)` indicates a shift amount of 2 bits.

32-bit code:
0000000 00010 00001 001 01111 0010011

15) Srl r16,r14,r2(2) :
This instruction shifts the value in register `r14` right by the amount specified in the lower 5 bits of register `r2`, and stores the result in register `r16`. This is a logical right shift operation. The `(2)` indicates a shift amount of 2 bits.

32-bit code:
0000000 01110 00014 101 10000 0010011





**TASK 3**

 Part1: C lab
 
**Code#1: SUM of digits from 1 to n**

_Step1_- open terminal in ubuntu

Type the following command to ensure we are in the home directory

       cd

_Step2_- 
This code opens leafpad editor which we use to write simple codes in.

       leafpad sum1ton

In this case "sum1ton' is the name of file of editor we want to open.
If we want to name our file "abcd" then type 

       leafpad abcd

So, this step will open up the editor where you can type your codes.

_Step3_- We want to create a code which calculates sum of numbers from 1 to n

        #include <stdio.h>
               int main() {
               int i, sum=0, n=5;
               for (i = 1 ; i <= n; ++i) {
                      sum += i;
               }
               printf("sum of numbers from 1 to %d is %d", n, sum);
               return 0;
               }

_Step4_- open up terminal and run the following 

       gcc sum1ton.c

(Note- Here, "sum1ton" is your file name, so replace it with your file name)
 - Explanation- 'gcc' command used mostly in Unix operating systems stands for "GNU compiler collection". So, basically when we run 'gcc' in a terminal or command prompt window, it compiles C, C++ and many other programming language source codes into executable programs(basically translates human language to machine readable code that computer can execute directly).

_Step5_- Run 

        ls -ltr

This code helps us to list compiled executables, helps to view compilation output and to check compilation status.

_Step6_-

       ./a.out

This is used to execute the compiled program named "a.out" in present directory. 
"./" specifies that we want to run the particular program located at present or current directory.
"a.out" is default name given to executable file.

_Note_: If we want to give a different name for the executable file run this -

       gcc abc_name source_code.c
here 'abc' is the name of the executable file, which followed by name of source code to be compiled

_Step7_- Output

**You should get the following output**

<img width="400" alt="Screenshot 2024-04-28 231824" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/assets/121378763/7fbb2254-3e2c-4bc4-a031-b518e98f1468">




**Code#2: sum of n numbers when the input 'n' is given by user**

The output is as follows-

<img width="400" alt="user input sum" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/assets/121378763/5ca41d8f-fd84-4ad7-a9ed-87907f78b74e">




PART2: RISCV LABS

Instruction 1- 

    riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=riscv64i -o sum1ton.o sum1ton.c

<IMG width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/main.png">


Instruction 2-

     riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv641 -o sum1ton.o sum1ton.c

<img width="400" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/MAIN2.png">


- `-O1` makes your code faster by applying basic optimizations, but it's careful not to change the code too much, so it's easier to understand and debug.
- `-Ofast` makes your code even faster by using more aggressive optimizations, but it might change the code in ways that make it harder to understand or debug.
- A more aggressive level means the compiler will take more liberties in restructuring the code to make it run faster, potentially at the cost of making the code harder to debug or deviating from the original source code's behavior.



**Task 4**

 Until now we saw the output of command "./a.out" for "gcc<program>".
 Now we will be learning about output of spike simulator. The spike simlator output is said to be verified if it is same as "./a.out" output.
Spike is a RISC-V ISA simulator used for running RISC-V assembly programs.

STEP 1:

<img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/spike1.png">

 STEP 2: to check next instructions

 <img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/next%20instructions.png" >

 STEP 3: To check contents of reg a0
 
 We see that in our main function we have the following list-
 
 <img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/MAIN2.png">
 
 Now to check the contents of reg a0-

 <img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/contents%20of%20reg%20a0.png">

 STEP 4: To check contents of reg a0 after lui-

 <img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/contents%20of%20a0%20after%20lui.png">

 Step 5: to check stack pointer contents

<img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/uploadthis_stack%20pointer.png">

 

 
