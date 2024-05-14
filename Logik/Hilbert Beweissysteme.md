
Das Hilbert Beweissystem basiert auf nur wenigen Axiomen und mit nur einer Interferenzregel([Modus Ponens](Modus%20Ponens.md)). Wir betrachten die Version die man $\mathfrak F_0$ nennt. In diesem System haben alle Formeln nur die Operatoren $\lbrace \to, \neg\rbrace$ und keine Konstanten $\lbrace \top, \bot \rbrace$.

Wir haben drei __Axiomenmuster__

- $P \to (Q\to P)$
- $(P \to ( Q\to R)) \to ((P\to Q) \to (P\to R))$
- $(\neg P \to \neg Q)\to (Q\to P)$

Die einzige Inferenzregel ist [Modus Ponens](Modus%20Ponens.md).

>[!WARNING]
>$P, Q, R$ sind Formeln die nur die Operatoren $\lbrace \to, \neg\rbrace$ enthalten dürfen.

## Beweisbar

Eine Formel $P$ ist __herleitbar/beweisbar__ aus der Menge $\Sigma$ von Formeln (schreibe: $\Sigma \vdash P$) falls es eine Sequenz von Formeln gibt $\varphi_1, \dots, \varphi_n, P$ wobei jede Formel $\varphi_i$ entweder:
- Ein Axiom oder eine Formel aus $\Sigma$ ist, oder
- kann von $\varphi_j, \varphi_k$ mit [Modus Ponens](Modus%20Ponens.md) aus einer vorherigen Formeln hergeleitet werden, also $j, k <i$

>[!DEFINITION] 
>Sätze sind Formeln hergeleitet aus $\Sigma = \emptyset$

Wir schreiben $\vdash P$ falls $\emptyset \vdash P$

## Hilfreiche Resultate

>[!NOTE] Double Negation
>$$A \vdash \neg\neg A$$

>[!NOTE] Contrapositive 1
>$$\neg \varphi \to \neg \psi \vdash \psi \to \varphi$$

>[!NOTE] Transitivity
>$$\Sigma \vdash A \to B, \Sigma \vdash B \to C \implies \Sigma \vdash A \to C$$

>[!NOTE] Contrapositive 2
>$$\varphi \to \psi \vdash \neg \psi \to \neg \varphi$$

>[!NOTE] Proof by Contradiction 
>$$\varphi, \neg \varphi \vdash \psi$$

>[!NOTE] Proof by Cases
>$$\Sigma, \varphi \vdash \psi \text{ und } \Sigma, \neg \varphi \vdash \psi \text{ impliziert } \Sigma \vdash \psi$$


## Korrektheit

$$\Sigma \vdash \varphi \text{ impliziert } \Sigma\vDash\varphi$$

Wir führen den Beweis durch [Strukturelle Induktion](Strukturelle%20Induktion.md) über die Länge des Beweises für $\Sigma \vdash \varphi$

__Länge = 1__: Dann ist $\varphi$ entweder ein Axiom, oder $\varphi \in \Sigma$. Also gilt $\Sigma \vDash \varphi$.

__Länge > 1__: Dann ist $\varphi$ mithilfe von $MP(\alpha, \beta)$ bewiesen, wobei $\alpha, \beta$ beide kürzere Beweise haben. Nach der Induktionsvoraussetzung haben wir $\Sigma \vDash \alpha$ und $\Sigma \vDash \beta$. Da $\beta$ gleich $\alpha \to \varphi$ ist, folgt $\Sigma \vDash \varphi$

## Vollständigkeit

$$\Sigma \vDash \varphi \text{ impliziert } \Sigma \vdash \varphi$$

Wir werden dies nur für den Fall $\Sigma = \emptyset$ zeigen. Der allgemeine Fall folgt aus dem [Kompaktheitssatz der Aussagenlogik](Kompaktheitssatz%20der%20Aussagenlogik.md)

>[!NOTE] Lemma
>Falls $\varphi$ Variablen $x_1, \dots, x_n$ hat und $l_i$ ein $x_i$-[Literal](Literal.md) ist, dann gilt
>$$l_1, \dots, l_n \vdash \varphi \text{ oder } l_1, \dots, l_n \vdash \neg \varphi$$

Daraus würde die Vollständigkeit direkt folgen. Betrachten wir eine Tautologie $\varphi$. Dann:
$$\begin{align}
&l_1, \dots, l_n \vdash \varphi \text{ und } l_1, \dots,\overline l_n \vdash \varphi\\
\implies& l_1, \dots, l_{n-1} \vdash \varphi (\text{Fallunterscheidung})\\
\implies&\dots\\
\implies& \vdash \varphi
\end{align}$$

### Beweisskizze des Lemmas

Sei $I$ eine [Belegung](Belegung.md), die jedes Literal $l_i$ wahr macht. Unser Beweis ist mit [Strukturelle Induktion](Strukturelle%20Induktion.md) über $\varphi$.

Der Fall $\varphi = x_i$ ist Trivial, da $l_i = x_i$ oder $l_i = \neg x_i$ gilt.

Fall $\varphi = \psi_1 \to \psi_2$: Ist $I \not\vDash \varphi$, dann gilt $I\vDash \psi_1$ und $I\vDash \neg \psi_2$. Wenden wir die Induktionsvoraussetzung auf $\varphi_1$ und $\varphi_2$ an, erhalten wir wegen der Korrektheit $l_1, \dots, l_n \vdash \psi_1$  und $l_1, \dots, l_n \vdash \neg \psi_2$. Aus $\psi_1, \neg \psi_2 \vdash \neg(\psi_1 \to \psi_2)$ folgt $l_1, \dots, l_n \vdash \neg \varphi$

Fall $\varphi = \neg \psi$ Von der Induktionsvoraussetzung angewendet auf $\psi$ erhalten wir entweder $l_1, \dots, l_n \vdash \psi$ oder $l_1, \dots, l_n \vdash \neg \psi$. Der erste Fall ist trivial. Für den zweiten Fall liefert $\vdash \psi \to \neg\neg \psi$ die Behauptung $l_1, \dots, l_n \vdash \neg \varphi$.
