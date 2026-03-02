

Assume we are given a $\omega$-Regular language, we construct an NBA.

- $L^\omega$, given $L$ as an NFA, with a unique initial state, we connect the end states to the inital state using $\varepsilon$ transitions and make only the initial state final.
- $L.L'$ Assume $L$ is given as an NFA, and $L'$ as a NBA. We connect the final states of $L$ using $\varepsilon$ transitions to the initial states of $L'$
- NBA's are trivially closed under union.

---

Assume we are given a NBA $A$, we can write it as
$$L = \bigcup_{p\in I, q\in F} L_{p, q} L_{q, q}^\omega$$
Where both $L_{p, q}$ and $L_{q, q}$ are regular languages, this is a valid $\omega$-regular expression.

