```
Name:-Janarthanan B
Reg no:-212223100014
```
# Exp-04 Implementation of Half subtractor and Full subtractor circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
   Hardware – PCs, Cyclone II , USB flasher
   Software – Quartus prime
   
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Procedure

1.  Use module projname(input,output) to start the Verilog programmming.

2.  Assign inputs and outputs using the word input and output respectively.

3.  Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.  Use each output to represnt onre for differnce and the other for borrow.

5.  End the verilog program using keyword endmodule

## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits.
It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). 
To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. 
The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. 
The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. 
The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. 
The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Program:
```
module project_4_1(a,b,borrow,diff);
input a,b;
output borrow,diff;
assign borrow=~a&b;
assign diff=a^b;
endmodule
```

## Truthtable
![image](https://github.com/jokerjana/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/147173630/1a2dade9-21d4-48d9-97d0-81983d806d28)

##  RTL realization
![image](https://github.com/Raji1009/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/89059861/a5259217-f5ae-4649-b591-a21d0618d756)

## Timing diagram 
![image](https://github.com/Raji1009/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/89059861/e2eed852-f5b0-44f9-a339-6a3f913e7085)


## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . 
It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Program:
```
module project_4_2(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule
```

## Truthtable
![image](https://github.com/Raji1009/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/89059861/3216ee64-c320-4f8b-a4ee-1f6a30ef0ac6)

##  RTL realization
![image](https://github.com/Raji1009/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/89059861/6011a067-43cd-4c50-8d83-1473444b1e84)

## Timing diagram 
![image](https://github.com/Raji1009/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/89059861/ff8c311c-e9a9-4a62-9c73-389476e10b08)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
