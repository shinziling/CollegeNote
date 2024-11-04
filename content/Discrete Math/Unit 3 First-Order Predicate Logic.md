A predicate is an expression that is either `true` or `false`. This depends on the value that is substituted for the variable. When defining a predicate the domain must also be specified. 
- A predicate is not a statement. But we can transform predicate into quantified statement. But for now this is an predicate: 
	- $P(x)$ = "x is odd", where x is an integer ($\Bbb{Z}$)
> Observe that we defined the predicate and the domain of x.

The domain of the variable does not have to be just numbers and we can also have multiple variables in a predicate.

>[!example]
>
>- $P(x,y) =$ "x > y", where $x, y \in \Bbb {R}$
>- $R(a, b) =$ "Student A is taller than Student B", where $a, b$ are students in your school

Logic connectivity can be used to connect different predicates together

>- $P(x) = \neg R(x) \wedge Q(x, y)$
>- $T(x, y) = \neg R(x) \to L(y)$

## Quantifiers (Universal and Existential)

There is two types of quantifiers: Universal $(\forall)$ and Existential $(\exists)$
- They are the negation of each other so negating $\forall$ becomes $\exists$ and vice versa

Definition: 
- $\forall$ means "for all" or "for every". 
- $\exists$ means "there exists some" or "at least one". 

### Quantified Statement

Combining predicate(s) and quantifier(s) (as well as some domains), we can create a quantified statement.
- $(\forall x \in \Bbb {Z})[P(x)]$
	- This means "for all integer x, P(x) holds or P is true about x"
- $(\exists x \in \Bbb {Z}) [R(x)]$
	- This means "there exists a integer x (at least one) such that R(x) holds or R is true about x"

### Variable Scope for Quantified Statement

This is similar to block scope in programming where variables are bounded to a predicate or predicates. Think global variable and local variable. The scope of the variable in a quantified statement is determined by the set of bracket that comes after the variable domain.
- The bracket is not an official way to determine variable scope, it actually depends on the context since different individuals, professors, and textbooks have different ways of expressing variable bound. 
	- Some just write out in plain English, some don't use bracket at all. 

At the end of the day when writing mathematical notation you want to be as clear as possible. But for now the bracket is there to help understand mathematical logic.

>[!example]
>- $(\forall x \in \Bbb {N}) [P(x)] \wedge (\forall y \in \Bbb {Z}) [R(y)]$
>> The $x$ is bounded to the P and the $y$ is bounded to R. 
>
>How about this one?
>- $(\forall x \in \Bbb {N}) [P(x) \wedge T(x)] \vee (\forall x \in \Bbb {R}) [R(x)]$
>>[!success]- Solution
>>
>>Although there are two $x$, they are different $x$, the first $x$ is bounded to P and T but the second one is bounded to R. But please don't do this, it makes it confusing to follow your notation, use different variables for each one. 

## Vacuous Statement
These are just statements that we just say it is true or false (It just works).<br>
Consider the domain $D$ where $D$ is empty
- $(\forall x \in D) [P(x)]$ is vacuously true.
	- This is a true statement since if the domain $D$ is empty then it means that P always holds for all $x$ in $D$ because $D$ is empty.
- $(\exists x \in D)[P(x)]$ is vacuously false.
	- This is a false statement since if the domain $D$ is empty then there cannot possibly exist any $x$ where P holds because $D$ is empty.
> This concept of vacuous statement is not very important so there is no needs to worry about this. 


>[!info] Specifying Domain 
>Sometimes it is not needed to explicitly write the domain for each variable if: 
>- The domain was specify in advance or it is obvious from the context.
>>[!example]-
>>
>>Suppose the domain is all real number $\Bbb {R}$ 
>>- $(\forall x) [P(x)]$
>>>Notice I did not explicitly write out the domain for $x$ because I already specify the domain to be all real number in advance

### Multiple and Different Quantifiers

A quantified statement can have multiple quantifiers defined for a predicate.

>[!example]
>1. $(\forall x \in \Bbb {N}) (\exists y \in \Bbb {Z}) [P(x, y) \wedge R(y)]$
>2. $(\exists x \in \Bbb {R}) (\exists y \in \Bbb {R}) [P(x, y)]$
>> If multiple variables have matching quantifiers and domain then we can simplify the notation.
>
>For example, for number 2 the $x$ and $y$ have the same quantifiers and domain, so we can simplified that to: 
>- $(\exists x, \exists y \in \Bbb {R}) [P(x, y)]$

When dealing with different quantifiers, order actually matters.
- Consider the quantified statement:
	- $(\forall x \in \Bbb {N}) (\exists y \in \Bbb {Z}) [P(x, y)]$
		- This is not the same as $(\exists y \in \Bbb {Z}) (\forall x \in \Bbb {N}) [P(x, y)]$
- Example: 
>[!example]
>Suppose the domain is all real numbers
>$P(x, y)$ means "x > y"
>1. $(\forall x)(\exists y) [P(x, y)]$
>	- This reads "for all $x$, there exists a $y$ such that x > y". This is true, for every $x$ you can always find a $y$ in the set of all real number that is smaller than $x$. Note: This statement may be false in some other domains but not in the domain I have defined.
>2. $(\exists y)(\forall x) [P(x, y)]$
>	- This reads "there exists a y such that for all x, x > y". This is false, there does not exists a real number $y$ where all $x$ is greater than that $y$, there is always going to be some $x$ that is less than that $y$. Again, this may be true in some other domains but not in the domain I have defined.


>Order does not matter if all the quantifiers used are the same.

## Negating Quantified Statement

Move the $\neg$ symbol down until you reach the predicate and "flip" all quantifiers. 

>[!example]
>
>- $\neg ((\forall x) (\exists y) [P(x, y) \wedge R(y)]) \equiv (\exists x) (\forall y) [\neg P(x,y) \vee \neg R(y)]$
>

>[!note]
>Given: 
>- $\neg ((\exists x)[P(x)]) \equiv (\forall x)[\neg P(x)]$
>>This reads "For all x, P is not true about x" or "There is no x such that P is true about x".

## Converting Statements into Quantified Statement

Assume the domain is all natural number $\Bbb {N}$ (0 is a natural number, we are not having an argument over this). 

1. x is even
2. x is odd
3. x is a square

>[!success]- Solution
>
>1. $(\exists x,k) [x = 2k]$
>2.  $(\exists x,k) [x = 2k + 1]$
>3.  $(\exists x,y) [x = y * y]$


### At least, At most, Exactly Statements

For these statements I will just convert them and explain why. <br>
Assume the domain is all creatures $C$. Let $V(x)$ means "x is vampire". 

1. There is at least one vampire.
> $(\exists x)[V(x)]$
> - This is pretty self explanatory, "there exists some creature x (at least one) such that x is a vampire".

2. There are no vampire.
>Negate the previous statement
>$(\forall x) [\neg V(x)]$
>- Again self-explanatory, "for all x, x is not a vampire".

3. There is at least two vampires.
>$(\exists x, y)[V(x) \wedge V(y) \wedge x \neq y]$
>The idea is that there is two vampires but we have to make sure they are not the same vampire.

4. There is at most one vampire.
>$(\forall x, y) [V(x) \wedge V(x) \to x = y]$
>Here, we are saying "it is not the case that there are at least 2 vampires", so we negate the previous statement. This basically reads "If x is vampire and y is a vampire then they must be the same vampire". Recall that arrow means implication and $x \to y \equiv \neg x \vee y$ from the equivalence chart. Also remember that $\wedge$ has a higher precedence than $\to$

5. There is at most two vampire
>$(\forall x, y, z) [(V(x) \wedge V(x) \wedge V(z)) \to (x = y \vee x = z \vee y = z)]$
>Same ideas as above. This reads "if x, y and z are all vampires then x must be the same as y or x is the same as z or y is the same as z", so one of the vampires must be the same vampire as the other two. 

7. There is exactly one vampire.
>$(\exists x)[V(x) \wedge (\forall y)[V(y) \to y = x]]$ or $(\exists x)(\forall y)[V(x) \wedge (V(y) \to y = x)]$
>Here, we are saying "there is at least one vampire AND there is at most one" so we can just combine the "at least one" statement with the "at most one" statement but that looks ugly. Instead, we just say "there exists a vampire x and for all y, if y is a vampire then y must be the same vampire as x".

7. There is exactly two vampires. 
>$(\exists x, y)[V(x) \wedge V(y) \wedge x \neq y \wedge (\forall z)[V(z) \to (z = x \vee z = y)]]$ or $(\exists x, y)(\forall z)[V(x) \wedge V(y) \wedge x \neq y \wedge (V(z) \to (z = x \vee z = y)]$
>Again same idea as above combine the statement "at least two" with the statement "at most two" but that looks ugly. Instead, we just say, "there exists a vampire x and a vampire y such that x and y are not the same vampire, and for all z, if z is a vampire then z must either be the same vampire as x or y."


>[!success] You can apply the same strategy for any $n$ vampires for each category (at least $n$, at most $n$, and exactly $n$).


## Interpretation
Applying an interpretation means assigning a domain to each variable(s) and a meaning to the predicate symbol(s). Basically, you are applying a model to a formula. 
- Variables not bounded by quantifiers are called **free variables**
	- Statements and sentences cannot have free variables.
		- A sentence is not a statement if any variables is not assigned a domain and if any predicate symbol is not assigned a meaning.

>Quantified Statements are statements.

**Example: Determine if the followings are statement, sentence or neither (Assume all predicates are assigned a meaning)**

1. $(\forall x, y \in \Bbb {R})[P(x, y)]$
2. $(\exists x \in \Bbb {N})[P(x)] \wedge P(x)$
3. $(\forall y \in \Bbb {Z})[P(y)] \wedge R(2.7)$
4. $(\exists y)[P(y)] \wedge (\forall y)[R(y)]$

>[!success]- Solution
>
>1. Statement. Both variables are bounded to all real numbers and we are assuming the predicate has a meaning assigned to it
>2. Neither. Although the first x is bounded to all natural numbers and the second x is a free variable that is not bounded to anything and does not have a quantifier (See [[#Variable Scope for Quantified Statement|Variable Scope]]).
>3. Statement. Variable y is bounded and has a quantifier. 2.7 is a real number that is passed into the predicate itself. 
>4. Sentence. The first y is bounded and with a quantifier. The second y has a quantifier but it is not bounded to any domain (See [[#Variable Scope for Quantified Statement|Variable Scope]]).

