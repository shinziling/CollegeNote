
## Statement
- A sentence that can be assigned a truth value to it either `true` or `false`
- Not all sentences are statements
- It is also called "Proposition"
>[!example] Example of Statement
>- 6 < 4
>- There exist some integer x such that x > 2

>[!note]
>If the sentence contains any "ambiguous" words such as "she, he, they or them", they are not statement. The words must be specific.
>>[!example]
>> - She lives at 1234 Main Street 
>> > That is not a statement the word "she" is basically treated like a free variable or unbound variable ***X*** you would need to specify who "she" is for it to be considered a statement.
>
> Also Note: 
>- Opinion are not statement
>> Chocolate ice cream are the best flavored ice cream
>- Question are not statement
>>What is the weather today? 
>- Command are not statement
>> Hey go close that door now!

## Logical Connectivity 
- They are used to connect statements together to form, according to my professor, more complex statements.

| Connectivity    | Meaning |
| --------------- | ------- |
| $$\wedge$$      | and     |
| $$\vee$$        | or      |
| $$\sim (\neg)$$ | not     |
- ### Some Simple Usage of Connectivity
	- Suppose $$p$$
= `"I am getting an A"` and $$q$$
= `"I am in denial"`
		- A simple form of connectivity can be $$p \wedge q$$
			- This would mean `I am getting an A and I am in denial`

>[!info]- Order of Precedence 
> - $$\sim (\neg)$$ takes precedence over $$\wedge$$ and $$\vee$$
> - $$\wedge$$ and $$\vee$$ have the same precedence.
>>[!important] Important
>>- When dealing with $$\wedge$$ and $$\vee$$ parenthesis is needed to specify what comes first or else it is not considered a statement unless it contains all the same connectivity
>>>[!example] Example
>>>- Suppose we used the same example ***p*** and ***q*** above and introduce a new variable ***r***, suppose ***r*** = `I am angry.` 
>>>		- $$p \wedge q \vee r$$, is not a valid statement (Parenthesis is needed!!!). 
>>>		- $$(p \wedge q) \vee r$$, is a valid statement. 
>>>		- $$p \wedge q \wedge r$$, is also a valid statement since all the connectivity are the same.

## Truth Table 
- Determine whether or not the statement is `true` or `false` under every possible interpretation. 
	- We would use `T` for `true` and `F` for `false`
	- Or in binary `1` would be `true` and `0` would be `false`
	
- ### Interpretation
	- Each row of a truth table represent an interpretation
	- An Interpretation is basically assigning a `true` or `false` value for each variable
		- For example, suppose we have variable ***p*** and ***q***
			- One interpretation can be ***p*** is `true` and ***q*** is `false`
		- Given an Interpretation we can evaluate whether or not that statement is true, this is known as **"truth valuation"**
			- Suppose ***p*** and ***q*** is connected by `and` connectivity, so $$p \wedge q$$
			- Under the interpretation above this statement would be `false` since ***p*** is `true` and ***q*** is `false`. 
>[!tip]-
>- The only time that a statement connect by only $$\wedge$$ is true is if all the variables are true
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
- Two statements are consider equivalent if they are true under every possible interpretation
	- 

