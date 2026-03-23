A channel system is a tuple $S = (Q, C, \Sigma, T, q_0)$ where
- $Q$ is a finite [set](Mengen.md) of states
- $C$ is a finite set of channels
- $\Sigma$ is an [Alphabet](Alphabet.md)
- $T \subseteq Q \times C \times (\Sigma^* \cup \overline \Sigma^* \times Q)$ is a finite set of transitions
- $q_0 \in Q$ is the initial state

A configuration of $S$ is a tuple in $Q \times (\Sigma^*)^C$
We write $(q, \tau) \to (q', \tau')$ if there is a transition $(q, c, x, q')$,
$x\in \Sigma^* \cup \overline\Sigma^*$, with
- $x = u\in\Sigma^*$ and $$\tau'(d) = \begin{cases}\tau(c)u &\text{if } d = c \\ \tau(d) &\text{if } d\not=c\end{cases}\text{ for every } d \in C$$
- $x = \overline u$ for some $u\in\Sigma^*$ and $\tau(c) = uw$ for some $w\in \Sigma^*$ and $$\tau'(d) = \begin{cases}w &\text{if } d = c\\\tau(d) &\text{if } d\not = c\end{cases}\text{ for every } d\in C$$

Even [State Reachability](State%20Reachability.md) is undecidable in channel systems.
We show this by reduction from [2-Counter Automaton](d-Counter%20Automaton.md). We encode $n\in\mathbb N$ as channel content $\triangleright a^n \triangleleft$. We can assume that each transition in the counter automaton either increments, decrements or zero tests,
Increment
![](Channel%20Systems%202026-03-08%2015.37.28.excalidraw)
Decrement
![](Channel%20Systems%202026-03-08%2015.40.51.excalidraw)
Zero Test
![](Channel%20Systems%202026-03-08%2015.41.57.excalidraw)

