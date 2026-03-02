


Second Order Quantify Sets $X_1, ..., X_n$ corresponding to states $q_1, ..., q_n$. Position $i \in X_j$ means at position $i$ the Automata is in state $q_j$.
Then
$$\phi_A = \exists X_1 ... \exists X_n(\text{Partition} \land \text{Init} \land \text{Transition} \land \text{Final})$$

With

- $\text{Partition} := \forall x. \bigvee^n_{i=0} ( X_i(x) \land \bigwedge_{j \not = i} \neg X_j(x))$ 
- $\text{Init} := \exists x. first(x) \land \bigvee_{i\in I} X_i(x)$
- $\text{Transition} := \forall x, y. Succ(x, y) \to \bigvee_{(p, a, q)\in \Delta} X_p(x) \land X_q(y) \land P_a(y)$
- $\text{Final} := \exists x. last(x) \land \bigvee_{(p, a, q) \in \Delta, q \in F} X_p(x) \land P_a(x)$


---

Assume the MSO sentence is in MSO0, meaning no FO Quantifiers. That means the following Atomic formulas exist:

- $Sing(X)$ checks if $X$ is a singelton
- $Succ(X, Y)$ checks that the singleton $Y$ follows the singleton $X$
- $X \subseteq Y$ Subset of a set
- $X \subset P_a$ subset of a given relation


The translation then follows the generic Logic -> Automata Construction


A simple Corollary by converting forth and back, is that every MSO sentence is equivalent to some existential MSO sentence