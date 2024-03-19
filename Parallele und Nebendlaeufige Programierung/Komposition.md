In einem System gibt es in der Regel mehrere [Prozesse](Prozess.md). Es kann sein, dass diese Prozesse Ressourcen(Speicher, CPU, GPU) teilen oder miteinander interagieren. Die individuellen Prozesse werden in einem übergeordneten Prozess kombiniert

## Sequentielle Komposition

Für zwei Prozesse $p_1 = (E_1, \leq_1, \alpha_1), p_2 = (E_2, \leq_2, \alpha_2)$ gilt, dass $p_2$ erst beginnen darf wenn $p_1$ vorbei ist.

Hierfür muss gelten $E_1\cap E_2 = \emptyset$

Sequentiell Komposition $p_s = (E_s, \leq_s, \alpha_s)$ mit 
- $E_s = E_1 \cup E_2$
- $\leq_s = \leq_1 \cup \leq_2 \cup \lbrace (e_1, e_2): e_1 \in E_1, e_2\in E_2\rbrace$
- $\alpha_s(e) = \begin{cases}\alpha_1(e), e\in E_1\\ \alpha_2(e), e\in E_2\end{cases}$

## Nebenläufige Komposition

Die Prozesse $p_1 = (E_1, \leq_1, \alpha_1), p_2 = (E_2, \leq_2, \alpha_2)$ sind voneinander unabhängig.

Es werden keine kausalen Abhängigkeiten hinzugefügt.

Bedingungen: $E_1 \cap E_2 = \emptyset\land \rbrace \alpha_1(e) | e\in E_1\rbrace \cap \lbrace \alpha_2(e) | e\in E_2\rbrace = \emptyset$ 

__Nebenläufige Komposition__ $p_c = (E_c, \leq_c, \alpha_c)$ mit:
- $E_c = E_1 \cup E_2$
- $\leq_c = \leq_1 \cup \leq_2$
- $\alpha_c(e) = \begin{cases}\alpha_1(e), e\in E_1\\ \alpha_2(e), e\in E_2\end{cases}$

## Parallele Komposition

Jeder der Prozesse $p_1 = (E_1, \leq_1, \alpha_1), p_2 = (E_2,\leq_2, \alpha_2)$ beschreibt einen Teilaspekt des Systems; es kann kausale Abhängigkeiten zwischen den Teilen geben.


Seien $p_1 = (E_1, \leq_1, \alpha_1), p_2 = (E_2,\leq_2, \alpha_2)$ Prozesse mit gemeinsamer Aktionsmenge $A$, und $S\subseteq A$
- $\forall e \in E_1 \cap E_2. \alpha_1(e) = \alpha_2(e)$
- $\forall e\in E_1: (\alpha_1(e)\in S\implies e\in E_2)\land \forall e\in E_2:(\alpha_2(e)\in S\implies e\in E_1)$
- $\forall e\in E_1:(\alpha_1(e) \not\in S \implies e\not\in E_2)\land \forall e\in E_2:(\alpha_2(e)\not\in S \implies e\not\in E_1)$

__Parallele Komposition__ $p_p = (E_p,\leq_p,\alpha_p)$ mit gemeinsamen [Aktionen](Aktion.md) aus $S$:
- $E_p = E_1\cup E_2$
- $\leq_p = (\leq_1 \cup \leq_2)^* \land \leq_p \text{ ist antisymmetrisch}$
- $\alpha_p(e) = \begin{cases}\alpha_1(e), e\in E_1\\ \alpha_2(e), e\in E_2\end{cases}$


