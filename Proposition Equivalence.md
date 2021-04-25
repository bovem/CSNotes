# Proposition Equivalence

A [[Compound Proposition]] that is true no matter what is the truth value of [[Proposition (or State) Variables]] in it is called [[Tautology]].
Similarly, a compound proposition that is always false is called [[Contradiction]] and a compound proposition that is neither a tautology nor a contradiction is called [[Contingency]].

Compound Propositions that have same truth value in all the cases are called [[Logically Equivalent]]. 
If proposition P and Q are logically equivalent then $P \leftrightarrow Q$ is a tautology. 
It is represented as $P \equiv Q$.

Using this logical equivalence we can establish:

## 001 - [[De Morgan's Law]]
## 002 - [[Identity Law]]
## 003 - [[Domination Law]]
## 004 - [[Idempotent Law]]
## 005 - [[Double Negation Law]]
## 006 - [[Commutative Law]]
## 007 - [[Associative Law]]
## 008 - [[Distributive Law]]
## 009 - [[Absorption Law]]
## 010 - [[Negation Law]]

Notations like $p_1 \wedge p_2 \dots p_n$ could be summarized as $\bigwedge_{(i=1)}^n p_i$

A compound proposition is [[Satisfiable]] if there is an assignment of truth values to its variables that makes it **True**. Else it is [[Unsatifiable]].
The unsatifiable proposition is a tautology.
That assignment of truth values that make a compound proposition **True** is called [[Solution]].

## Satisfiability of Sudoku
To check satisfiability of sudoku over rows we follow these steps:
Here proposition $p(i, j, n)$ is true if number $n$ is in $i$th row and $j$th column.
1. Check if a cell in row $i$ contains at least one number out of (1-9). $$\bigvee_{j=1}^9 p(i, j, n)$$
2. Now we check if all the cells in row contain numbers out of  (1-9). $$\bigwedge_{n=1}^9\bigvee_{j=1}^9 p(i, j, n)$$
3. We can apply this all the rows.$$\bigwedge_{i=1}^9 \bigwedge_{n=1}^9 \bigvee_{j=1}^9 p(i, j, n)$$

Similarly, to check satisfiability over columns we have expression
$$\bigwedge_{j=1}^9 \bigwedge_{n=1}^9 \bigvee_{i=1}^9 p(i, j, n)$$

and to check satisfiability of $3 \times 3$ blocks we have expression
$$\bigwedge_{r=0}^2 \bigwedge_{s=0}^2 \bigwedge_{n=1}^9  \bigvee_{i=1}^3 \bigvee_{j=1}^3 p(3r+i, 3s+j, n)$$

We also check if a cell has only one number $$p(i, j, n) \rightarrow \neg p(i, j, n')$$ where $n \neq n'$

A sudoku is solved only when all of these 729 [[Proposition (or State) Variables]] are true.