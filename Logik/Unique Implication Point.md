
A __UIP__ in a [conflict Graph](Implication%20Graph.md) is a node $v\not = \bot$ with the highest decision level $l$ such that any path from the guessed literal at level $l$ to $\bot$ visists $v$.

The guessed literal at level $l$ is one UIP

## 1-UIP

First UIP is a UIP that is closes to $\bot$

>Any conflict graph contains a unique 1-UIP

## UIP generated Cuts

Given a UIP $v$ in a conflict graph $G = (V, E)$, the cut generated by $v$ is
$$\left(V\setminus \text{post}^+(v), \text{post}^+(v)\right)$$
where $\text{post}^+ = \lbrace w \in V : v \to_E^{+} w\rbrace$


## Asserting Clauses

Conflict Clauses leraned via 1-UIP $l$ have the feature that 
- $\neg l$ will be implied by BCP after backtracking
- Such a conflict clause is said to be asserting

Some learning/backjumping strategies might produce conflict clauses that are not asserting.

## Conflict arising at decision level 0

This means that we deduce $\bot$ from $\varphi$ using only [Boolean Constraint Propagation](Boolean%20Constraint%20Propagation.md)]. This corresponds to a resolution proof of unsatisfiability.


## Conflict arising at decision level 1

The second highest decision level at current decision level $1$ might not be well defined, for example when no nodes $v$ with $l_T(v) = 0$ exist in the graph.

We then pop the trail stack all the way till(including the top level) guessed literal