
## Statement
- A sentence that can be assigned a truth value to it either `true` or `false`
- Not all sentence are statement
- It is also called "Proposition"
>[!example] Example of Statement
>- 6 < 4
>- There exist some integer x such that x > 2

>[!note]
>If the sentence contains any "ambiguous" like word such as "she, he, they or them", they are not statement. 
>>[!example]
>> She lives at 1234 Main Street 
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
- They are used to connect statements together

| Connectivity    | Meaning |
| --------------- | ------- |
| $$\wedge$$      | and     |
| $$\vee$$        | or      |
| $$\sim (\neg)$$ | not     |
- ### Some Simple Usage of Connectivity
	- Suppose $$p$$
= `"I am definitely getting an A"` and $$q$$
= `"I am in denial"`
		- A simple form of connectivity can be $$p \wedge q$$
		- This would mean `I am definitely getting an A and I am in denial`
>[!info] Order of Precedence 
> - $$\sim (\neg)$$ takes precedence over $$\wedge$$ and $$\vee$$
> - $$\wedge$$ and $$\vee$$ have the same precedence.
>>[!important] Important
>>- When dealing with $$\wedge$$ and $$\vee$$ parenthesis is needed to specify what comes first or else it is not considered a statement unless it contains all the same connectivity
>>>[!example] Example
>>>- Suppose we used the same example ***p*** and ***q*** above and introduce a new variable ***r***, suppose ***r*** = `I am reaching anger`
>>>	- $$p \wedge q \vee r$$ is not a valid statement(Parenthesis is needed!!!).
>>>	- $$(p \wedge q) \vee r$$ is a valid statement.
>>>	- $$p \wedge q \wedge r$$ is also a valid statement since all the connectivity are the same.




