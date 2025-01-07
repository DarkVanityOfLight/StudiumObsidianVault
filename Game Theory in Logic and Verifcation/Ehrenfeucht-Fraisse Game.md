Given two $\sigma$-[structures](Structure.md): $\mathfrak A, \mathfrak B$ with constant symbols $\overline c = (c_1, \dots, c_m)$ 
If $\mathfrak S = \mathfrak A$, then $\overline S = \mathfrak B$(and the other way around respectively).

There are 2 players: __Spoiler__ and __Duplicator__.
Spoiler and Duplicator move in turns for $n \in\mathbb N$ rounds.

At round $i$:
1. Spoiler picks a structure $\mathfrak S$ and element $s_i$ in it
2. Duplicator picks an element $s_i'$ in $\overline{\mathfrak{S}}$

 After $n$ rounds: Two tuples $\overline a \in A^n$ and $\overline b\in B^n$ are generated.
 Duplicator wins iff $((\overline a, \overline c^\mathfrak A), \overline b, \overline c^\mathfrak B))$ defines a [partial isomorphism](Isomorphism.md#Partial%20Isomorphism) between $\mathfrak A, \mathfrak B$.

## Winning Strategies
Write $\mathfrak A \equiv_n\mathfrak B$ if Duplicator has a winning strategy on the $n$-round EF games on $\mathfrak A,\mathfrak B$.


