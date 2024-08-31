# 16-Bit-MIPS-CPU

The aim of this project is to consolidate knowledge of computer architecture and gain an affinity for singlecycle processors.

* All instructions are 16 bit wide.
* 8x16 bit general purpose registers
* 64 Kb RAM
* 64 Kb Instruction Memory
* 3 type of jump instruction

I used the ISA from https://www.fpga4student.com/ site.

Here are the compleate ISA : 

![image](https://github.com/user-attachments/assets/f55e311d-c2f0-4ada-9888-56c985f8a76b)

![image](https://github.com/user-attachments/assets/616a2fb9-6393-48e3-b04d-46da0f888170)

Here are the description for instructions :

Add : R[rd] = R[rs] + R[rt]

Subtract : R[rd] = R[rs] - R[rt]

And: R[rd] = R[rs] & R[rt]

Or : R[rd] = R[rs] | R[rt]

SLT: R[rd] = 1 if R[rs] <  R[rt] else 0

Jr: PC=R[rs]

Lw: R[rt] = M[R[rs]+SignExtImm]

Sw : M[R[rs]+SignExtImm] = R[rt]

Beq : if(R[rs]==R[rt]) PC=PC+1+BranchAddr

Addi: R[rt] = R[rs] + SignExtImm

J :  PC=JumpAddr

Jal : R[7]=PC+2;PC=JumpAddr

SLTI: R[rt] = 1 if R[rs] < imm else 0

# Test Codes

R type Instructions Test Code

lw $0 0 ($0)
lw $1 1 ($1)
add $2 $1 $0
sub $3 $1 $0
and $4 $1 $0
or $5 $1 $0
slt $6 $1 $0
addi $7 $0 20
slti $7 $1 40

Hexadecimal Code

8000
8481
0420
0431
0442
0453
0464
E394
27A8

J and I type Instructions Test Code

lw $0 0 ($0)
lw $1 1 ($1)
jr  $0
j   (7)
jal (15)
beq $0 $1 20
sw $6 5 $0

Hexadecimal Code

8000
8481
8
4007
610C
C094
B805


