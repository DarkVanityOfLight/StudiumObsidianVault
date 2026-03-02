
There exists an undecidable language.


Define $L = \lbrace x\in\lbrace 0, 1\rbrace^* | M_x \text{ does not accept } x\rbrace$
Suppose $L$ is decidable, that is there is a [TM](Turing%20Machines.md) $M$ with $L = L(M)$.
Let $x$ be the encoding of $M$. Then
$$x \in L \iff M_x = M\text{ accepts } x\iff x\not\in L$$
