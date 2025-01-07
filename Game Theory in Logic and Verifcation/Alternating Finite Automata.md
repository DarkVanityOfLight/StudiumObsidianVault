

An AFA $A$ over an [alphabet](Alphabet.md) $\Sigma$ is a tuple
$$A = \langle Q, \Sigma, \Delta, q_0, F\rangle$$

where
1. $Q$ is a finite set of states
2. $q_0\in Q$ is the initial state
3. $F\subseteq Q$ is a set of final states
4. $\Delta: Q\times\Sigma \to B^+(Q)$ is the transition function, where $B^+(Q)$ is the set of all positive Boolean formulas with variables $Q$

## Runs

We define acceptance of an input word $w = a_1 \dots a_n$.
We do this by defining a run as sequence of sets of states
$$Q_0, \dots, Q_n$$
such that:
1. $Q_0 = \lbrace q_0\rbrace$ and $Q_i \subseteq Q$ for each $i = 1, \dots, n$
2. For each $i = 1, \dots, n, Q_i$ is satisfying assignment of $\bigwedge_{q\in Q_{i-1} \Delta(q, a_i)}$ 

This run is accepting if $Q_n \subseteq F$
A word $w$ is accepted if there's an accepting run on $w$.
The language $L(A)$ of $A$ contains precisely all words accepted by $A$.

## Membership

Given an AFA $A$ over $\Sigma$, a word $w\in\Sigma^*$, decide if $w\in L(A)$.
Membership for AFA is decidable in PTIME. We can prove this by establishing an intuitive interpretation of membership as two player [reachability game](Reachability%20Game.md).


Assume each $\Delta(q, a)$ is fully conjunctive or fully disjunctive

$$\bigwedge_{q\in Q'} q$$
where $(q, a)$ is a $\land$ config
$$\bigvee_{q\in Q'} q$$
where $(q, a)$ is a $\lor$ config
for some nonempty $Q'\subseteq Q$.

>[!DEFINITION]
> Define the notation $post_w(q)$ for each $q\in Q, w\in\Sigma^*$ by induction:
> __Base__: $post_{\varepsilon}(q) := \lbrace q\rbrace\qquad post_a(q):= Q'$ if $\Delta(q, a) = \bigvee_{q\in Q'} q$ or $\Delta(q, a) = \bigwedge_{q\in Q'} q$
> __Induction:__ $post_{aw'}(q) := \bigcup_{q' \in post_a(q)} post_{w'}(q')$


[Arena](Arena.md):
$$\begin{align}
&V := \bigcup^{n}_{i=0} \lbrace (i, q) : q \in post_{u[1, i]}(q_0)\rbrace\\
&E := \lbrace ((i-1, q), (i, q')): i\in [1, n], q' \in post_{a_i}(q)\rbrace
\end{align}$$

We define $V_0$ to be all $(i, q)$ such that $(q, a_{i+1})$ is $\lor$ config
We define $V_1$ to be all $(i, q)$ such that $(q, a_{i+1})$ is $\land$ config

[Reachability Game](Reachability%20Game.md) $G$: 
The Arena and the Target set $T:= (\lbrace n\rbrace \times F) \cap V$

$u\in L(a)$ iff Player $0$ wins from $(0, q_0)$ in $G$

Membership of AFA is polynomial time solvable.


## Toolbox

### Membership
Given an AFA $A$ over $\Sigma$, a word $w \in \Sigma^*$.
We can decide in PTIME if $w\in L(A)$.
By interpreting of membership as a two player reachability game.

### Nonemptiness
Given an AFA $A$ over $\Sigma$ deciding if $L(A) \not = \emptyset$ is solvable in PSPACE.
For the proof we transform any AFA into an equivalent NFA.

### Intersection

Given AFA $A_1$ with $n_1$ states and $A_2$ with $n_2$ states, we can construct in PTIME an AFA $A$ with $n_1 + n_2 + 1$ states recognizing
$L(A_1) \cap L(A_2)$.
![](Alternating%20Finite%20Automata%202024-12-13%2013.19.08.excalidraw)

### Union
Given AFA $A_1$ with $n_1$ states and $A_2$ with $n_2$ states, we can construct in PTIME an AFA $A$ with $n_1 + n_2 + 1$ states recognizing
$L(A_1) \cup L(A_2)$.

![](Alternating%20Finite%20Automata%202024-12-13%2013.20.51.excalidraw)

### Complement
Given an AFA $A$ with $n$ states, we construct in PTIME an AFA $A'$ with $n$ states recognizing $\overline{L(A)}$.

### Universality
Given an AFA $A$ over $\Sigma$ deciding if $L(A) = \Sigma^*$ is PSPACE

### Inclusion
Given two AFA $A, A'$ over $\Sigma$. Deciding if $L(A) \subseteq L(A')$ is PSPACE.

