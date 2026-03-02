
Assume we are given a NBA $A = (Q, \Sigma, I, \Delta, F)$ with $|Q| = n$, we construct the following MSO formula, representing each state as an infinite set of positions at which it appears.

$$\exists X_1, ..., X_n. \text{Partition} \land \text{Initial} \land \text{Transition} \land \text{Acc}$$
with

- $\text{Partition} := \forall x. \bigvee_{i \in Q} (X_i(x) \land \bigwedge_{j \not = i} \neg X_j(x))$
- $\text{Initial} := \exists x. first(x) \land \bigvee_{q \in I} X_q(x)$
- $\text{Transition} := \forall x, y. Succ(x, y) \to \bigvee_{(p, a, q) \in \Delta} X_p(x) \land P_a (x) \land X_q(y)$
- $\text{Acc} := \forall x. \exists y. x > y \land \bigvee_{q \in F} X_q (y)$
- 


For the converse we apply the standard Logic -> Automaton Translation, utilizing the closure properties of $\omega$-regular languages.

