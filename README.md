# PDP11-Microprocessor
* A synthesizable simplified PDP11 microprocessor that can execute the program loaded in its ram.
* It is implemented in VHDL and simulated using Modelsim.

### The PDP11 has the following characteristics:
* Word length 16 bits.
* Memory size of 2K words.
* Single bus architecture.
* 4 general purpose registers (R0, R1, R2, R3), (use R3 as PC, R2 as SP).
* 20 functions ALSU.
* Special purpose registers (IR, MAR, MDR, TMP, SRC, DST,FLAG_REGISTER).
* Support for the following 8 addressing modes:
  1. Register mode.
  2. Auto increment
  3. Auto decrement
  4. Indexed
  5. Register mode indirect
  6. Auto increment indirect
  7. Auto decrement indirect
  8. Indexed indirect.
  
### The CPU support the following instruction set:
![2-operand](https://github.com/abdallahmagdy1993/PDP11-Microprocessor/blob/master/Images/1%202-operand.PNG)
![1-operand](https://github.com/abdallahmagdy1993/PDP11-Microprocessor/blob/master/Images/2%201-operand.PNG)
![branch](https://github.com/abdallahmagdy1993/PDP11-Microprocessor/blob/master/Images/3%20branch.PNG)
![jump](https://github.com/abdallahmagdy1993/PDP11-Microprocessor/blob/master/Images/4%20jump.PNG)
![no-operand](https://github.com/abdallahmagdy1993/PDP11-Microprocessor/blob/master/Images/5%20no-operand.PNG)

### The design includes the following components:
#### 1. REGISTER ARRAY: 
Contains the registers R0, R1, R2, R3 connected to the bi-directional bus.
#### 2. SPECIAL REGISTERS ARRAY:
Contains the PC, SP, TMP, SRC, DST registers connected to the bi-directional bus
#### 3. ALSU: 
Contains the ALSU with the Y and Z registers, beside the OVERFLOW, CARRY,ZERO, NEGATIVE flags.
#### 4. DECODER SET: 
Combinational circuit consists of 7 or more decoders used to divide the control word (31 bits) into 11 functions f0 to f11.
#### 5. WIDE BRANCH: 
Combinational circuit to generate the address that would be ORED with the next address field from the ROM.
This component is mainly responsible for generating the address of the wide branch after fetching the instruction from the memory to the IR, its inputs are IR &ROM[31..0]
#### 6. RAM: 
Contains the MAR, MDR and the RAM. 
#### 7. CPU: 
Contains the UAR, IR, ROM, and all the above modules.

### The repository contains:
* VHDL folder that contains the VHDL code for the system modules.
* ROM folder that contains:
  - ROM.txt file that contains the micro instructions that will be static in the ROM and their addresses.
  - C++ code that converts the micro instructions into binary representation to be saved in actual rom.
* Design.pdf that contains the design for all system modules.
* sample.txt file that contains a sample instructions used for testing the project.
* sim.do that used in the simulation for the project on Modelsim.
