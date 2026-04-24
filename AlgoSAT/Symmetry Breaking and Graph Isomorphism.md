
There is no polynomial-time algorithm solving the [Complete Symmetry Breaking](Complete%20Symmetry%20Breaking.md) problem unless $GI \in coNP$.

Assume the symmetry breaking problem can be solved in ptime. We prove $\overline GI \in NP$.

The certificate are the [bijections](Bijektiv.md) $\varphi: V(G_1) \to \{1, \dots, n\}$, $\psi: V(G_2) \to \{1, \dots, n'\}$.

To check we do the following:
If $n\not = n'$ reject.
Using the oracle, construct a symmetry breaking circuit $C$ for $Sym(\{1, \dots, n\})^{(2)}$
If $C[\tau_{\varphi(G_1)}] \not =  1$ reject
If $C[\tau_{\psi(G_2)}] \not =  1$ reject
If $\varphi(G_1) = \psi(G_2)$ reject
Otherwise accept.

