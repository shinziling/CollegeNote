Not a super important unit for discrete structure since this kind of stuff deals with hardware. But good to know. <br>
## Basic Logic Gates
The three most basic logic gates are: 
- the **or** gate
- the **and** gate
- the **not** gate
![[Gates.jpg]]
> Combining a couples of these together with some inputs and outputs we get a circuit board. 

Consider this simple circuit (Took this from my professor slide)
- It has three input bits and two output bits
![[Simple Circuit.png]]

What is the output given the input 011(Top to bottom)? 
>[!success]- Solution
>-  Output: 11


## Propositional Logic into Circuit
- You can turn a propositional logic statement into a circuit.
	- Where each variable represent one input bit and there is one output bit for the entire statement.
Consider the statement $p \wedge \neg (q \vee r) \equiv p \wedge (\neg q \wedge \neg r)$

It will look something like this

![[Example_1.png]]

>Alternatively, you can combine the $q$ and the $r$ to an "or" gate then negate the output of the "or" gate with a "not" gate. FYI I drew the picture above. 

## Truth table into Circuit 
- You can also turn any truth table into circuit

Consider the truth table below with some random outputs I have chosen: 

| row # | $p$ | $q$ | $r$ | $output$ |
| :---: | :-: | :-: | :-: | :------: |
|   1   |  1  |  1  |  1  |    0     |
|   2   |  1  |  1  |  0  |    0     |
|   3   |  1  |  0  |  1  |    0     |
|   4   |  1  |  0  |  0  |    1     |
|   5   |  0  |  1  |  1  |    0     |
|   6   |  0  |  1  |  0  |    1     |
|   7   |  0  |  0  |  1  |    1     |
|   8   |  0  |  0  |  0  |    0     |
> What propositional statement corresponds to the output column?

>[!success]- Solution
>$(p \wedge \neg q \wedge \neg r) \vee (\neg p \wedge q \wedge \neg r) \vee (\neg p \wedge \neg q \wedge r)$
>- The only rows you have to consider are the ones with 1 on the output column, so there is three rows on the output column with 1: row 4, 6 and 7. Then take all the variables with their corresponding truth value in that row and combine them with "and" connectivity and separate each row with "or" connectivity.
>
>>You can probably simplify the above statement with some logic rules but my lazy ass is not doing that. 


## Math with Circuit 
You can build a circuit that does math

### Brute Force: Addition
If we are adding two 2-bit numbers together we can use a truth table to show the output
- It is just adding binary number
	- There would be 4 input bits since there are two 2-bit numbers
	- When adding two 2-bit data you would have 3 output bits
- If it was two 32-bit numbers there would be 64 input bits
	- Which get really annoying with a truth table since there will be 64 input bit columns plus another 33 output bit columns

## A Better Way to Add Binary
So, instead of using a truth table we do the normal way of adding vertical. It is the same idea with base 10 number but instead we have base 2:
- In base 10 : $9 + 1 = 10$, where you would carry the one over
	- But in base 2 or binary we carry the one over when the sum is 2. So $1 + 1 = 10$ in base 2 since 2 is 10 in binary.
	- So, what if we add three 1's together in binary? 
		- $1+1+1 = 11$, 3 is 11 in binary
			- Breakdown: 
				- $1+1=10$, carry the one over
				- $10 + 1 = 11$, add straight down
### Example using a table

| Carry |  1  |     |     |     |     |
| :---: | :-: | :-: | :-: | :-: | :-: |
|       |     |  1  |  0  |  0  |  0  |
|  $+$  |     |  1  |  0  |  1  |  1  |

| ***Output*** |  1  |  0  |  0  |  1  |  1  |
| :----------: | :-: | :-: | :-: | :-: | :-: |
>Answer : 10011

| Carry |  1  |  1  |     |     |     |
| :---: | :-: | :-: | :-: | :-: | :-: |
|       |     |  1  |  1  |  0  |  0  |
|  $+$  |     |  1  |  1  |  1  |  1  |

| ***Output*** |  1  |  1  |  0  |  1  |  1  |
| :----------: | :-: | :-: | :-: | :-: | :-: |
>Answer : 11011


## Converting Binary to Base 10 and Vice Versa
Okay, you should know how to do this but I will briefly go over it. You also don't need to know any other base other than 2 or 10. 

- Binary to Base 10 is simple:
	- Take a binary number multiply each bit with it corresponding place value which is $2^{n}$, where $n$ is the place value. Then add them up. Note: the first place value is 0. 
		- For other base you do the same thing but instead of a 2 it would be whatever base you are using. 

Example with table

| Convert the following to base 10 |     1      |     1     |     0     |     1     |     1     |
| :------------------------------: | :--------: | :-------: | :-------: | :-------: | :-------: |
|           Place Value            |   $2^4$    |   $2^3$   |   $2^2$   |   $2^1$   |   $2^0$   |
|             Multiply             | $1*2^4=16$ | $1*2^3=8$ | $0*2^2=0$ | $1*2^1=2$ | $1*2^0=1$ |
> Then add the result up: $16+8+2+1 =27$

> [!tip]
> You can safely ignore all the ones with 0 since 0 times anything equal to 0 anyways and you would just need to worry about the ones with 1 in them. As a matter of fact you don't need to do any multiplication with 1 since 1 times any number $n$ is $n$ itself. 
> - So using the above example, ignoring all the 0 and just looking at the place value with 1 in them. I can just write $11011_2 = 2_{10}^4 + 2_{10}^3 + 2_{10}^1 + 2_{10}^0 = 27_{10}$
>
>> The little 2 notation just means that number is in base 2 and same thing for the little 10.

- Base 10 to Binary, there is two ways to do this: Division and Subtraction
	- The Division way: When doing this way you are writing the 0 and 1 in reverse order (You will know what I mean when I do the example)
		- Steps:
			1. Looks at the original number (base 10) is it even or odd? If odd put a 1, if even put a 0.
			2. Divide by 2 and throw the remainder out (integer division), look at the result is it even or odd? If odd put a 1 BEFORE the previous number, if even put a 0 BEFORE the previous number.
			3. Repeat step 2 until you reach 0 or 1.
		- Example: Consider the base 10 number 106
			- 106 is even so we put 0: 0
			- $106/2 = 53$. 53 is odd put a 1 BEFORE 0 so: 10
			- $53/2= 26$, We throw out the remainder 26 is even put a 0 BEFORE 10 so: 010
			- $26/2=13$ 13 is odd put a 1 so: 1010
			- $13/2 = 6$, 6 is even put a 0 so: 01010
			- $6/2=3$ 3 is odd put a 1 so: 101010
			- $3/2 = 1$1 is odd put a 1 so: 1101010
			- **STOP We reach 1**, so the Answer is 1101010
	- The Subtraction way: In division we put the 1 and 0 in reverse order. In subtraction we put the 1 and 0 in order.
		- Steps: 
			1. Look at the original number (base 10), what is the highest power (exponent) of base 2, $2^n$ where $n$ is the highest power, without being greater than the original number (base 10)?
			2. Put a 1 then subtract the highest power of base 2 from the original number. After which subtract 1 from the exponent so $2^{n-1}$ now look at $2^{n-1}$ , is that greater than the resulting difference? If so, put a 0 and subtract 1 from the exponent, if not, put a 1 and subtract $2^{n-1}$ from the resulting difference.
			3. Repeat step 2 until you reach 0, if the exponent $n$ has not reach 0 then everything after where you stop are all 0. 
		- Example: Consider the base 10 number 106 again
			- The highest power $n$ of base 2 without being greater than 106 is 6 since $2^7= 128$ which is greater than 106 and $2^6=64$. Let use a table for this: 

| Base 2 powers |       $2^6 = 64$        |       $2^5 = 32$       |            $2^4 = 16$            |       $2^3 = 8$       |     $2^2 = 4$     |                     $2^1 = 2$                     |       $2^0 = 1$        |
| :-----------: | :---------------------: | :--------------------: | :------------------------------: | :-------------------: | :---------------: | :-----------------------------------------------: | :--------------------: |
|   Subtract?   | Yes, since $64 \le 106$ | Yes, since $32 \le 42$ |       No, since $16 > 10$        | Yes, since $8 \le 10$ | No, since $4 > 2$ |               Yes, since $2 \le 2$                | No, since we reached 0 |
|  Subtraction  |     $106 - 64 = 42$     |      $42-32 = 10$      | Ignore the subtraction, still 10 |      $10 - 8 =2$      |  Ignore, still 2  | $2-2=0$<br>STOP, any remaining exponents put a 0. |                        |
| Binary Answer |            1            |           1            |                0                 |           1           |         0         |                         1                         |           0            |

> Observe that we still got the same answer 1101010 as in the division example for 106. Personally, I prefer the subtraction since I think it is faster and I don't have to write it in reverse order. 


>[!tip]
>
>If a base 10 number is exactly 2 to the $n$ power then the binary form is 1 plus $n$ amount of 0(s). 
>- So if the base 10 number is 64. 64 is exactly $2^6$ $\therefore$ the binary form is 1 with six 0s after so 1000000. 
>
>If a base 10 number is +1 away from 2 to the $n+1$ power, in other word if $2^{n+1}$ is greater than the base 10 number by exactly 1, then the binary form is $n$ amount of 1(s).
>- So if the base 10 number is 255. The highest $n$ power of base 2 without being greater than 255 is 7, however, 255 is exactly +1 away from $2^{7+1} = 2^8 = 256$, $\therefore$ the binary form of 255 is exactly seven 1s so 1111111. 

