# Test Instructions - Part 2

Note (For mac users): We have a ... (OFF) button. It will turn off "OUR" computer and set all registers to 0. Then you can turn it back on by clicking on it. It will go to on. 

Note (For windows users): The button will say OFF. 

Three ways to use the interface:

## One Instruction At a Time

1. Put in the instruction in the console. Click S.I.T - Single Instruction Test. This will set PC to 1 and store the instruction into mem[1].
2. It will run the instruction and does NOT increment the PC. 
3. If that is IN instruction, you need to put the number in the console and hit enter. 

## Run instructions from the File

Put the name of the file in the prompt:

The name of the file is: testing.txt

Click Load. It will load the instructions into memory and set PC to the position of the first instruction. 

Click either: 

1. Single Step Switch Button: Run one instruction at a time and increment the PC by 1. 
2. Run button: Run the whole program. 

## LDR

Instruction: 000001 01 00 0 00001 (1281)

LDR 1,0,2[,0]

Load register 1 with the contents of memory location 1. 

Steps:

1. Put the instruction in the console. Hit Enter. 
2. Set mem[2] = 10.
3. Push SSS.
4. R[1] = 10. 

## STR

Instruction: 000010 10 01 0 10100 (2644)

STR 2,1,21[,0]

Store the contents of register 2 into memory location 21.

Steps: 

1. Put the instruction in the console. Hit Enter.  
2. Set R[2] = 7.
3. Set I1 = 1. 
4. Click SSS. Look at memory location 21. It should be 7. 

## LDA

Instruction: 000011 00 01 1 10100 (3188)

LDA 0,1,27[,1]

Load register 0 with address 27. 

Steps:

1. Put the instruction in the console. Hit enter. 
2. Set mem[27] = 15.
3. Set I[1] = 7.
4. Click SSS. Look at the contents of register 0. It should be 15.

## LDX

Instruction: 101001 00 01 1 00000 (42080)

LDX 0,1,0[,1]

Load index register from memory location 0.

1. Put the instruction in the console. Hit Enter.
2. Set mem[0] = 31.  
3. Click SSS. Look at the contents of I1. It should be 31. 

## STX

Instruction: 101010 00 10 0 00000 (43136)

STX 0,2,0[,0]

Store index register 2 to memory location 0.

1. Put the instruction in the console. Hit Enter.
2. Set I2[2] = 31.
3. Click SSS. Look at the contents of mem[0]. It should be 31. 

## AMR

Instruction: 000100 11 00 0 00000 (4864)

AMR 3,0,0[,0]

Add the contents of address 0 with the contents of register 3

1. Put the instruction in the console. Hit Enter. 
2. Set mem[0] = 7. 
3. Set R[3] = 3.
4. Click SSS. Look at the contents of R[3]. It should be 10. 

## SMR

Instruction: 000101 11 00 0 00000 (5888)

SMR 3,0,0[,0]

Subtract the contents of memory location 0 from the contents of register 3. 

1. Put the instruction in the console. Hit Enter. 
2. Set mem[0] = 5. 
3. Set R[3] = 3.
4. Click SSS. Look at the contents R[3]. It should be -2. 

## AIR

Instruction: 000110 11 00 0 00010 (6914)

AIR 3,2

Add the immediate 2 to the contents of register 3. 

1. Put the instruction in the console. Hit Enter.  
2. Set R[3] = 7. 
3. Click SSS. Look at the contents R[3]. It should be 9. 

## SIR

Instruction: 000111 11 00 0 11111 (7967)

SIR 3,31

Subtract the immediate 31 from register 3.

1. Put the instruction in the console. Hit Enter.  
2. Set R[3] = 47.
3. Click SSS. Look at the contents R[3]. It should be (47 - 31 = 16)

## JZ

Instruction: 001010 01 00 1 00110 (10534)

JZ 1,0,6,[,0]

Jump to an address if the contents of Register 1 is equal to 0. 

1. Put the instruction in the console. Hit Enter. 
2. Set R[1] = 0.
3. Look at PC. It should be 0.

## JNE

Instruction: 001011 10 00 0 00110 (11782)

JNE 2,0,6[,0]
  
Jump to an address if the contents of Register 2 is not equal to 0.

1. Put the instruction in the console. Hit Enter. 
2. Set R[2] = 0.
3. Look at PC. It should be 2. 

## JCC

Instruction: 001100 01 00 0 11111 (12575)

JCC 1,0,31[,0]

Jump to an address if the condition code is set. 

1. Put the instruction in the console. Hit Enter. 
2. Set CC[1] = true
3. Look at PC. It should be 31. 


## JMA

Instruction: 001101 00 00 1 10000 (13360)

JMA 0,16[,1]

Jump to an address. 

1. Put the instruction in the console. Hit Enter. 
2. Set the contents of address 16 to 37.  
3. Look at PC. It should be 37 + 1 = 38. 

## JSR

Instruction: 001110 00 00 0 10000 (14352)

JSR 0,0,16,[,0]

Jump and save address at GPR[3].

1. Put the instruction in the console. Hit Enter.
2. Set the contents of address 16 to 49. 
3. Look at PC. It should be 1 + 16 = 17.  
4. Look at R[3]. It should be 2. 

## RFS 

Instruction: 001111 00 00 0 11000 (15384)

RFS 0,24

Return from subroutine with R[0] being the intermedate and PC being the contents of R[3].

1. Put the instruction in the console. Hit Enter.
2. Set GPR[3] = 1.
4. Look at GPR[0]. It should be 24. 
5. Look at PC. It should be 1.

## SOB

Instruction: 010000 01 00 0 11100 (16668)

SOB 1,0,28[,0]

Subtract 1 from register 1 and branch if the value is greater than 0. 
1. Put the instruction in the console. Hit Enter.
2. Set GPR[1] = 13. 
3. Look at PC. It should be 28. 
4. Look at GPR[1]. It should be 12. 

## JGE

Instruction: 010001 00 00 0 00011 (17411)

JGE 0,0,3[,0]

Jump on greater than or equal to 0. 

1. Put the instruction in the console. Hit Enter. 
3. Set GPR[0] = 11. 
4. Look at PC. It should be 3. 

## MLT 

Instruction: 010100 00 10 0 00000 (20608)

MLT 0,2

Multiply the contents of register 0 and register 2. 

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 12. Set GPR[2] = 3. 
3. GPR[1] = 36 and GPR[0] = 0. CC[0] = false.

## DVD 

Instruction: 010101 00 10 0 00000 (21632)

DVD 0,2

Divide the contents of register 0 and register 2.

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 12. Set GPR[2] = 3. 
3. GPR[0] = 4. GPR[1] = 0. CC[3] = false.

## TRR

Instruction: 010110 00 10 0 00000 (22656)

TRR 0,2

Test the equality of register 0 and register 2. 

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 12. Set GPR[2] = 12. 
4. Check CC[3]. It should be true.

## AND

Instruction: 010111 00 10 0 00000 (23680)

AND 0,2

Logical AND of register 0 to register 2. 

1. Put the instruction in the console. Hit Enter. 
2. Set GPR[0] = 3. Set GPR[2] = 3. 
3. Check GPR[0]. It should be 1. 

## OR

Instruction: 11000 00 10 0 00000 (24704)

OR 0,2

Logical OR of register 0 to register 2. 

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 3. Set GPR[2] = 5. 
3. Check GPR[0]. It should be 1. 

## NOT

Instruction: 11001 00 10 0 00000 (25728)

NOT 0

Logical NOT of register 0.

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 3. 
3. Check GPR[0]. It should be 0. 

## SRC

Instruction: 011111 11 1 1 0 00011 (32707)

SRC 3,3,1,1

Shift register by 3.

1. Put the instruction in the console. Hit Enter.
2. Set R[3] = 7.
3. Look at R[3].

## RRC

Instruction: 100000 11 1 1 0 00011 (33731)

RRC 3,3,1,1

Rotate register by 3.

1. Put the instruction in the console. Hit Enter.
2. Set R[3] = 5.
3. Look at R[3].

# IN

Instruction: 111101 00 00 0 00000 (62464)

IN 0,0

Inputs a character from console keyboard to R[0].

Interface needs to have a console keyboard.

1. Prompt for short. User types it in and it is stored. 
2. Check R[0]. It should be equal to the short. 

# OUT

Instruction: 111110 00 00 0 00000 (63488)

OUT 0,1

Outputs the character from R[0] to the console printer. 

1. This should print out what is stored in R[0]. 
