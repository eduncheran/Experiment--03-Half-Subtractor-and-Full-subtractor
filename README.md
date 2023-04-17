# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1. Use module projname(input,output) to start the Verilog programmming.
2. Assign inputs and outputs using the word input and output respectively.
3. Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4. Use each output to represnt onre for differnce and the other for borrow.
5. End the verilog program using keyword endmodule. 


## Program:
```
HALF SUBTRACTOR

module halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```
```
FULL SUBTRACTOR

module fullsub(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```

```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: R.Neduncheran
RegisterNumber:  212222050040
```

## Output:
## HALF SUBTRACTOR


### Truthtable

![tt hs](https://user-images.githubusercontent.com/115524975/231995081-9565114a-6e8e-4386-91d0-07317ff01b24.png)

###  RTL realization

![rtl hs](https://user-images.githubusercontent.com/115524975/232001410-95100ac0-496b-4b64-bc66-1a33d138a069.png)

### Timing diagram

![td hs](https://user-images.githubusercontent.com/115524975/231995665-1505773b-6cf8-4105-ac5f-3edf1b9d3ae6.png)

## FULL SUBTRACTOR


### Truthtable

![tt fs](https://user-images.githubusercontent.com/115524975/231995184-38ce3b74-a537-4a3f-933d-dc78673176a4.png)


###  RTL realization

![rtl fs](https://user-images.githubusercontent.com/115524975/232002027-55014d9d-8a4f-4e9b-9e3c-d0a1cc7ce098.png)

### Timing diagram

![td fs](https://user-images.githubusercontent.com/115524975/231995781-dda93ae2-5223-4810-8a5c-5d6fe643696f.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
