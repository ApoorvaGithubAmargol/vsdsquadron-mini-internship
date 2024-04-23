# vsdsquadron-mini-internship
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


![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave1.png)

- verification of gtwave

![](https://github.com/ApoorvaGithubAmargol/vsdsquadron-mini-internship/blob/main/gtkwave2.png)
