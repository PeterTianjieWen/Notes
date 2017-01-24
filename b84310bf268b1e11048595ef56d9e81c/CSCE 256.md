# Lecture 2

## Logic

Logic helps us to specify the precise meaning of a mathematical statement 

Logic teaches the `RULES` 


`Application`:
For developing a system, wen precise and unambiguous specifications
System and software engineers take requirements in natural language and produce precise and unambiguous specifications 

## Propositions

We will use variables to represent proposition.

* **How can declarative sentence fail to be a proposition** 
	* `Opinions` `interrogative` `imperative`
	*	unspecified term

### Propositional Calculus or Logic



**Building a Machine**: 
SImple Propositions -> `Logical Operators` -> Compound Propisition

## Negetation 
The negation of proposition $p$ is $\neg p $


## Logical `And`
 
* also referred to as a conjunction
* Note : **Both of the propositions are true**
 

## Logical OR $\lor$
* also referred to as a disjunction
one or both of the propositions are true 

## Exclusive $\leor$
* is true when exactly one of its propositions is true and the other one is false.

Example: `The circuit is either is on or off`
***
##Implications/Conditional Statements
Representative word: **for if then**
* WE may form a compound proposition using two propositions p and q 
		via 
		
* WE can think of p -> p as being a promise that whenever p is true, q will be true also
* If p is true then i am claiming that q is true 
**Otherwise i am making no claim.**
* There is only one way this promise can be broken and that is if p is **true** but q is **false** 
     			$p$`Sufficient condition` $\rightarrow$ $q$`Necessary condition`
   
   * $p\rightarrow q $ can be true even if the sufficient condition is not met(	$p$ is not true)  			
   * $p\rightarrow q $ will be false
   * From **Sufficient** we know that the latter part is hypothesis.
   * From **Necessary** we know that the former part is hypothesis.
***
###Conditional Statements

* In propositional logic, we consider conditional statements of a **more general sort** than we use in English
* The **mathematical concept** of a conditional statement is **independent of a cause-and-effect relationship** between hypothesis and conclusion    

**Conditional statements specify truth values and it is not based on English usage**    
**Propositional language is an artificial language**
***
##Biconditional
Signal word: **if and only if, necessary and sufficient, conversely, iff**
E.g: `An integer a is divisible by 2 if and only if it is even`
p: An integer a is divisible by 2
q: The integer a is even
$$q \rightarrow p$$
$$p \rightarrow q$$
$$\Rightarrow p \leftrightarrow q$$
***
## Converse, Contrapositive and Inverse

Forming new conditional statements starting with $p \rightarrow q$:
* The proposition  $q \rightarrow p$ is called the **converse** of the proposition  $p \rightarrow q$
*  The **contrapositive** of the proposition is $\neg q \rightarrow \neg p$
*  The **inverse** of the proposition is $p \rightarrow q$
     
 Truth Tables are used to **show the relationship** between the **truth values** of **individual propositions** and the **compound propositions** based on them.
 
To avoid using unnecessary parentheses, we define the following precedences:
1. ($\neg$) Negation
2. ($\land$) Conjunction 
3. ($\lor$) Disjunction 
4. ($\rightarrow$) Implication 
5. ($\leftrightarrow$) Biconditional

Express the  specification :“The automated  reply cannot be sent when the file system is full” using logical connectives.
`
“The diagnostic message is stored in the buffer or it is retransmitted.”
“The diagnostic message is not stored in the buffer.”
“If the diagnostic message is stored in the buffer, then it is retransmitted.”
`


* In order to **verify** the consistency, these English sentences need to be translated into logical statements

###Logic Puzzles
* Puzzles that can be solved using **logical reasoning** are known as logic puzzles
	* excellent way to practice working with rules of logic
	* Also,computer programs designed to  carry out logical reasoning often use well-known logic puzzles to illustrate their capabilities


