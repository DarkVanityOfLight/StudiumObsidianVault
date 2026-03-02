
Diagonalization views [TMs](Turing%20Machines.md) as black boxes. It only depends on
1. Some efficient encoding of TMs
2. the ability of a single TM to simulate all TMs without much overhead in time/space

We show that certain TMs also satisfy the two properties above

In one variant we prove $P = NP$
In another one we prove $P\not = NP$

Thus viewing TMs as black boxes with the properties above is too weak to resolve the P vs NP question.

 
There exists [oracles](Oracle%20Turing%20Machine.md) $A, B$ such that $P^A = NP^A$ and $P^B \not = NP^B$.

Choose $A = EXPCOM = \lbrace \langle M, x, 1^n\rangle | M\text{ outputs } 1 \text{ within } 2^n\text{ steps}\rbrace$

$$P^A = NP^A = EXPTIME$$

For $B$, define a unary language
$$U_B = \lbrace 1^{|x|} | x\in B\rbrace$$
For every $B$, $U_B \in NP^B$  since a nondeterministic TM can guess on input $1^n$ a word $x$ of length $n$ and test $x\in B$ using the oracle.

Now construct some $B$ with $U_B \in P^B$.
Let $M_i$ be the oracle TM with encoding $bin(i)$. We construct $B$ in stages $i=1,2,3$

In phase $i$ we ensure that $M_i^B$ does not accept $U_B$ in $2^n - 1$. Initially $B=\emptyset$, and each step determines the states of finitely many words.

In stage $i$ we have defined the status of finitely many words. Let $n$ be strictly larger than their maximal length. Run $M_i^B$ on $1^n$. Whenever $M_i$ queries the orcale $x\in B$ and the status of $B$ was already defined, answer consistently. Otherwise, we declare that $x\in B$. If $M_i$ halts in $2^n - 1$ time, we wish to ensure that its answer is incorrect.

- If $M_i$ accepts, we declare that all other strings in $\lbrace 0, 1\rbrace^n$ also does not belong to $B$. Thus $1^n \not\in U_B$
- If $M_i$ rejects, we pick any $x\in\lbrace 0, 1\rbrace^n$ with undetermined status. It exists because in time $2^n-1$ we can make at most $2^n - 1$ many oracle queries. Declare $x\in B$. Thus $1^n \in U_B$

Assume $U_B \in P^B$. Let $M$ be a oracle TM running in poly time $p(n)$ such that $U_B = L(M^B)$. We can pick $i$ large enough so that $M_i = M$ and $2^n - 1> p(n)$ for the $n$ picked in stage $i$. Hence $M = M_i$ halts in $p(n) < 2^n -1$ steps and its answer on $1^n$ must be incorrect.



