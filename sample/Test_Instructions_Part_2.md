# Test Instructions - Part 2

## LDR

Instruction: LDR 1,0,2[,0]

Load register 1 with the contents of memory location 1. 

Steps:

1. Put the instruction in the console. Hit Enter. 
2. Set mem[2] = 10.
3. Push SSS.
4. R[1] = 10. 

## STR

Instruction: STR 2,1,21[,0]

Store the contents of register 2 into memory location 21.

Steps: 

1. Put the instruction in the console. Hit Enter.  
2. Set R[2] = 7.
3. Set I1 = 1. 
4. Click SSS. Look at memory location 21. It should be 7. 

## LDA

Instruction: LDA 0,1,27[,1]

Load register 0 with address 27. 

Steps:

1. Put the instruction in the console. Hit enter. 
2. Set mem[27] = 15.
3. Set I[1] = 7.
4. Click SSS. Look at the contents of register 0. It should be 15.

## LDX

Instruction LDX 0,1,0[,1]

Load index register from memory location 0.

1. Put the instruction in the console. Hit Enter.
2. Set mem[0] = 31, set PC = 1.  
3. Click SSS. Look at the contents of I1. It should be 31. 

## STX

Instruction: STX 0,2,0[,0]

Store index register 0 to memory location 0

1. Put the instruction in the console. Hit Enter.
2. Set I2[2] = 31.
3. Click SSS. Look at the contents of mem[0]. It should be 31. 

## AMR

Instruction: AMR 3,0,0[,0]

Add the contents of address 0 with the contents of register 3

1. Put the instruction in the console. Hit Enter. 
2. Set mem[0] = 7. 
3. Set R[3] = 3.
4. Click SSS. Look at the contents of R[3]. It should be 10. 

## SMR

Instruction: SMR 3,0,0[,0]

Subtract the contents of memory location 0 from the contents of register 3. 

1. Put the instruction in the console. Hit Enter. 
2. Set mem[0] = 5. 
3. Set R[3] = 3, set PC = 1.
4. Click SSS. Look at the contents R[3]. It should be -2. 

## AIR

Instruction: AIR 3,2

Add the contents of address 0 to the contents of register 3. 

1. Put the instruction in the console. Hit Enter.  
2. Set R[3] = 7. 
3. Click SSS. Look at the contents R[3]. It should be 9. 

## SIR

Instruction: SIR 3,31

Subtract the contents of intermediate from the register.

1. Put the instruction in the console. Hit Enter.  
2. Set R[3] = 47.
3. Click SSS. Look at the contents R[3]. It should be (47 - 31 = 16)

## JZ

Instruction: JZ 1,0,6,[,0]

Jump to an address if the contents of Register 1 is equal to 0. 

1. Put the instruction in the console. Hit Enter. 
2. Set R[1] = 0.
3. Look at PC. It should be 0.

## JNE

Instruction: JNE 2,0,6[,0]
  
Jump to an address if the contents of Register 2 is not equal to 0.

1. Put the instruction in the console. Hit Enter. 
2. Set R[2] = 0.
3. Look at PC. It should be 2. 

## JCC

Instruction: JCC 1,0,31[,0]

Jump to an address if the condition code is set. 

1. Put the instruction in the console. Hit Enter. 
2. Set CC[1] = true
3. Look at PC. It should be 31. 


## JMA

Instruction: JMA 0,16[,1]

Jump to an address. 

1. Put the instruction in the console. Hit Enter. 
2. Set the contents of address 16 to 37.  
3. Look at PC. It should be 37 + 1 = 38. 

## JSR

Instruction: JSR 0,0,16,[,0]

Jump and save address at GPR[3].

1. Put the instruction in the console. Hit Enter.
2. Set the contents of address 16 to 49. 
3. Look at PC. It should be 1 + 16 = 17.  
4. Look at R[3]. It should be 2. 

## RFS 

Instruction: RFS 0,24

Return from subroutine with R[0] being the intermedate and PC being the contents of R[3].

1. Put the instruction in the console. Hit Enter.
2. Set GPR[3] = 1.
4. Look at GPR[0]. It should be 24. 
5. Look at PC. It should be 1.

## SOB

Instruction: SOB 1,0,28[,0]

Subtract 1 from register 1 and branch if the value is greater than 0. 

1. Put the instruction in the console. Hit Enter.
2. Set GPR[1] = 13. 
3. Look at PC. It should be 28. 
4. Look at GPR[1]. It should be 12. 

## JGE

Instruction: 010001 00 00 0 00011 (17411)

Jump on greater than or equal to 0. 

JGE 0,0,3[,0]

1. Put the instruction in the console. Hit Enter. 
3. Set GPR[0] = 11. 
4. Look at PC. It should be 3. 

## MLT 

Instruction: 010100 00 10 0 00000 (20608)

MLT 0,2

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 12. Set GPR[2] = 3. 
3. GPR[0], GPR[1] should be 36 and 36 respectively. 

## DVD 

Instruction: 010101 00 10 0 00000 (21632)

DVD 0,2

1. Put the instruction in the console. Hit Enter.
3. Set GPR[0] = 12. Set GPR[2] = 3. 
4. GPR[0], GPR[1] should be 4 and 0.

## TRR

Instruction: 010110 00 10 0 00000 (22656)

TRR 0,2

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 12. Set GPR[2] = 12. 
4. Check CC[3]. It should be true.

## AND

Instruction: 010111 00 10 0 00000 (23680)

AND 0,2

1. Put the instruction in the console. Hit Enter. 
2. Set GPR[0] = 3. Set GPR[2] = 3. 
3. Check GPR[0]. It should be 3. 

## OR

Instruction: 11000 00 10 0 00000 (24704)

OR 0,2

1. Put the instruction in the console. Hit Enter.
2. Set GPR[0] = 3. Set GPR[2] = 5. 
3. Check GPR[0]. It should be 7. 

## NOT

Instruction: 11001 00 10 0 00000 (25728)

NOT 0

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

// interface needs to have a console keyboard
1. Prompt for short. User types it in and it is stored. 
2. Check R[0]. It should be equal to the short. 

# OUT

Instruction: 111110 00 00 0 00000 (63488)

OUT 0,1

Outputs the character from R[0] to the console printer. 

1. This should print out what is stored in R[0]. 
