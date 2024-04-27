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


![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/riscv%20toolchain%20configure.png)

**step3**: Installation of yosys.

- sudo apt update
sudo apt install build-essential clang bison flex \
                 libreadline-dev gawk tcl-dev libffi-dev \
                 git mercurial graphviz xdot pkg-config \
                 python3 libboost-system-dev \
                 libboost-python-dev libboost-filesystem-dev


![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/yosys%20build.png)

- verification of yosys

![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/yosys%20build2.png)

**step4**: Installation of iverilog.

- sudo apt-get install iverilog

![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/iverilog.png)

**step5**:Installation of gtkwave.
- sudo apt update
sudo apt install gtkwave


**TASK 2**

- Introduction
RISCV
RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computing (RISC) principles. It's designed to be simple, modular, and extensible, allowing for a wide range of implementations. RISC-V is gaining popularity in academia and industry due to its open nature, which enables anyone to design, manufacture, and sell RISC-V chips and software without paying royalties.

ISA and Non ISA
Basically, ISA refers to the instruction set architecture, which defines the interface between software and hardware, while "non-ISA" is not a standard term but could potentially refer to other aspects of system or processor design.

Privileged and unprivileged code
Code can execute as privileged or unprivileged. Unprivileged execution limits or excludes access to some resources. Privileged execution has access to all resources. Handler mode is always privileged. Thread mode can be privileged or unprivileged.
The microprocessors have two execution modes: Handler mode and Thread mode. The processor always enters the Handler mode when an interrupt or CPU exception is raised. The processor is in thread state when it is executing background (noninterrupt) code.




- INSTRUCTIONS GIVEN TO US

1)	add r6, r2, r1 :
In RISC-V assembly language, the instruction `add r6, r2, r1` performs an addition operation. Here's a breakdown of the instruction:
- `add`: This is the mnemonic for the addition operation.
- `r6`, `r2`, `r1`: These are registers in the RISC-V architecture. Registers are small, fast storage locations within the CPU. `r6` is the destination register where the result of the addition will be stored, and `r2` and `r1` are the source registers containing the values to be added.
So, the instruction `add r6, r2, r1` adds the values in registers `r2` and `r1` and stores the result in register `r6`.

2)	Sub r7,r1,r2 : 
This instruction subtracts the value in register `r2` from the value in register `r1` and stores the result in register `r7`. For example, if `r1` contains 10 and `r2` contains 5, then after this instruction, `r7` will contain 5 (10 - 5).

3)	And r8,r1,r3 : 
This instruction performs a bitwise AND operation between the values in registers `r1` and `r3`, and stores the result in register `r8`. Each bit in the result is 1 if and only if both corresponding bits in `r1` and `r3` are 1. For example, if `r1` contains 1010 (decimal 10) and `r3` contains 1100 (decimal 12), then `r8` will contain 1000 (decimal 8).

4)	Or r9,r2,r5 : 
This instruction performs a bitwise OR operation between the values in registers `r2` and `r5`, and stores the result in register `r9`. Each bit in the result is 1 if either or both corresponding bits in `r2` and `r5` are 1. For example, if `r2` contains 1010 (decimal 10) and `r5` contains 1100 (decimal 12), then `r9` will contain 1110 (decimal 14).

5) Xor r10,r1,r4 :
This instruction performs a bitwise XOR (exclusive OR) operation between the values in registers `r1` and `r4`, and stores the result in register `r10`. Each bit in the result is 1 if the corresponding bits in `r1` and `r4` are different, and 0 otherwise. For example, if `r1` contains 1010 (decimal 10) and `r4` contains 1100 (decimal 12), then `r10` will contain 0110 (decimal 6).

6) Slt r11,r2,r4 :
This instruction sets register `r11` to 1 if the value in register `r2` is less than the value in register `r4`, and sets it to 0 otherwise. This is a set-on-less-than operation. For example, if `r2` contains 5 and `r4` contains 7, then `r11` will be set to 1.

7) Addi r12,r4,5 :
This instruction adds immediate value 5 to the value in register `r4` and stores the result in register `r12`. For example, if `r4` contains 10, then after this instruction, `r12` will contain 15 (10 + 5).

8) Sw r3,r1,3 :
This instruction stores the value in register `r3` to the memory address calculated as the sum of the value in register `r1` and immediate value 3. This is a store word operation, where a word is typically 32 bits or 4 bytes.

9) Lq r13,r1,2 :
This instruction loads a quad-word (64 bits) from the memory address calculated as the sum of the value in register `r1` and immediate value 2, and stores it in register `r13`. This is a load quad-word operation.

10) Beq r0,r0,15 :
This instruction is a branch instruction that always branches to the instruction located 15 instructions ahead. This is a way to implement a jump or loop in the code.

11) Bne r0,r1,20 :
This instruction is a branch instruction that branches to the instruction located 20 instructions ahead if the values in registers `r0` and `r1` are not equal. This is a way to implement a conditional branch based on a comparison.

12) Sll r15,r1,r2(2) :
This instruction shifts the value in register `r1` left by the amount specified in the lower 5 bits of register `r2`, and stores the result in register `r15`. This is a logical left shift operation. The `(2)` indicates a shift amount of 2 bits.

13) Srl r16,r14,r2(2) :
This instruction shifts the value in register `r14` right by the amount specified in the lower 5 bits of register `r2`, and stores the result in register `r16`. This is a logical right shift operation. The `(2)` indicates a shift amount of 2 bits.
![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave1.png)

- verification of gtwave

![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave2.png)
