---
title: Turing Machines
aliases:
  - Multi-Tape Turing Machine
  - Turing Machine
  - TM
tags:
  - computability
  - complexity
---

## Multi-Tape Turing Machine

- **Input tape**: read-only
- **Work tapes**: read/write (one or more)
- **Output tape**: write-only

**Definition (K-tape TM)**
> $M = \langle Q, \Sigma, \Gamma, \Omega, \Delta, q_0, F\rangle$, where:
> - $Q$: finite set of states
> - $\Sigma \subseteq \Gamma$: input alphabet
> - $\Gamma \cup \{\square\}$: tape alphabet ($\square$ = blank symbol)
> - $\Omega$: output alphabet
> - $\Delta \subseteq (Q\setminus F) \times \Gamma^k \times Q \times \Gamma^k \times (\Omega\cup\{\varepsilon\}) \times \{-1,0,1\}^k$: transition relation
> - $q_0$: initial state
> - $F \subseteq Q$: set of halting (final) states

A transition

> $(p, a_1, \dots, a_k,\; q, b_1, \dots, b_k,\; c,\; d_1, \dots, d_k) \in \Delta$

means:

1. In state $p$, each head $i$ reads symbol $a_i$.
2. Switch to state $q$.
3. Write symbol $b_i$ on tape $i$.
4. Output $c$ (or $\varepsilon$ if none).
5. Move head $i$ by $d_i \in \{-1,0,1\}$.

$M$ is **deterministic** if $\Delta$ is a function.

![](Turing%20Machines%202025-04-27%2018.40.31.excalidraw)

---

## Configurations & Computations

A **configuration** is a tuple
$$(q, u_1, i_1, u_2, i_2, ..., u_k, i_k, v)$$

- $q \in Q$: current state
- $u_i \in \Gamma^+$: contents of tape $i$
- $i_i$: head position on tape $i$
- $v \in \Omega^*$: output so far

Initial configuration on input $w \in \Sigma^*$:

$$c_0 = (q_0, w, 1, \square, 1, ..., \square, 1, \varepsilon)$$

We write $c_1 \vdash_M c_2$ if $c_2$ is a successor of $c_1$.

A computation is a (finite or infinite) sequence

$$c_0, c_1, c_2, ...$$
- Each step satisfies $c_{i-1}\vdash_M c_i$.
- A **halting** computation ends in a config with state $q\in F$, producing output $v$.

The **function** computed by a deterministic TM is a (partial) map
$$M: \Sigma^* \rightarrow \Omega^*$$

where $M(x)=y$ iff TM halts on input $x$ with output $y$.

A **language** $L \subseteq \Sigma^*$ is **decidable** if its characteristic function
$$X_L(x) \lbrace 1 \text{ if } x\in L; 0\text{ otherwise}\rbrace$$
is computed by a deterministic TM.

A **nondeterministic** TM **accepts**
$$L(M) = \lbrace x | \exists \text{ halting computation on $x$ with output $=1$}\rbrace$$


---

