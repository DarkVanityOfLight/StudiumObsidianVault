
> Temporal means "can reason about program executions"

> Linear means "property is checked against one program execution"


## Syntax

 An LTL formula is of the following form:
 $$\varphi ::=\top | \bot | \varphi \land \varphi | \varphi \lor \varphi| \neg \varphi | \langle \Sigma'\rangle \varphi (\Sigma' \subseteq \Sigma) | \varphi U \varphi$$
 where $\Sigma$ is a finite set of "atomic propositions". $U$ is read "Until"

We use the following shorthands

- $\varphi \to \psi := \neg \varphi \lor \psi$
- $X\varphi := \langle\Sigma\rangle\varphi$ X is read as neXt
- $\langle a \rangle\varphi := \langle \lbrace a\rbrace\rangle \varphi$
- $a := \langle a\rangle \top$ for $a\in \Sigma$
- $F \varphi := \top U \varphi$
- $G \varphi := \neg F \neg \varphi$
- $F$ is read "in the Future"
- $G$ is read "Globally"


## Semantiks

The semantics of LTL is interpreted over a single program execution.
Given $u = a_1 \dots a_n \in \Sigma^*$, define $u\vDash \varphi$ inductively:

1. $u\vDash \top$ $u\not\vDash \bot$
2. $u \vDash \varphi \land \psi$ iff $u\vDash \varphi$ and $u\vDash \psi$
3. $u\vDash \varphi \lor \psi$ iff $u\vDash \varphi$ or $u\vDash \psi$
4. $u\vDash \neg \varphi$ iff $u\not \vDash \varphi$
5. $u\vDash \langle \Sigma'\rangle \varphi$ iff $n\ge 1, a_1\in\Sigma'$ and $u[2, n]\vDash \varphi$
6. $u \vDash \varphi U \psi$ iff for some $j\in \lbrace 1, \dots, n\rbrace$, $u[j, n] \vDash \psi$ and for each $i\in\lbrace 1, \dots, j-1\rbrace, u[i, n] \vDash \varphi$

>[!DEFINITION]
>$L(\varphi) := \lbrace u\in\Sigma^* : u\vDash \varphi\rbrace$


---

- $L(\varphi \land \psi) = L(\varphi) \cap L(\psi)$
- $L(\varphi \lor \psi) = L(\varphi) \cup L(\psi)$
- $L(\neg \varphi) = \Sigma^*\setminus L(\varphi)$
- $L(\varphi U \psi) = L(\psi \lor (\varphi \land X(\varphi U \psi)))$



## Satisfiability

Decide if there exists $u\in\Sigma^*$ such that $u\vDash \varphi$

## Model Checking

Decide if for each $u\in L(A)$ we have $u\vDash \varphi$

Both problems can be solved in PSPACE using [Alternating Finite Automata](Alternating%20Finite%20Automata.md) 
