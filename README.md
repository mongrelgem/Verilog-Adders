# Verilog-Adders
Implementing Different Adder Structures in Verilog

The Aim of this project is to describe and differentiate different types of adders in verilog and distinguish them at simulation level.
All adders have been defined for **8, 16, 32 and 64 bit** addition along with test benches for each type of adder.
This project implements the following adders :

* Carry Lookahead Adder
* Carry Ripple Adder
* Carry Select Adder
* Carry Skip Adder
* Kogge Stone Adder
* Hybrid Adder

## Carry Lookaheaed Adder

![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/4-bit_carry_lookahead_adder.svg/500px-4-bit_carry_lookahead_adder.svg.png)       
4-bit Carry Lookahead Adder

A carry-look ahead adder improves speed by reducing the amount of time required to determine carry bits. It can be contrasted with the simpler, but usually slower, ripple-carry adder (RCA), for which the carry bit is calculated alongside the sum bit, and each stage must wait until the previous carry bit has been calculated to begin calculating its own sum bit and carry bit. The carry-lookahead adder calculates one or more carry bits before the sum, which reduces the wait time to calculate the result of the larger-value bits of the adder. The Kogge–Stone adder (KSA) and Brent–Kung adder (BKA) are examples of this type of adder.
Carry-lookahead depends on two things:
* Calculating for each digit position whether that position is going to propagate a carry if one comes in from the right.
* Combining these calculated values to be able to deduce quickly whether, for each group of digits, that group is going to propagate a carry that comes in from the right.

## Carry Ripple Adder

![alt text](https://www.researchgate.net/publication/283037309/figure/fig2/AS:454461651984390@1485363509931/Eight-bit-Ripple-Carry-adder.png)  
8-bit Carry Ripple Adder


It is possible to create a logical circuit using multiple full adders to add N-bit numbers. Each full adder inputs a Cin, which is the Cout of the previous adder. This kind of adder is called a ripple-carry adder (RCA), since each carry bit "ripples" to the next full adder. Note that the first (and only the first) full adder may be replaced by a half adder (under the assumption that Cin = 0).
The layout of a ripple-carry adder is simple, which allows fast design time; however, the ripple-carry adder is relatively slow, since each full adder must wait for the carry bit to be calculated from the previous full adder.


## Carry Select Adder

![alt text](https://upload.wikimedia.org/wikipedia/en/thumb/1/10/Carry-select-adder-detailed-block.png/712px-Carry-select-adder-detailed-block.png)  
4-bit Carry Select Adder


The carry-select adder generally consists of two ripple carry adders and a multiplexer. Adding two n-bit numbers with a carry-select adder is done with two adders (therefore two ripple carry adders), in order to perform the calculation twice, one time with the assumption of the carry-in being zero and the other assuming it will be one. After the two results are calculated, the correct sum, as well as the correct carry-out, is then selected with the multiplexer once the correct carry-in is known


## Carry Skip Adder

![alt text](https://www.researchgate.net/profile/Sujan_Sarkar3/publication/322057640/figure/fig3/AS:631632960700450@1527604441337/8-bit-Carry-Skip-Adder.png)  
4-bit Carry Skip Adder


The worst case for a simple one level carry-ripple-adder occurs, when the propagate-condition is true for each digit pair. Then the carry-in ripples through the n n-bit adder and appears as the carry-out after definitive delay
For each operand input bit pair  the propagate-conditions using an XOR-Gate (see ). When all propagate-conditions are true, then the carry-in bit  determines the carry-out bit. The n-bit-carry-skip adder consists of a n-bit-carry-ripple-chain, a n-input AND-gate and one multiplexer. Each propagate bit that is provided by the carry-ripple-chain is connected to the n-input AND-gate. The resulting bit is used as the select bit of a multiplexer that switches either the last carry-bit or the carry-in  to the carry-out signal.


## Kogge Stone Adder

![alt text](https://elnndccpro.files.wordpress.com/2017/01/4bit-kogge-stone-adder.jpg)  
4-bit Kogge Stone Adder


Each vertical stage produces a "propagate" and a "generate" bit, as shown. The culminating generate bits (the carries) are produced in the last stage (vertically), and these bits are XOR'd with the initial propagate after the input (the red boxes) to produce the sum bits. E.g., the first (least-significant) sum bit is calculated by XORing the propagate in the farthest-right red box (a "1") with the carry-in (a "0"), producing a "1". The second bit is calculated by XORing the propagate in second box from the right (a "0") with C0 (a "0"), producing a "0".
