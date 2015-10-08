# Mult.asm
// Mike Fu
// Mult.asm program
// works with 0’s
// multiplies negative numbers
// If first num is neg, the code works properly  
// If the second number is neg, I need to reverse the sign of both first and second num
// @1 first number
// @2 second number
// @17 iteration
// @18 sum
	
  @18	//line 12, 0 of the actual code
  M=0	//clears sum
  @1	//start of preserving the numbers
  D=M
  @16
  M=D	//sets @16 to @2
  @2
  D=M	
  @17	
  M=D  	//end of preserving the numbers,sets @16 to @2
  @16	
  D=M	//checks if mums are 0
@END
  D;JEQ	//checks if second num=0
  @17	
  D=M	
@END
  D;JEQ	//check if first num=0 
  @17	
  D=M	//checks if second numb>0
@LOOP
  D;JGT	//if yes, no switch signs
  @16
  D=M
  @0
  D=A-D	//switches signs of @16
  @16
  M=D
  @17
  D=M
  @0
  D=A-D	//switches signs of @17
  @17
  M=D
(LOOP)
  @16
  D=M	//put value in R16 into D
  @18
  M=D+M	//make sum equal to original+R16
  @17	//serves as the iteration
  M=M-1	//i=i-1
  @17
  D=M	//checks if 0
@LOOP
  D;JGT	//if D>0, jumps back to loop 
@END
  D;JEQ	//if D=0, ends loop
(END)
@END	//if D=0 jump to end, creating an infinite loop
  0;JMP	//infinite loop	   
	
