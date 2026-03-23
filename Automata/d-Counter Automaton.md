---
aliases:
  - Minsky Machine
---

A $d$-counter automaton is a tuple $(Q, T, q_0)$, where
- $Q$ is a finite set of states
- $T\subseteq Q \times (\mathbb Z \cup \{z\})^d \times Q$
- $q_0 \in Q$ is its initial state

A _configuration_ is a pair $(q, \textbf(u)) \in Q \times \mathbb N^d$.
In a _transition_ $(q, \textbf{v}, q')$, we add $\textbf{v}[i]$ to counter $i$, and if $\textbf{v}[i] = z$, then we check if counter $i$ is zero.

We write
$$ (q, \textbf{u}) \to (q', \textbf{u})$$
for configruartions $(q, \textbf{u}), (q', \textbf{u}')$ if there is a $(q, \textbf{v}, q') \in T$ where for each $i\in \{1, ..., d\}$:
- If $\textbf{v}[i] \in \mathbb{Z}: \textbf{u}[i] + \textbf{v}[i]$
- If $\textbf{v}[i] = z$ then $\textbf{u}[i] = \textbf{u}'[i] = 0$

We write $\to^*$ for the _reflexive, transitive_ closure of $\to$ on the set of configurations.


The state reachability problem for $2$-counter Machines is undecidable.

We reduce via the undecidability of [2-PDA](d-Pushdown%20Automaton.md).

We encode a configuration a configuration $(q, u, v)$ of a 2-PDA with [Alphabet](Alphabet.md) $\Gamma = \{0, 1\}$, by representing each word as binary encodings. Let $u = u_1 \dots u_k$ and $v = v_1 ... v_l$,
$$\begin{align}
a = 2^k + 2^{k-1} \cdot u_1 + 2^{k-2} \cdot u_2 + \dots + 2^0 \cdot u^k\\
b = 2^l + 2^{l-1} \cdot v_1 + 2^{l-2} \cdot v_2 + \dots + 2^0 \cdot v^k\\
\end{align}$$

The terms $2^k$ and $2^l$ guarantee that the encoding is [injective](Injektiv.md), if we don't include the extra digit, the words $u=001$ and $v=01$ encode the same number $a = b=1$.

A $\overline{0}$ pop from the first stack we divide the counter by $2$
![](d-Counter%20Automaton%202026-03-02%2014.58.54.excalidraw)

A $\overline 1$ pop from the first stack is implemented by substracting 1 and dividing by 2.
![](d-Counter%20Automaton%202026-03-02%2015.02.48.excalidraw)
Here we need to make sure that initally the counter value was not $1$, else it could be that the counter value is $1$ meaning the stack is empty.

To push a $0$ to the first stack, we double the counter value:
![](d-Counter%20Automaton%202026-03-02%2015.05.10.excalidraw)

To push a $1$ we double the counter and then add $1$:

![](d-Counter%20Automaton%202026-03-02%2015.07.10.excalidraw)


A counter machine is _s-deterministic_, if every transition only changes counters by $+e_i$ or $-e_i$.

A counter machine is called _accumulating_ if for every infinite run 
$$(q_0,u_0) \to (q_1,u_1) \to \cdots$$
the sequence 
$$\|u_0\|, \|u_1\|, \ldots$$
is unbounded.
Any $d$-counter machine can be transformed into a _accumulating_ machine by adding a new counter and increasing it after every transition.

