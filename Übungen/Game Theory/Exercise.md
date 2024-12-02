## Exercise 1
Given a NFA $\mathcal A$ over $\Sigma$, decide if $\mathcal L(\mathcal A) = \Sigma^*$ in PSPACE = NPSPACE.

$Q = \lbrace q_0\rbrace$ guess a symbol $w \in \Sigma$, $Q' = \bigcup_{q\in Q} \delta(q, w)$, if at any point one of the states is not accepting, then $L(A) \not = \Sigma^*$
After $2^{|Q|}$ iterations stop, everything after that is repeating.

## Exercise 2

Given DFAs $A_i$ over $\Sigma$ check if $\bigcap_i L(A_i) \not = \emptyset$ in PSPACE.

 $q \in Q_0 \dots Q_r$
 $q\in \lbrace q_0, \dots, q_n\rbrace$

for $\_ \in [Q_i : \prod\lbrace |Q| \in [1 \dots n\rbrace]$
	$\sigma \in \Sigma$ n.d.
	for $j \in [1, n]$
		if $q_i \not \in F_i$ then return False
	$q_i \in \sigma_i(q_i, \sigma)$
return True

## Exercise 3
Show that the above is PSPACE complete.

Idea:

Encode the Turring machine state as some sort of string:
$ID = 01q0100\#\#$
If the turring machine accepts the input, then there exists a sequence of IDs, where the first one is the initial tape and the last one the accepting state of the Turring machine.

Then there exists a word:
$$ID_0 \# \dots \# ID_n$$

For each we symbol we can create a DFA that checks if it behaves correctly, if the intersection of these is not empty then the Turring machine accepts.

Construction of the DFAs is not shown.


## Exercise 4

Quantified Boolean Formulas  $\lor, \land, \neg, \forall, \exists$
e.g.
$$\forall x \exists y x \lor y$$

is PSPACE.

If there are no quantifiers evaluate via assignment??.
If $\forall x_i \varphi$ then $\varphi[x_i = 1]$ and check $\varphi[x_i = 0]$ if both are true we accept.
If $\exists x_i \varphi$ then $\varphi[x_i = 1]$ and check $\varphi[x_i = 0]$ if one is true we accept.

We only store the current assignment

## Exercise 5

Checking if a directed Graph $G$ has a cycle, is NL-Complete.

$\in NL$
For every state, choose a path nondeterministically of length $n$, check if we are at the start.

NL-Hard:
So here he gave some explanation, which he didn't wrote down, neither did I fully understand what he talked about. As far as I understood he described some Turring machine equivalent of [Savitch's Theorem](https://en.wikipedia.org/wiki/Savitch's_theorem). 

---

> Remember winning sets from last exercise:
> A play is winning if there is a finite winning prefix
> This definition does not admit winning conditions about length of the games. This is correct and intended, it is enough for our purposes.


---


## Exercise 1
$$\begin{align}
u \vDash \langle \Sigma \rangle \varphi\\
n \ge 1, a_1 \in \Sigma, u[2, n] \vDash \varphi\\
u[2, n] \vDash \varphi
\end{align}$$

$$\begin{align}
&u\vDash F \varphi\\
\iff&u \vDash \top U \varphi\\
\iff&\exists j \in \lbrace 1, \dots, n\rbrace u[j, n] \vdash \varphi\\
&\forall i\lbrace 1, \dots, j-1\rbrace u[i, n] \vDash \top\\
\iff& \exists j\lbrace 1, \dots, n\rbrace u[j, n]\vDash \varphi
\end{align}$$

$$\begin{align}
&u \vDash G \varphi\\
\iff& u \vDash \neg F \neg \varphi\\
&u\not\vDash \neg F \neg \varphi\\
&\neg (\exists i \in \lbrace 1, \dots, n\rbrace u[i, n] \vDash \varphi)\\
\iff& \forall i \in \lbrace 1, \dots, n\rbrace\\
&u[i, n] \vDash \varphi
\end{align}$$

---

$$(\neg d U (1 \lor (0.5 \land X(\neg d U (0.5 \lor 1)))))\lor G \neg d$$
## Exercise 2

$$F\varphi \land F \psi \not \to F(\varphi \land \psi)$$

$$G(\varphi \lor \psi) \not \to G\varphi \lor G\psi$$

$$F(\varphi \to \psi) \not \to F\varphi \to F\psi$$

$$(G(\varphi) \to G(\psi)) \not \to G(\varphi \lor \psi)$$
$$XG\varphi \not \to GX \varphi$$
$$\varphi = \langle a\rangle \top \qquad u = aa$$
$$FX\varphi \not \to XF\varphi$$
$$\varphi = \neg \langle a\rangle \top \qquad u = a$$


## Exercise 3
$$\forall u, \varphi u \vDash G\varphi \to F\varphi$$
