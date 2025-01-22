$$\varphi = \top | \bot | \varphi \land \varphi | \neg | \langle \Sigma'\rangle\varphi | \varphi U \varphi$$

$a = \langle a \rangle \top = \langle \lbrace a \rbrace\rangle \top$
$X \varphi = \langle \Sigma \rangle \varphi$
$F\varphi = \top U \varphi$
$G \varphi = \neg F \neg\varphi$

---


Given $u = a_1 \dots a_m \in \Sigma^*$ define $u\vDash \varphi$ inductively:
$u \vDash \top$ $u\not\vDash \bot$
$u\vDash \varphi \land \psi \iff u\vDash \varphi and u\vDash\psi$
$u \vDash \neg \varphi \iff u\not\vDash \varphi$
$u \vDash \langle \Sigma'\rangle \varphi \iff m \ge 1, a_n \in \Sigma', u[2, n] \vDash \varphi$
$u\vDash \varphi U \psi \iff \exists j\in\lbrace 1, \dots, n\rbrace u[j, n]\vDash \varphi and \forall i\in\lbrace 1, \dots, j-1\rbrace, u[i, n] \vDash \varphi$

---

## LTL satisfiability

__Input:__ LTL formula $\varphi$
__Task:__ Decide if there is $u\in \Sigma^*$ such that $u\vDash\varphi$

> [!THEOREM]
> LTL sat is in PSPACE

We have already seen the upper bound.

> [!Theorem]
> LTL sat is PSPACE hard

We reduce from acceptance of poly-space bounded Turing Machines.


Deterministic Turing Machine(DTM) is $M = \langle Q, \Sigma, \Gamma, \delta, q_0, q_f\rangle$
- $Q$ is a finite set of states
- $\Sigma$ is the input alphabet
- $\Gamma \subseteq \Sigma$ is the tape alphabet
- Assume $\square \in \Gamma\setminus \Sigma$ as the blank symbol
- With more symbols in $\Gamma$ we may assume the TM does not move to the left if at the first cell
- $q_0, q_f$ are the initial and final state, respectively.
- $\delta : (Q \setminus \lbrace q_f\rbrace) \times \Gamma \to Q \times \Gamma\times\lbrace L, R\rbrace$ -> TM halts when in $q_f$

Say that the DTM is $p(n)$-space bounded for some polynomial $p$ if on some input word $w := a_1 \dots a_n \in \Sigma^*$ the TM uses at most $m := p(n)$ cells.
Then a configuration is element of $\Gamma^k Q \Gamma^{m - k}$ for some $0 \le k < m$.

The inital configuration $q_0 w \underbrace{\square \dots\square}_{m-n}$
Find configurations $i$ Elements of $\Gamma^k q_f \Gamma^{m-k}$.

__Reduction:__
Given a DTM $M$ and a word $w$ when $M$ is $p(n)$-space bounded,
construct in poly-time an LTL formula $\varphi$ such that $\varphi$ is sat iff $M$ accepts $w$.

We define $\varphi$ such that it is satisfied precisely by the accepting computation of $M$ on $w$, that is a sequence of configurations. 
$\#c_0\#c_1 \dots \# c_k$ where $c_0$ is the initial configuration and $c_k$ is the final configuration and the step $c_i \vdash c_{i+1}$ is allowed by $M$.

__Initial configuration:__
We construct an LTL formula that ensures that the computation starts with the initial configuration.
$$\varphi_{init} := \# \land X q_0 \land X^2 a_1 \land X^3 a_2 \land \dots \land X^{n+1} a_n \land X^{n+2} \square \land \dots \land X^{n+1 + (m-n)} \square$$

__Final configuration:__
Next we construct an LTL formula that checks if the last configuration is final.
$$\varphi_{final} := F q_f$$Suffices since we assume the computation stops when reaching $q_f$.

__One-Step__
First construct a formula that checks a specific transition from the beginning.
For all $q\in Q\setminus \lbrace q_f\rbrace$, $a\in \Gamma$ and $\delta(q,a) = (q', a', L)$
#exercise do for $\delta(q, a) = (q', a', R)$

$$\varphi_{q, a} := \bigvee_{k = 2}^{m} \left( \bigwedge_{i = 1}^{k-2} \bigvee_{b\in\Gamma} X^i b \land X^{m+2+i} b\right) \land X^k q \land X^{m+1 + k} q' \land X^{k+1} a \land X^{m+3 +k} a' \land \left( \bigvee_{b\in\Gamma} X^{k-1} v \land X^{m+2+k}\right) \land \left( \bigwedge^{m+1}_{i = k+2}\bigvee_{b\in \Gamma} X^i b X^{m+2+i} b \right)$$

$$\varphi_{cons} := G(\# \land \neg(X \neg F \#)) \to X^{m+2}  \# \land \left(\bigvee_{q\in Q\setminus \lbrace q_f\rbrace} \bigvee_{a \in \Gamma} \varphi_{q, a}\right)$$


$$\varphi := \varphi_{initial} \land \varphi_{final} \land \varphi_{cons}$$
The size of $\varphi$ is polynomial.
Our reduction only uses the operators $X, F$.
Thus, the fragment $LTL(X, F)$ is already PSPACE-hard.