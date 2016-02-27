# Design Documentation 

The interface is the same as Part 1 except for some small changes. 

First, we added a row of fields for the condition codes. 

Second, we also added a command prompt at the bottom for users to type in the instruction and run a program. 

We added four buttons:

1. ON/OFF: Turn the program off and set all the registers equal to 0. 
2. S.I.T: Single Instruction Test. It will set PC to 1 and store the instruction into mem[1].
3. Run: Run the whole program you load in. 
4. Load: It will load the instructions into memory and set PC to the position of the first instruction. 

We have two new classes:

## Translate.java

This class serves as the assembler. It translates the instruction to machine code and convert it to a short type. 

It takes the instruction from the interface (Controller) and turns it into a short value for the CPU to process. 

## cache.java

Implemented following the specifications:

1. Fully associative
2. Uniform
3. 16 lines
4. block size: 4 words

The API consists of a getter and setter:

1. cache.write: Takes an address and a value to write to. 
2. cache.read: Takes an address to read form. 


Other changes:

Since the cache now sits between the CPU and interface, both the CPU and the interface will only interact with cache. Memory is initialized in cache and handled by cache. 

All of the instructions for part II were added to CPU, including 
JZ, JNE, JCC, JMA, JSR, RFS, SOB, JGE, MLT, DVD, TRR, AND, ORR, NOT, 
SRC, RRC, IN, OUT. 








