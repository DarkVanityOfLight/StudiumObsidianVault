# Game Theory in Logic and Verification
> Kilian Lichtner

## Games

>[!DEFINITION] Arena
> An arena is a pair $A = \langle V, E\rangle$ where
> - $V = V_0 \cup V_1, V_0$ is 0-vertices, $V_1$ is 1-vertices, $V_0 \cap V_1 = \emptyset$
> - $E \subseteq V\times V$ is the edge relations

>[!DEFINITION] Successors
> The set of successors of $v\in V$ is defined by $suc(v) := \lbrace v' \in V | (v, v') \in E$

>[!DEFINITION] Plays
> A play is a finite non-empty sequence $\pi = v_0v_1v_2\dots v_n \in V^+$ such that $v_{i+1} \in suc(v_i)$ for all $i < n$.

> [!DEFINITION] Games
> A game is defined as a tuple $\mathcal G = \langle A, Win\rangle$ where
> - $A = \langle V, E\rangle$ is an arena 
> - $Win \subset V^*$ is the winning set.

>[!DEFINITION] Reachability Game
> A reachability game is a game $\mathcal G = \langle A, Win\rangle$ where there exists a target set $T\subseteq V$ such that 
> $$Win = \lbrace v_0\dots v_n\in V^+ | v_i \in T\text{ for some } 0 \le i\le n\rbrace$$
> We assume that a reachability game is given by the pair $\langle A, T\rangle$

>[!DEFINITION] Extended Play 
> An extended play is either a play $v_0\dots v_n$ such that $suc(v_n) = \emptyset$, i.e ending in a dead end, or an infinite sequence $v_0v_1\dots$ s.t. $v_0\dots v_k$ is a play for all $k\ge 0$

>[!DEFINITION] Won Extended Play
> An extended play is won for Player 0 if some finite prefix is a winning play for Player 0. Otherwise, the extended play is won for Player 1.

>[!DEFINITION] Strategy
> A strategy for Player $i$ is a partial function $\sigma_i: V^*V_i \to V$ that assigns every prefix of $v_0\dots v_k$ of a play with $v_k \in V_i$ and $suc(v_k) \not = \emptyset$ a vertex $v\in V$ such that $v\in suc(v_k)$ and is undefined otherwise.
> A play $v_0\dots v_n$ is conform with $\sigma_i$ if $v_{k+1} = \sigma(v_0\dots v_k)$ for all $0 \le k <n$ with $v_k \in V_i$
> An extended play is conform with $\sigma_i$ if every prefix play is conform with $\sigma_i$.

>[!DEFINITION] Winning Strategy
> A strategy $\sigma_i$ for Player $i$ is a winning from a vertex $v\in V$ if all extended plays that start in $v$ and are conform with $\sigma_i$ are won for Player $i$.

>[!DEFINITION] Memoryless Strategy
> A strategy $\sigma_i$ for Player $i$ is called memoryless if the value $\sigma_i(v_0\dots v_k)$ only depends on $v_k$, i.e. the last vertex

>[!DEFINITION] Winning Region
> Let $\mathcal G = \langle A, Win\rangle$. The winning region for Player $i$ is the set 
> $$W_i := \lbrace v\in V | \text{Player $i$ has a winning strategy from $v$} \rbrace$$

>[!DEFINITION] Determinacy
> A game $\mathcal G = \langle A, Win\rangle$ is determined if each vertex of the game graph belongs to either $W_0$ or $W_1$, i.e. $W_0 \cup W_1 = V$.

## Backwards Induction

Let $A = \langle V, E\rangle$ be an arena, $U\subseteq V$, and $i \in\lbrace 1, 0\rbrace$.
The controlled predecessor for Player $i$ on $U$ is
$$CPRE(U) := \lbrace v\in V_i | suc(v)  \cap U \not = \emptyset\rbrace \cup \lbrace v \in V_{1-i} | suc(v) \not = \emptyset \land suc(v) \subseteq U\rbrace$$
The $i$-attractor $Attr_i(U)$ is defined inductively by applying the controlled predecessor.

$Attr_i^0(U) := U$
$Attr^{n+1}_i(U) := Attr_i^n(U) \cup CPRE_i(Attr_i^n(U))$ and
$Attr_i(U) := \bigcup_{n\in\mathbb N} Attr_i^n(U)$

By monotonicity of the Attractor, there exists $k \le |V|$ such that $Attr_i^k(U) = Attr_i^{k+1}(U)$

## Regular Languages

>[!DEFINITION] NFA
>$A = (Q, \Sigma, \Delta, q_0, F)$ with:
> - $Q$ a finite set of states,
> - $\Sigma$ Input alphabet
> - $\Delta \subseteq Q \times \Sigma \times Q$ transition relation
> - $q_0$ the initial state
> - $F\subset Q$ the set of final states

>[!DEFINITION] DFA
$A = (Q, \Sigma, \delta, q_0, F)$ wobei:
> - $Q$ a finite set of states
> - $\Sigma$ a finite input alphabet
> - $\delta: Q \times \Sigma \to Q$ transition funktion
> - $q_0 \in Q$ initial state
> - $F\subseteq Q$ the set of final states


### Subset construction
Given an NFA $\mathcal A_N = \langle Q_N, \Sigma \delta_N, q_0, F_N\rangle$, we build a DFA $\mathcal A_D = \langle Q_D, \Sigma, \delta_D, \lbrace q_0\rbrace, F_D\rangle$
such that $\mathcal L(\mathcal A_N) = \mathcal L(\mathcal A_D)$ as follows:
- $Q_D := 2^{Q_N}$ the powerset
- $F_D := \lbrace S\in Q_D | S\cup F_N \not = \emptyset$, ie all sets that contain at least one accepting state from $F_N$
- For all $S \in Q_D$ and $a\in\Sigma$ $$\delta_D(S, a) := \bigcup_{s\in S} \delta_N(s, a)$$
Given an NFA $\mathcal A_N$, one can construct in PSPACE a DFA $\mathcal A_D$ such that $\mathcal L(\mathcal A_N) = \mathcal L(\mathcal A_D)$.

### Intersection
For DFAs $\mathcal A=\langle Q, \Sigma, \delta, q_0, F\rangle$ and $A' = \langle Q', \Sigma, \delta', q_0', F'\rangle$ with the same alphabet $\Sigma$ we define the product automaton $A \times A' = A_\times := \langle Q_X, \Sigma, \delta_\times, (q_0, q_0'), F_\times\rangle$ where
- $Q_\times := Q \times Q'$
- for all $(q, q') \in Q_\times$ and $a\in\Sigma$ $$\delta_\times((q, q'), a):= (\delta(q, a), \delta'(q', a))$$
- $F_N := F \times F'$

---

## Regular Games
>[!DEFINITION] Regular Games
> We say that a game $\mathcal G = \langle A, Win\rangle$ is regular if $Win$ is a regular language. We assume that $Win$ is given by an DFA/NFA $\mathcal G = \langle A, \mathcal A_{Win}\rangle$

>[!IMPORTANT] 
> Every reachability game is regular.
> Regular games are determined and can be solved in 
> - polynomial time if $Win$  is given by a DFA
> - exponential time if $Win$ is given by an NFA

- Determinize
- Game -> Automaton(Add state $q_0$, $\delta(q_0, v_0):= v_0; \forall (v, v')\in E \text{ let } \delta(v, v') := v'$)
- Product Automaton
- Automaton -> Game($V_0 := \lbrace (q, q_\text{Win}) \in Q \times Q_\text{Win} | q \in V_0 \cup \lbrace q_0\rbrace \rbrace$, forget about letters on transitions)



## LTL
(Linear Temporal Logic)
Temporal means can reason about program executions
Linear means the property is checked against one program execution

$$\varphi ::= \top | \bot | \varphi \land \varphi | \varphi \lor \varphi | \neg \varphi | \langle \Sigma'\rangle \varphi (\Sigma' \subseteq \Sigma) | \varphi U \varphi$$

- $\varphi \to \psi := \neg \varphi \lor \psi$
- $X\varphi := \langle \Sigma \rangle \varphi$
- $\langle a\rangle\varphi := \langle \lbrace a \rbrace\rangle \varphi$
- $a := \langle a\rangle \top$
- $F \varphi := \top U \varphi$
- $G\varphi := \neg F\neg\varphi$

### Semantics

Let $u = a_1 \dots a_n \in \Sigma^*$, define $u\vDash \varphi$ inductively:
1. $u\vDash \top$ $u \not\vDash \bot$
2. $u\vDash \varphi \land \psi \iff u\vDash \varphi \text{ and } u\vDash \psi$
3. $u\vDash \varphi \lor \psi \iff u\vDash \varphi \text{ or } u\vDash \psi$
4. $u\vDash \neg \varphi \iff u\not\vDash \varphi$
5. $u\vDash \langle \Sigma'\rangle \varphi \iff n \ge 1, a_1 \in \Sigma' \text{ and } u[2, n] \vDash \varphi$
6. $u\vDash \varphi U \psi \iff \text{ for some } j\in\lbrace 1, \dots, n\rbrace, u[j, n] \vDash \psi \text{ and for each } i\in\lbrace 1, \dots, j-1\rbrace, u[i, n]\vDash \varphi$


>[!IMPORTANT] Remember
> LTL formulas and thus $\varphi$ and $\psi$ are formulas over the entire (sub) word

$L(\varphi \land \psi) = L(\varphi) \cap L(\psi)$
$L(\varphi \lor \psi) = L(\varphi) \cup L(\psi)$
$L(\neg \varphi) = \Sigma^*\setminus L(\varphi)$
$L(\varphi U \psi) = L(\psi \lor (\varphi \land X(\varphi U\psi)))$

### Past Operators
$w, i \vDash Y \varphi \iff  i>1 \text{ and } w, i-1 \vDash \varphi$
$w, i \vDash \varphi S \psi \iff \exists j\in [i, n]: w, j \vDash \psi \text{ and } \forall k\in(j, i]: w, k\vDash \varphi$

## Alternating Finite Automata

>[!DEFINITION] Alternating Finite Automata
> An AFA $A$ over the Alphabet $\Sigma$ is a tuple $$A = \langle Q, \Sigma, \Delta, q_0, F\rangle$$
> - where $Q$ is a finite set of states
> - $q_0\in Q$ is the initial state 
> - $F\subseteq Q$ is the set of final states
> - $\Delta: Q\times \Sigma \to B^+(Q)$ is the transition function, where $B^+(Q)$ is the set of all positive Boolean formulas(i.e. no negation is allowed, only $\land, \lor, \top, \bot$ with variables $Q$

>[!IMPORTANT] AFA (strictly) generalize NFA

### Acceptance
Acceptance of an input word $w = a_1 \dots a_n$ is done by defining a run  as a sequence of sets of states $Q_0, \dots, Q_n$ such that 
1. $Q_0 = \lbrace q_0\rbrace$ and $Q_i \subseteq Q$ for each $i = 1, \dots, n$
2. For each $i = 1, \dots, n$ $Q_i$ is a satisfying assignment of $\bigwedge_{q\in Q_{i-1}}\Delta(q, a_i)$

The run is accepting if $Q_n \subseteq F$
A word $w$ is accepted if there exists an accepting run on $w$.
The language $L(A)$ of $A$ contains precisely all words accepted by $A$

### Membership
__Input:__ An AFA $A$ over $\Sigma$, a word $w\in \Sigma^*$
__Task:__ Decide if $w\in L(A)$

Membership for AFA is decidable in PTIME.

Proof by turning the AFA into a two player game. Player 0 controlls $\lor$ Player 1 controlls $\land$.

### Nonemptiness
__Input:__ An AFA over $\Sigma$
__Task:__ Decide if $L(A) \not = \emptyset$

>[!IMPORTANT] Non emptiness of AFA is solvable in PSPACE

>[!IMPORTANT] Any AFA can be transformed into an equivalent NFA in PSPACE


#### AFA to NFA
Given an AFA $A = \langle Q, \Sigma, \Delta, q_0, F\rangle$
Construct the NFA $A' = \langle 2^Q, \Sigma, \delta', \lbrace q_0\rbrace, 2^F$
$$\delta'(S, a) := \lbrace T: T\text{ satisfies }\bigwedge_{q\in S} \Delta(q, a) \rbrace$$
By convention the empty conjunction is equivalent to $\top$, i.e.
$\delta'(\emptyset, a) = 2^Q$

>[!IMPORTANT] Intuition
> $A'$ guesses satisfying assignments and simulates $A$ on all guessed states.

### Intersections
>[!IMPORTANT] PTIME


Introduce a new state conjunctive state $q_0$, with edges to both initial states of the intersecting automatons. 

### Union
>[!IMPORTANT] PTIME

Introduce a new state disjunctive state $q_0$, with edges to both initial states of the intersecting automatons. 

### Complement
>[!IMPORTANT] PTIME

Introduce the dual of a positive formula $\overline \varphi$(negate everything)


### Universality
__Input:__ An AFA over $\Sigma$
__Task:__ Decide if $L(A) = \Sigma^*$

>[!IMPORTANT] PSPACE

1. Negate the automaton
2. Check for emptiness

### Inclusion
__Input:__ Two AFA $A$ and $A'$ over $\Sigma$
__Task:__ Decide if $L(A) \subseteq L(A')$

1. Complement $A'$
2. Do the intersection $A \cap \overline A'$
3. Check for non emptiness, if it s empty $L(A) \subseteq L(A')$

## Vardi Wolpers

>[!IMPORTANT] Given an LTL formular $\varphi$, we can construct in PTIME a linear size $O(|\varphi|)$ AFA with $L(\varphi) = L(A)$.
> Thus LTL satisfiability and model checking are both solvable in PSPACE

### Subformulas 
The set $sub(\varphi)$ of subformulas $\varphi$ is defined inductively:
- $sub(\top) := \lbrace \top\rbrace$ $sub(\bot) := \lbrace \bot \rbrace$
- $sub(\varphi \sim \psi)(\sim \in\lbrace \land, \lor\rbrace := \lbrace\varphi \land \psi\rbrace \cup sub(\varphi) \cup sub(\psi)$
- $sub(\neg \varphi) := \lbrace \neg \varphi\rbrace \cup sub(\varphi)$
- $sub(\langle \Sigma'\rangle\varphi) := \lbrace \langle \Sigma'\rangle\varphi\rbrace \cup sub(\varphi)$
- $sub(\varphi U \psi) := \lbrace \varphi U \psi\rbrace\cup sub(\varphi) \cup sub(\psi)$
The set $sub^\pm(\varphi)$ of a positive or negative subformula of $\varphi$ is defined inductively:
- $sub^\pm(\top) = sub^{\pm}(\bot) := \lbrace \top, \bot\rbrace$
- $sub^\pm(\varphi \sim \psi)(\sim\in\lbrace \land,\lor\rbrace) := \lbrace \varphi \sim \psi, \neg(\varphi \land \psi)\rbrace \cup sub^{\pm}(\varphi) \cup sub^\pm(\psi)$
- $sub^\pm(\neg \varphi) := sub^\pm(\varphi)$
- $sub^\pm(\langle \Sigma'\rangle \varphi) := \lbrace \langle\Sigma'\rangle\varphi, \neg(\langle\Sigma'\rangle\varphi)\rbrace \cup sub^\pm(\varphi)$
- $sub^\pm(\varphi U \psi) := \lbrace \varphi U \psi, \neg(\varphi U \psi)\rbrace \cup sub^\pm(\varphi) \cup sub^{\pm}(\psi)$
### Construction
From $\varphi$ we construct AFA $A = \langle Q, \Sigma, \Delta, q_0, F\rangle$ as follows:
- $Q := \lbrace p_\psi : \psi \in sub^\pm(\varphi)$
- $q_0 := p_\varphi$

#### Final states
We define $F$ by induction:

__Base Case__
- $p_\top \in F$
- $p_\bot \not \in F$

__Inductive Step__
Let $\chi\in sub(\varphi)$ such that we already defined containment in $F$ for all $p_\psi$ with $\psi \in sub^\pm(\chi) \setminus\lbrace \chi, \neg \chi\rbrace$.
- If $\chi = \psi_1 \land \psi_2$, then $p_\chi \in F$ iff $p_{\psi_1} \in F$ and $p_{\psi_2} \in F$
- If $\chi = \psi_1 \lor \psi_2$, then $p_\chi \in F$ iff $p_{\psi_1} \in F$ or $p_{\psi_2} \in F$
- If $\chi = \neg \psi$, then $p_{\chi}\in F$ iff $p_{\psi} \not \in F$
- If $\chi = \langle\Sigma'\rangle\psi$ or $\chi = \psi_1 U \psi_2$, then $p_\chi \not\in F$
If $\chi$ is as in $1, 2, 4$ then $p_{\neg \chi} \in F$ iff $p_\chi \not \in F$


#### Transition Function
We define $\Delta(p_\psi, a)$ by induction on $\psi$
__Base Case__
$\Delta(p_\top, a) := \top$
$\Delta(p_\bot, a) := \bot$

Since our state set contains positive and negative subformulas we use a modified notion of "dual" of a positive Boolean formula:

- $\overline\top := \bot$, $\overline \bot := \top$
- $\overline p_\psi := p_{\neg\psi}$
- $\overline{\alpha \land \beta} := \overline \alpha \lor \overline \beta$
- $\overline{\alpha \lor \beta} := \overline a \land \overline \beta$
for $\alpha, \beta \in B^+(Q)$.

__Inductive Step__
- $\Delta(p_{\psi_1 \land \psi_2}, a) := \Delta(p_{\psi_1}, a) \land \Delta(p_{\psi_2}, a)$
- $\Delta(p_{\psi_1 \lor \psi_2}, a) := \Delta(p_{\psi_1}, a) \lor \Delta(p_{\psi_2}, a)$
- $\Delta(p_{\neg \psi}, a) := \overline{\Delta(p_\psi, a)}$
- $\Delta(p_{\langle \Sigma'\rangle \psi}, a) := \begin{cases}p_\psi, \quad a\in \Sigma' \\ \bot\end{cases}$
- $\Delta(p_{\psi_1 U \psi_2}) := \Delta(p_{\psi_2}, a) \lor (\Delta(p_{\psi_1}, a) \land p_{\psi_1 U \psi 2})$
- $\Delta(p_{\neg(\psi_1 U \psi_2)}) := \overline{\Delta(p_{\psi_2}, a)} \land (\overline{\Delta(p_{\psi_1}, a)} \lor (p_{\neg (\psi_1 U \psi 2)}))$


>[!IMPORTANT] 
> Remember $a := \langle a\rangle \top$
> So $\Delta(p_a, a) = p_\top$


## LTL Games

>[!DEFINITION] LTL Game
> A game $G = \langle A, Win\rangle$ with $A = \langle V, E\rangle$ is called LTL game if there is an LTL formula $\varphi$ over the alphabet $\Sigma$ and labeling function $f: V \to \Sigma$ such that $$Win = \lbrace w\in V^* : f(w) \in L(\varphi)\rbrace$$
> We assume that $Win$ is given by $\varphi$ and $f$ i.e. $G= \langle A, \varphi, f\rangle$


>[!IMPORTANT] Every LTL game $G = \langle A, Win\rangle$ is regular. Moreover, if $G = \langle A, \varphi, f\rangle$, then one can compute in polynomial space a regular game $G' = \langle A, A_{Win}, f\rangle$ such that $L(A_{Win}) = L(\varphi)$

1. Use VW-Theorem to turn $\varphi$ into an AFA $A_{\varphi}$ with $L(A_\varphi) = L(\varphi)$ (PTIME)
2. Turn the AFA $A_\varphi$ into an NFA $A_{Win}$ with $L(A_{Win}) = L(A_\varphi)$ (PSPACE)
3. Solve the Regular game (EXPTIME)

>[!IMPORTANT] LTL games are determined and can be solved in double exponential time.

## Past Operators

$w, i\vDash Y \varphi \iff i > 1,\text{ and } w, i-1 \vDash \varphi$
$w, i \vDash \varphi S \psi \iff \exists j\in[1, i] : w, j\vDash \psi \text{ and } \forall k\in(j, i]: w, k\vDash \varphi$

## Kamp's Theorem

> LTL = FO over $\Sigma^+$. That is:
> 1. for every LTL formular $\varphi$, there exists an FO formula $\psi(x)$ such that for all words $w = a_1\dots a_n\in\Sigma^+, i\in [1, n]$
> 2. for every FO formula $\psi(x)$, there exists an LTL formula $\varphi$ such that for all words $w = a_1\dots a_n\in \Sigma^+, i\in[1, n] \mathfrak A_w \vDash \psi(i) \iff w, i\vDash\varphi$

>[!NOTATION]
> Write $w\vDash \varphi$ if $w, 1\vDash \varphi$. Write $L_\varphi = \lbrace w\in\Sigma^+ : w\vDash \varphi\rbrace$

### LTL+past -> FO

Introduce Relation symbols $U_a/1$ for all $a\in\Sigma$ $U_a(i) \iff w[i] = a$


__Base Case:__
$\varphi := a \implies \psi := U_a(x)$


__Induction:__

- $\varphi := X \varphi'$ Let $\psi'$ be the formula equivalent to $\varphi'$. Define $\psi(x) := \exists y(x < y\land \psi'(y) \land \neg\exists z(x < z<y))$. Then $w, i \vDash \varphi \iff \mathfrak A_w \vDash \psi(i)$

- $\varphi := \varphi_1 U \varphi_2$. Let $\psi_i$ be the formula equivalent to $\varphi_i$. Define $\psi(x) := \exists y(x \le y \land \psi_2(y) \land \forall z(x \le z < y \to \psi_1(z)))$. Then $w, i\vDash \varphi \iff \mathfrak A_w \vDash \psi(i)$.

The cases for $Y$ and $S$ are identical.


### FO -> LTL

A LTL+past formula is said to be a future formula if it does not have operators $Y$ and $S$.

An LTL+past formula is said to be a past formula if it does not have operators $X$ and $U$.

>[!LEMMA] Seperation Property
> Every LTL+past formula is a boolean combination of future formulas and past formulas.

### Base Case
$\psi(x) := W \implies \varphi := W$ for $W \in \lbrace\top,\bot\rbrace$
$\psi(x) := U_a(x) \implies \varphi := a$
$\psi := x = x \implies \varphi := \top$
$\psi(x):= x < x \implies \varphi := \bot$

### Inductive Case
$\exists y\theta(y) \implies \varphi := (\top U \varphi_\theta) \lor (\top S \varphi_\theta)$

## Structures

A relational vocabulary 
$$\sigma = \lbrace R_1, \dots , R_n, c_1, \dots c_n\rbrace$$
where 
1. $R_i$ is an $r_i$ ary relation symbol 
2. $c_i$ is a constant symbol

A $\sigma$ structure $\mathfrak A$ is a tuple 
$$\mathfrak A := \langle A; \lbrace R_i^{\mathfrak A}\rbrace^n_{i=1}, \lbrace c_i^\mathfrak A\rbrace^m_{i = 1}$$
where $A$ is the universe (a set of elements) $R_i^\mathfrak A \subseteq A^{r_i}$ and $c_i^\mathfrak A \in A$ for each $i$.

$STRUCT[\sigma]$ denotes the set of all structures over $\sigma$
$A, B, \dots$ are used for universes of structures $\mathfrak A, \mathfrak B$
We sometimes omit superscripts from $R^\mathfrak A_i, c^\mathfrak A_i$

## Alternating Turing Machines

An alternating turing machine is a nondeterministic
Turing machine whose state set $Q$ is divided into four classes $Q_\exists$, $Q_\forall$ , $Q_{acc}$ and $Q_{rej}$


$ALOGSPACE = ASPACE(O(\log n))$
$APTIME = \bigcup_{d\in\mathbb N} ATIME(n^d)$
$ASPACE = \bigcup_{d\in\mathbb N} ASPACE(n^d)$


### Class Equivalencies
$PTIME = ALOGSPACE$
$PSPACE = APTIME$
$EXPTIME = APSPACE$
$EXPSPACE = AEXPTIME$

## Homomorphism

Given two $\sigma$-structures $\mathfrak A,\mathfrak B$, a homomorphism form $\mathfrak A$ to $\mathfrak B$ is a mapping $h: A \to B$ such that for all constant symbol $c\in \sigma$ and relation symbol $R \in \sigma$
1. $(a_1, \dots a_r) \in R^\mathfrak A \implies (h(a_1), \dots, h(a_r)) \in R^\mathfrak B$ 
2. $h(c^\mathfrak A) = c^\mathfrak B$

A homomorphism between $\sigma$-structures $\mathfrak{A}$ and $\mathfrak{B}$ is a function $h: A \to B$ that respects the interpretation of relation symbols and constant symbols in $\sigma$, ensuring that $\mathfrak{A}$ can be embedded (structurally) into $\mathfrak{B}$

### Substructures
Let $\mathfrak A, \mathfrak B$ be $\sigma$ structures. We say that $\mathfrak A$ is a substructure of $\mathfrak B$ if there is a homomorphism from $\mathfrak A$ to $\mathfrak B$.

Let $B' \subseteq B$ include all constants in $\mathfrak B$. The substructure of $\mathfrak B$ generated by $B$ is the $\sigma$ structure $\mathfrak B'$ whose universe is $B'$, $c^{\mathfrak B'} := c^\mathfrak B$ for each constant symbol $c$ and $R^{\mathfrak B'} := R^\mathfrak B \cap (B')^r$ for each $r$ ary relation symbol $R$.

## Isomorphism

An isomorphism is a bijective homomorphism whose inverse is also a homomorphism.

Two $\sigma$-structures $\mathfrak A$, $\mathfrak B$ are said to be isomorphic, written $\mathfrak A \cong \mathfrak B$, if there is an isomorphims from $\mathfrak A$ to $\mathfrak B$.

Intuitively, $\mathfrak A\cong \mathfrak B$ means that $\mathfrak A$, $\mathfrak B$ look the same up to renaming of elements in the universe.

### Partial Isomorphism
Fix two $\sigma$-structures $\mathfrak A, \mathfrak B$ with constant symbols $c_1, \dots, c_m$.
Let $\overline a = (a_1, \dots, a_n) \in A^n, \overline b = (b_1, \dots, b_n) \in B^n$. Then, $((\overline a, c^\mathfrak A), (\overline b, \overline c^{\mathfrak B}))$ defines a partial isomorphism between $\mathfrak A, \mathfrak B$, if the mapping defined as $a_i \mapsto b_i$ and $c_i^{\mathfrak A} \mapsto c_i^{\mathfrak B}$ is an isomorphism between the substructures of $\mathfrak A$ and $\mathfrak B$ generated by $\overline a\cup \overline c^{\mathfrak A}$ and $\overline b \cup \overline c^{\mathfrak B}$ respectively

## Property
Fixing a base class $\mathcal C \subseteq STRUCT[\sigma]$ of structures.
A $\sigma$ property is a subset of $\mathcal C$. 

## Ehrenfeucht-Fraisse Games

Given 2 $\sigma$ structures: $\mathfrak A, \mathfrak B$ with constant symbols $\overline c = (c_1, \dots c_m)$ 

>[!NOTATION] 
> If $\mathfrak S = \mathfrak A$(resp. $\mathfrak S = \mathfrak B$), then $\overline{\mathfrak S} = \mathfrak B$

There are two players Spoiler and Duplicator. Spoiler and Duplicator move in turns for $n\in \mathbb N$ rounds.

At round $i$:
1. Spoiler picks a structure $\mathfrak S$ and element $s_i$ in it
2. Duplicator picks an element $s_i'$ in $\overline{\mathfrak S}$

After $n$ rounds: two tuples are $\overline a \in A$ and $\overline b \in  B$ are generated. Duplicator wins iff $((\overline a, \overline c^\mathfrak A), (\overline b, \overline c^\mathfrak B))$ defines a partial isomorphism between $\mathfrak A$ and $\mathfrak B$

>[!IMPORTANT] Write $\mathfrak A \equiv_n \mathfrak B$ if Duplicator has a winning strategy on the $n$-round EF games on $\mathfrak A, \mathfrak B$

>[!IMPORTANT] A property $\mathcal P\subseteq \mathcal C$ is not expressible iff for every $k\in\mathbb N$, there exit $\mathfrak A_k \in \mathcal P$, $\mathfrak B_k \in \mathcal C\setminus \mathcal P$ such that $\mathfrak A_k \equiv_k \mathfrak B_k$
>


Let $FO[k]$ denote all formulas of Quantifier Rank at most $k$ 
$\mathfrak A$ and $\mathfrak B$ agree on $FO[k]$ sentences IFF $\mathfrak A \equiv_k \mathfrak B$

#### Back and Forth Relation
We define the relation $\simeq_k$ over structures by induction.
$\mathfrak A \simeq_0 \mathfrak B$ iff $\mathfrak A \equiv_0\mathfrak B$, i.e. they satisfy the same atomic sentences.
$\mathfrak A \simeq_k \mathfrak B$ iff the following conditions hold:
For every $a\in A$, there is $b\in B$ s.t $(\mathfrak A, a) \equiv_{k-1} (\mathfrak B, b)$
For every $b\in B$, there is $a\in A$ s.t $(\mathfrak A, a) \equiv_{k-1} (\mathfrak B, b)$


## Rank k types
Let $\sigma$ be a relational vocabulary, $\mathfrak A \in STRUCT[\sigma]$, and $\overline a\in A^m$ . The rank-k m-type of $\overline a$ over $\mathfrak A$ is the set 
$$tp_k(\mathfrak A, \overline a) := \lbrace \varphi(\overline x) \in FO[k] : \mathfrak A \vDash \varphi(\overline a)\rbrace$$
A rank-k m-type is any set of formulas of the form $tp_k(\mathfrak A, \overline a)$ with $|\overline a| = m$. When $m$ is clear, we simply say rank-k type.

## Hanf Locality

### Proof Sketch
Assume a Query $Q$(or property) is Hanf Local. Then it has a Hanf Locality rank $hlr(Q) = d$.

Choose two structures with respect to $d$ such that structure $A$ such that $Q(\mathfrak A) = \top$ and $Q(\mathfrak B) = \bot$.

Show that their neighborhoods look the up to $d$.

Then $(\mathfrak A, a) \rightleftarrows_d (\mathfrak B, b)$ and thus $\overrightarrow a \in Q(\mathfrak A) \iff \overrightarrow b \in Q(\mathfrak B)$ which is a contradiction