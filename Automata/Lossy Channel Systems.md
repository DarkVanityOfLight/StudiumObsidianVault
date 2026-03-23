A _lossy channel system_ is a tuple $S = (Q, C, \Sigma, T, q_0)$ with components just as in a channel system. A configuration of $S$ is a tuple in $Q \times (\Sigma^*)^C$, but in contrast to [Channel Systems](Channel%20Systems.md) the step relation can lose before and after it modifies the channel:

We have $(q, \tau) \to (q', \tau')$ if there is a $\tau_1, \tau_2\in(\Sigma^*)^C$ such that
- for every $c \in C$, we have $\tau_1(c) \preceq \tau(c)$ 
- $(q,\tau_1) \to (q', \tau_2)$ is allowed by the rules of channel systems
- for every $c\in C$, we have $\tau'(c)\preceq \tau_2(c)$

We can define the following ordering on lossy channel systems:
$$(q, \tau) \le (q', \tau') \iff q = q'\text{ and }\tau(c) \preceq \tau'(c) \text{ for every } c\in C$$

With this ordering, lossy channel systems are [WSTS](Well-structured%20transition%20systems.md), and $\le$ is decidable on configurations $Q \times (\Sigma^*)^C$, given $(q,\tau)\in Q\times (\Sigma^*)^C$ on can compute a basis for $pre((q, \tau)\uparrow)$, therefore [coverability](Coverability%20Problem.md) is decidable for lossy channel systems.

