We can convert a [Unit Propagation](Unit%20Propagation.md) proof into a [Resolution](AlgoSAT/Resolution.md) proof:

Given a conflict by unit propagation on $F\land \neg C$, we can construct a resolution proof of $\bot$.

We go backwards, starting from the conflict clause and resolve with the _antecedent clause_ of propagated literals.

UP results in a sequence of propagated literals $\ell_1, \ell_2, \dots \ell_n$. Each propagated literal $\ell_i$ has an antecedent clause $A_{\ell_i} = (\ell_i \lor \overline \ell_{i_1} \lor \dots \lor \overline l_{i_k})$ such that all $\ell_{i_j}$ were already unit earlier. The conflict clause consists of the negations of the propagated literals that appear in contradiction
$$C_{conflict} \subseteq \{\overline\ell_1, \overline \ell_2, \dots, \overline\ell_n\}$$
where all $\ell\in C_{conflict}$ were propagated

We now construct the resolution proof backwards from the conflict.
Start from the conflict clause $C_{conflict}$, pick the latest propagated literal $\ell_i$ occurring in it and resolve it with its antecedent $A_{\ell_i}$
$$C' = C_{conflict} \bowtie A_{\ell_i} = (C_{conflict} \setminus \{ \overline \ell_i \}) \lor (\overline\ell_i \lor \dots \lor \overline l_{i_k})$$
we replace $\ell_i$ by its earlier reasons. We repeat this step for each $\ell$ in reverse order of propagation, when no propagated literal remains, we obtain $\bot$. Each resolution step replaces a later unit by earlier units.

