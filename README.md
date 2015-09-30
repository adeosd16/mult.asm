# mult.asm
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/04/Mult.asm

// Multiplies R0 and R1 and stores the result in R2.
// (R0, R1, R2 refer to RAM[0], RAM[1], and RAM[2], respectively.)
// 9/25/2015 by Dayo Adeosun
// Put your code here.

// add R0 to itself as many times as R1 and show result in R2
// place bigger number in R0 to make faster

 	@i	// i refers to some memory location
	M=1	// i=1

	@R2	//allocated somewhere
	M=0	// R2=0

	(LOOP)
	@i	//store value back in i 
	D=M
	@R1
	D=D-M	// before end after R1 is finished 
	@END
	D;JGT // greater than 0 then jump 

	@R0	// get value of R0
	D=M
	@R2	// R2 equal to R0
	M=D+M 	// add to itself

	@i	
	M=M+1	//store in RAM[15]
	

	@LOOP
	0;JMP //repeat of cycle for mult

	(END)
	@END
	0;JMP // infinite loop to end
