---
aliases:
  - oracles
---

An oracale [TM](Turing%20Machines.md) is a TM $M$ with a special read/write tape(oracle tape), and three special states $q_{query}, q_{yes}, q_{no}$. To execute $M$ we provide in addtion to the input word a language $O \subseteq \lbrace 0, 1\rbrace^*$  called the oracle.

Whenever $M$ enters state $q_{query}$, the machine switches to state $q_{yes}$($q_{no}$) if the word on the oracle tape belongs to O(not)

The membership query is counted as a single computational step.
We write $M^O(x)$ for the output of $M$ on input $x$ with oracle $O$.

For each $O\subseteq\lbrace 0, 1\rbrace^*$ define $P^O$ and $NP^O$ be the classes of languages accepted by a poly-time (non)deterministic oracle TM with oracle access to O.
