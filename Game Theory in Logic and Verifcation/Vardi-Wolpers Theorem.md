Given an [LTL](Linear%20Temporal%20Logic.md) formula $\varphi$, we can construct in PTIME a linear size [AFA](Alternating%20Finite%20Automata.md) with $L(\varphi) =  L(A)$.



## Subformulas
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

## Construction

From $\varphi$ we construct AFA $A = \langle Q, \Sigma, \Delta, q_0, F\rangle$ as follows:
- $Q := \lbrace p_\psi : \psi \in sub^\pm(\varphi)$
- $q_0 := p_\varphi$

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
- $\Delta(p_{\psi_1 U \psi_2}) := \Delta(p_{\psi_2, a}) \lor (\Delta(p_{\psi_1}, a) \land p_{\psi_1 U \psi 2})$

