
## Statement
- A sentence that can be assigned a truth value of either `true` or `false`.
- Not all sentences are statements 
	- However all statements by definition must be sentences
- It is also called "Proposition"
>[!example] Example of Statement
>- 6 < 4
>	- This would be `false`. 6 is not less than 4
>- There exists some integer x such that x > 2
>	- This would be `true`. There does exist some integer (labeled x) that is greater than 2
>> A statement can also involve future tense word so if the statement is: 
>> - Tommy will get an A in his next exam. 
>> 	- This is an statement we just don't know if it's `true` or `false` yet. 

>[!note]
>If the sentence contains any "ambiguous" words such as "she, he, they or them", they are not statement. The words must be specific. 
>>[!example]
>> - She lives at 1234 Main Street 
>> > This is not a statement. The word "she" is effectively treated like a free variable or unbound variable ***X***. This means that "she" is too vague and can be applied to any female. You would need to specify who "she" is for it to be considered a statement.
>
> Also Note: 
>- Opinions are not statements
>> Chocolate ice cream is the best flavored ice cream
>> >This is objectively false by the way. Still an opinion.
>- Questions are not statements
>>What is the weather today? 
>>>Try assigning a `true` or  `false` value to this one. You'll find its not possible.
>- Commands are not statements
>> Hey go close that door now!
>> >Once again, Try assigning a `true` or `false` value to this one. 


## Logical Connectivity 
- They are used to connect statements together to form, according to my professor, more complex statements.

| Connectivity    | Meaning           |
| --------------- | ----------------- |
| $$\wedge$$      | and (conjunction) |
| $$\vee$$        | or (disjunction)  |
| $$\sim (\neg)$$ | not (negation)    |
- ### Some Simple Usage of Connectivity
	- Suppose $$p$$= `Jason has an A in CMSC250` and $$q$$= `Jason is in denial`
		- A simple form of connectivity can be $$p \wedge q$$
			- This would mean `Jason has an A in CMSC250 and is in denial`

>[!info]- Order of Precedence 
> - $$\sim (\neg)$$ takes precedence over $$\wedge$$ and $$\vee$$
> - $$\wedge$$ and $$\vee$$ have the same precedence.
>>[!important] Important
>>- When dealing with $$\wedge$$ and $$\vee$$ parenthesis are needed to specify what comes first or else it is not considered a statement, unless it contains all the same connectivity
>>>[!example] Example
>>>- Suppose we used the same example ***p*** and ***q*** above and introduce a new variable ***r***, suppose ***r*** = `I am angry.` 
>>>		- $$p \wedge q \vee r$$, is not a valid statement (Parenthesis is needed!!!). 
>>>		- $$(p \wedge q) \vee r$$, is a valid statement. 
>>>		- $$p \wedge q \wedge r$$, is also a valid statement since all the connectivity are the same.
## Translating English into Logic 
When we are given an English statement we break the statement into parts and assign an variable to each parts then connect the parts together with a logic connectivity.
- Given these statements, we will translate them into logics: 
	- "Tommy likes oranges and apples"
		- Let p = `Tommy likes oranges` and q = `Tommy likes apples`
			- $$p \wedge q$$
	- "Fruits are healthy but snacks are not"
		- Let p = `fruits are health`y and q = `snacks are healthy` 
			- $$p \wedge \sim q$$
	- Either Jim is sleepy or Jim is tired
		- Let p = `Jim is sleepy` and q = `Jim is tired`
			- $$p \vee q$$
	- Neither Jim nor Timmy are sleeping 
		- Let p = `Jim is sleeping` and q = `Timmy is sleeping`
			- $$ \sim p \wedge \sim q$$ or
			- $$\sim (p \vee q)$$
	- Neither Jim nor Timmy are angry but Tommy is. 
		- Let p = `Jim is angry` and q = `Timmy is angry` and r = `Tommy is angry`
			- $$\sim p \wedge \sim q \wedge r$$
## Truth Table 
- Determines whether or not a statement is `true` or `false` under every possible interpretations. 
	- We would use `T` for `true` and `F` for `false`.
	- Or in binary `1` would be `true` and `0` would be `false`.
	
- ### Interpretation
	- Each row of a truth table represent an interpretation.
	- An Interpretation is basically assigning a `true` or `false` value for each variable.
		- For example, suppose we have variable ***p*** and ***q***.
			- One interpretation can be ***p*** is `true` and ***q*** is `false`.
		- Given an Interpretation we can evaluate whether or not that statement is true under that specific interpretation, this is known as **"truth valuation"**.
			- Suppose ***p*** and ***q*** is connected by `and` connectivity, so $$p \wedge q$$
			- Under the interpretation above this statement would be `false` since ***p*** is `true` and ***q*** is `false`. 
>[!tip]-
>- The only time that a statement connected by only $$\wedge$$ is true is if all the variables are true
>- The only time that a statement connected by only $$\vee$$ is false is if all the variables are false

### Truth Table Example
- I will be using `1` for `true` and `0` for `false`

| $$p$$ | $$q$$ | $$\sim p$$ | $$p \wedge q$$ | $$p \vee q$$ | $$\sim p \vee q$$ | $$\sim(p \wedge q)$$ |
| :---: | :---: | :--------: | :------------: | :----------: | :---------------: | :------------------: |
|   1   |   1   |     0      |       1        |      1       |         1         |          0           |
|   1   |   0   |     0      |       0        |      1       |         0         |          1           |
|   0   |   1   |     1      |       0        |      1       |         1         |          1           |
|   0   |   0   |     1      |       0        |      0       |         1         |          1           |

## Logical Equivalence
Two statements are considered logically equivalent if they have the same truth value under every possible interpretation. 
- $$q \equiv \sim \sim q$$
>[!info]
>The symbol $$ \equiv $$ means "equivalent" or "congruent" even though there is another symbol for congruent which is this one $$ \cong $$ but for sake of this course the symbol $$ \equiv $$ means both. Also note, that symbol does NOT mean "equal to". "Equivalent" and "congruent" is the NOT same as "equal to". 

To check whether or not two statements are equivalent you can always write out a truth table. 
- But as you progress in this course you will starts to notice that it is very tedious to write out a truth table every time. 
	- If you are given that the two statements are not logically equivalent and you are required to show that they are not equivalent then you just have to find one interpretation where they don't match.
### Tautology
A statement is called a tautology if they are `true` under every possible interpretation. 
- Example
	- $$ q $$ $$\vee$$ $$\sim q$$

### Contradiction 
A statement is called a contradiction if they are `false` under every possible interpretation.
- Example
	- $$q$$ $$\wedge$$ $$\sim q$$


## Laws of Equivalence
We can use the laws of equivalence to simplify statement 
![[Law of Equivalance.png]]
> [!example]-
> Given the statement: $$\sim (\sim p \wedge q) \wedge (p \vee \sim q)$$
> - Simplification Steps: 
> 	- Apply DeMorgan Law 
> 		- $$(\sim \sim p \vee \sim q) \wedge (p \vee \sim q)$$
> 	- Apply Double Negative Law
> 		- $$(p \vee \sim q) \wedge (p \vee \sim q)$$ 
> 	- Apply Idempotent Law 
> 		- $$ (p \vee \sim q)$$ 

We can also used Laws of Equivalence to show if two statement are equivalent to each other

>[!example]-
>Given the statement: $$\sim(p \vee \sim q) \vee (\sim q \wedge \sim p)$$ show that is it equivalent to $$\sim p$$
>- Steps(I will be combining some steps together because it is tedious to type everything out): 
>	- Apply DeMorgan Law
>		- $$(\sim p \wedge \sim \sim q) \vee (\sim q \wedge \sim p)$$
>	- Apply Commutative Law and Double Negative Law
>		- $$(\sim p \wedge q) \vee (\sim p \wedge \sim q)$$ 
>	- Apply Distributive Law
>		- $$\sim p \wedge (q \vee \sim q)$$
>	- Apply Negation Law
>		- $$\sim p \wedge Tautology$$
>	- Apply Identity Law 
>		- $$\sim p$$



## Implications (Conditional Statement)
Implication is defined with an arrow $$\implies$$.
 In English translation that means "implies" or an "if then" statement in programming. 
 - So if we have the statement $$ p \implies q$$
	 - In the English that means "p implies q" or "if p then q" 
	 - Using the definition of arrow$$(\implies)$$above in the laws of equivalence chart it is equivalent to $$ \sim p \vee q$$
> For some reason in LaTex notation the arrow looks different from the one shown in the Laws of Equivalence chart. You do not have to use the funky looking arrow you can just use the normal arrow shown in the Laws of Equivalence. 

>[!note]
>The arrow $$\implies$$ has a lower precedence than $$\vee$$ and $$\wedge$$
>> So if we have the statement $$ p \wedge q \implies r$$
>> - You would do the "and" first then the "arrow" so you can look at it as: $$ (p \wedge q) \implies r$$

When drawing truth table for implication, the only interpretation that makes the arrow `false` is if the left hand side of the arrow is `true` but the right hand side is `false`. However, if the left hand side of the arrow is `false` then we do not care if the right hand side is `true` or `false` so the statement is automatically `true` because if the left hand is `false` then it may or may not imply the right hand side. 
- If you think about it for a second it makes sense, the arrow mean implication so if "p implies q", meaning if p is `true` then it must mean that q is `true` for the statement to be `true` , however, if p is `true` and q is `false`, then that statement is `false`. Respectively, if p is `false` then we do not care if q is `true` or `false` the statement is `true` either way.
	- An example can be, using English, "If the floor is wet then the floor is slippery".
		- The only time that statement is `false` is if the floor is wet but the floor is not slippery.
		- If the floor is not wet then we do not care if it is slippery so the statement is `true` because if the floor is not wet then it may or may not imply that it is slippery. 
> When translating implication into logic is the same thing as breaking the statement apart and assign a variable to each parts. Example: "If the floor is wet then the floor is slippery"
> - Let p = `floor is wet` and q = `floor is slippery`
> 	- $$p \implies q$$

### Example of Implication using Truth Table

| $$p$$ | $$q$$ | $$\sim p$$ | $$p \implies q$$ | $$\sim p \vee q$$ |
| :---: | :---: | :--------: | :--------------: | :---------------: |
|   1   |   1   |     0      |        1         |         1         |
|   1   |   0   |     0      |        0         |         0         |
|   0   |   1   |     1      |        1         |         1         |
|   0   |   0   |     1      |        1         |         1         |
> Observe that $$p \implies q$$ and $$\sim p \vee q$$ are equivalent thus we have prove the Definition of $$\implies$$ from the Laws of Equivalence chart.

### Converse, Inverse and Contrapositive Definition for Implication
Suppose we have p and q where p = `floor is wet` and q = `floor is slippery` and $$p \implies q$$ so "if the floor is wet then the floor is slippery"
- The converse will be: $$q \implies p$$
	- This means "if the floor is slippery then the floor is wet"
- The inverse will be: $$\sim p \implies \sim q$$
	- This means "if the floor is not wet then the floor is not slippery"
- The contrapositive will be: $$\sim q \implies \sim p$$
	- This means "if the floor is not slippery then the floor is not wet"
Converse means you flip them, inverse means you negate both, contrapositive means you negate both then flip them. Pretty self-explanatory.

>[!tip]
> - The original statement is equivalent to its contrapositive
> - The converse is equivalent to the inverse
> 
> You can draw out a truth table for each one to confirm it yourself but I am too lazy to do one.

