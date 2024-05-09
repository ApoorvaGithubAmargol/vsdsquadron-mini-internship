<span style="font-size:larger;"> **TASK 5** </span>

RISC-V instruction using Verilog

- In this task we will be executing basic RISC-V instructions using Verilog which will give us an insight of working of Reduced instruction set computer five (RISC-V).  
- The five execution stages of RISC-V are: Fetch, Decode, Execute, Memory, Write back.

<img height="350" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/task5_intro.png"> 

- Based on value of Program counter (PC) the CPU will fetch the instruction from instruction memory.

 Decoder, decodes instructions and interprets the tasks to be performed. ALU performs the tasks.

 Fetch- fetches instructions, Decodes- interprets instructions, Execute- does the operation and produces value, and sometimes value is written back.

**Step 1:** Make sure you have verilog and gtkwave isntalled, if not run the following code in your terminal

    sudo apt get update
    sudo apt get install iverilog gtkwave

**Step 2:** To clone the repository and download the netlist for simulation

    git clone https://github.com/vinayrayapati/iiitb_rv32i
    cd iiitb_rv32i

**Step 3:** To simulate and run verilog code

This code compiles the verilog code

    iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
    ./iiitb_rv32i
    
 This code simulates the output in gtkwave

    gtkwave iiitb_rv32i.vcd


<img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/task5_opening%20gtkwave.png">

<img width="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/task5_instertttt.png">

**Step 4:** Insert the instructions of and observe the waveforms

<img widht="450" src="https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/images/task5_rv32.png" >

<span style="font-size:larger;"> **OUTPUTS** </span>
