# DE-WORSHOP

**AIM:**

To study and verify the ripple carry adder in Quartus II using Verilog programming.

**EQUIPTMENTS REQUIRED:**

Software – Quartus prime

**THEORY:**

Ripple Carry Adder in Verilog:

A Ripple Carry Adder (RCA) is a basic arithmetic circuit used to add two binary numbers. It consists of multiple full adders connected in a chain, where the carry output from each full adder "ripples" to the next.

Full Adder Logic:

A full adder adds three inputs: two bits A and B, and a carry-in Cin. It produces a sum S and a carry-out Cout as outputs.

**PROCEDURE:**

1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations generate the timing diagram.

**EXAMPLE:**

![image](https://github.com/user-attachments/assets/72736fcf-c368-416c-a3b5-b817af563db1)


**PROGRAM:**

Program for logic gates and verify its truth table in quartus using Verilog programming

Developed By: CHARUKESH S

Register No: 
```
module full_adder (A,B,Cin,Sum,Cout);
    input A, B, Cin;      
    output Sum, Cout;
    assign Sum = A ^ B ^ Cin;            
    assign Cout = (A & B) | (Cin & (A ^ B)); 
endmodule

// 4-bit Ripple Carry Adder Module
module RIPCAR(A,B,Cin,Sum,Cout);
     input [3:0] A, B;      
    input Cin;            
    output [3:0] Sum;     
    output Cout;      
    wire C1, C2, C3;       

    // Instantiate 4 full adders
    full_adder FA0 (A[0], B[0], Cin, Sum[0], C1);  // Least significant bit (LSB)
    full_adder FA1 (A[1], B[1], C1, Sum[1], C2);
    full_adder FA2 (A[2], B[2], C2, Sum[2], C3);
    full_adder FA3 (A[3], B[3], C3, Sum[3], Cout); // Most significant bit (MSB)
	 endmodule
```

**RTL REALIZATION:**

![image](https://github.com/user-attachments/assets/864661cf-4c94-4d96-af08-f26824d6f5d2)


**TIMING WAVEFORM:**

![image](https://github.com/user-attachments/assets/d954a356-1637-434b-9826-d586a10548a9)


**RESULT:**

the ripple carry adder is verified using Verilog programming.
