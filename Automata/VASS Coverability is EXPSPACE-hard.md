
We will construct a VASS that can count up to precisely $2^{2^n}$.

We reduce from [TM](Turing%20Machines.md), via [Minsky machines](d-Counter%20Automaton.md) and [VASS](Vector%20Addition%20Systems.md) by simple programming languages:

- Minsky machines <-> counter programs
- VASS <-> net programs

> A counter program $C$ is a sequence of labelled instructions:
> $\ell: x++$
> $\ell: x--$
> $\ell: \text{goto } \ell$
> $\ell: \text{if } x = 0 \text{ goto } \ell_1 \text{else goto } \ell_2$
> $\ell: \text{halt}$

The following problem is EXPSPACE hard
Given a counter program $C$ and an unary encoded number $n$, does $C$ halt via a $2^{2^n}$-bounded run?

Let $L \in EXPSPACE$ and $M$ be a TM for $L$ using space $2^{p(n)}$ for some polynomial $p$. Given an input word $w = a_1 \dots a_n$ construct a TM $M_w$ which write $w$ on its empty tape and simulates $M$. Then $w\in L$ iff $M_w$ halts (on $\varepsilon$) via a run that uses at most $2^{p(n)}$ tape cells.

An $s$-space bounded TM can be simulated by a $2^{O(s)}$ bounded counter program:

We convert $M$ into a machine $P$ with two pushdowns. A tape with content $a_1a_2\dots a_n$ is split into two pushdowns with contents $a_k a_{k-1}\dots a_1$ and $a_{k+1} \dots a_n$ if the head is at position $k$. The pushdown heights are bounded by $s$.

Next we convert $P$ into a counter program $C$ with three counters. Assume that the stack alphabet is $\{1, \dots, b-1\}$, we read each pushdown as the $b$-ary representation of a number bounded by
$b^s \le 2^{O(s)}$. Pushdown operations can be simulated 
- `push(a)`: Multiply by b, add a.
- `pop(a)`: Subtract a, divide by b.
This can be implimented via the third counter.


> A net program $N$ is a sequence of labelled instructions:
> $\ell: x++$
> $\ell: x--$
> $\ell: \text{goto } \ell$
> $\ell: \text{ goto } \ell_1 \text{or goto } \ell_2$
> $\ell: \text{call } \ell$
> $\ell: \text{return}$
> $\ell: \text{halt}$
> Net programs are nondeterministic, we ask if there exists a run that reaches halt.


We work with _well-structured_ net programs, that means the program is decomposed into $k$ subprograms, we only jump inside a subprogram and subroutine calls are only from subprogram $i+1$ to subprogram $i$.

We transform a well-structured net program $N$ into a VASS $V$ with a state $f$ such that 
$$N \text{halts} \iff \text{state $f$ is reachable in $V$}.$$

$V$ contains
- a state for each instruction label
- a counter for each variable
- a counter for each subroutine call


It remains to reduce the $2^{2^n}$ bounded halting problem for counter programs to the halting problem for net programs.

Clearly we can simulate counter updates in VASS. 
To simulate zero test, we introduce a a copy $\overline s$ for each variable $s$, such that $s+\overline s = 2^{2^n}$, the net program then guesses whether $s > 0$ or $s=0$, to test whether $s > 0$ we first decrement and then increment $s$, to test $s=0$ we add $2^{2^n}$ to $s$ and subtract $2^{2^n}$ from $\overline s$, this swaps $s$ and $\overline s$.

We incremenet/decrement by $2^{2^n}$ by induction over $n$, assume we can increment/decrement by $2^{2^{n-1}}$, and we have zero test on $2^{2^{n-1}}$  bound counters, then the following procedure computes $s -= 2^{2^n}$ and $\overline s += 2^{2^n}$

```
repeat
	y--; y'++;
	repeat
		z--; z'++;
		s--; s'++;
	until z=-
until y = 0
```

Now given a counter program $C$ and a number $n$, we transform $C$ into a net program $N$ which contains all variables from $C$ and further auxiliary variables. Each variable $x$ in $N$ has a complementary variable $\overline x$, $N$ consists of two phases

- $N_{init}(C)$ initializes $\overline x = 2^{2^n}$ for all variables $x$
- $N_{sim}(C)$ simulates $C$ while maintaining $x+ \overline x = 2^{2^n}$

The simulation phase is easy, increments, decrements and unconditional jumps are simulated directly, we replace a condition jump by a program $\text{Test}_n(x, \ell_{=0}, \ell_{\not = 0})$.

>$\text{Test}_n(x, \ell_{=0}, \ell_{\not = 0})$
>call $\text{Test}'_n(x, \ell_{=0}, \ell_{\not = 0})$
>$\ell_{cont}:$ call $\text{Test}'_n(\overline, \ell_{=0}, \ell_{\not = 0})$ 
>

And 
> $Test_i'(x, \ell_{=0}, \ell_{\not= 0})$
> goto $\ell_{nz}$ or $\ell_{z}$
> $\ell_{nz}: x--, x++$
> goto $\ell_{\not=0}$
> $\ell_z: x++, \overline x --, s_i++, \overline s_i--$
> goto $\ell_z$ or $\ell_{brk}$
> $\ell_{brk}:$ call $Dec_i$
> goto $\ell_{=0}$

Where $Dec_i$ decrements by $2^{2^i}$ (recursively).

The main program $N_{init}$ initializes the variables of $N$ as follows
- All variables $x$ from $C$ are set to $0$ and their complementary variables $\overline x$ to $2^{2^{n}}$
- All variables $s_i$ are set to 0 and $\overline s_i$ to $2^{2^i}$
- For all $0 \le i \le n-1$ initialize $y_i, z_i$ to $2^{2^i}$ and $\overline y_i, \overline z_i$ to $0$


