
For a [complexity class](Complexity%20Classes.md) $C$ define $coC = \lbrace \overline L | L\in C\rbrace$.

$$coDTIME(t) = DTIME(t)$$
$$coDSPACE(s) = DSPACE(s)$$

---

__Claim:__ UNSAT and TAUTOLOGY are coNP-complete.

$UNSAT \in coNP$ (SAT is in NP)

UNSAT is coNP-[hard](Completness.md):
Take $L\in coNP$, by definition $\overline L\in NP$, so there exists a polytime reduction $f$ from $\overline L$ to SAT.

$$x\in L \iff \overline x\not\in \overline L \iff f(x) \in \overline{SAT}= UNSAT$$
$\varphi\mapsto \neg \varphi$ is a polytime reduction from UNSAT to TAUTOLOGY.


## Certificates

$L\subseteq \lbrace 0, 1\rbrace^*$ is in coNP iff there exists a polynomial $p(n)$ and $V\in P$ such that for all $x\in\lbrace 0, 1\rbrace^*$:
$$x\in L \iff \forall u\in \lbrace 0, 1\rbrace^{p(n)} : \langle x, u\rangle \in V$$
