---
aliases:
  - full trio
---

An asynchronous transducer is a machine $T = (Q, \Sigma, \Gamma, \delta, q_0, F)$, where 
- $Q$ is a finite state set
- $\Sigma$ the finite input alphabet
- $\Gamma$ the finite output alphabet
- $\delta\subseteq Q \times (\Sigma \cup \{\varepsilon\}) \times (\Gamma \cup\{\varepsilon\}\times Q$ a set of transitions
- $q_0\in Q$ the initial state
- $F \subseteq Q$ a set of final states

A transducer accepts a subset of $\Sigma^* \times \Gamma^*$, denoted $L(T)$


Given a [language](Sprache.md) $K \subseteq \Sigma^*$ and a transducer $T$, $TK \subseteq \Sigma^*$ is defined to be the language obtained by application of $T$ on $K$.

$$TK := \lbrace v\in\Gamma^* | \exists u\in K . (u, v) \in L(T)\rbrace$$

> [!DEFINTION]
> A language class $\mathcal C$ is said to be closed under rational transductions if for every $K\in\mathcal C$ and every asynchronous transducer $T$, we have $TK \in \mathcal C$


A language class closed under rational transductions is also called a _full trio_. We also assume that this is effective, meaning we can compute a representation for $TK$.

