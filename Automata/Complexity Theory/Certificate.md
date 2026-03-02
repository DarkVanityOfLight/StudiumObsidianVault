[NP](NP.md) is defined as $\bigcup_k NTIME(n^k)$ or more intuitive:

A language $L\subseteq\lbrace 0, 1\rbrace^*$ is contained in NP if and only if there exists $V\in P$ and a [polynomial](Polynome.md) $p(n)$ such that for all $x\in\lbrace 0, 1\rbrace^*$:
$x \in L \iff \exists u \in\lbrace 0, 1\rbrace^{P(|x|)} : \langle x, u\rangle \in V$


__Proof:__
Let $L\in NP$, then there exists a nondeterministic $p$-time bounded [TM](Turing%20Machines.md) $M$, $L(M) = L$. For every $x\in L$ there exists an accepting computation of $M$ on $x$ that we can use as certificate.

It can be encoded in $\log(|\Delta|) \cdot p(|x|)$ bits.
We choose $V = \lbrace \langle x, c\rangle | c \text{ is an accepting computation of} M \text{ on } x\rbrace$ which is polynomial time.

Conversly a nondeterministic TM can guess and verify a certificate in polytime.

