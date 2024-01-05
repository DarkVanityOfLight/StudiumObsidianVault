Wir definieren Substitutionen für freie Variablen von [Termen](Term.md). Gegeben ein Term $t$ und eine freie Variable $x$, schreiben wir $\varphi[t/x]$, um diejenige Formel, die man aus $\varphi$ erhält, indem jedes freie Vorkommen von $x$ in $\varphi$ durch $t$ ersetzt wird. 


## Beispiel

$\varphi := \forall x(P(x)) \land Q(x)$. Wenn $t:= f(y)$, dann bezeichnet $\varphi[t/x]$ die Formel $\forall x(P(x)) \land Q(f(y))$. Zu beachten ist, dass quantifiziertes Vorkommen von $x$ in $P(x)$ nicht durch $t$ ersetzt wird.

## Einsetzbar

Ein Term $t$ ist einsetzbar für $x$  in $\varphi$, wenn es für jede Variable $y$ in $t$ gilt, dass jedes Vorkommen von $y$ in $\varphi$ gebunden ist.

Jede Substitution mit der Notation $\mathcal v[a/x]$ für eine [Bewertung](Bewertung.md) stimmt überein, wenn deren Anwendung auf einsetzbare Terme beschränkt wird.

>[!NOTE] Lemma
>Sei $\varphi$ eine Formel und $t$ ein fuer $x$ einsetzbarere Term in $\varphi$. Dann gilt es, dass 
>$$(\mathfrak S, \mathcal v) \vDash \varphi[t/x] \text{ g.d.w } (\mathfrak S, \mathcal v[\textbf{val}(t)/x])\vDash \varphi$$
>wobei $\textbf{val} := \textbf{val}_{\mathfrak S, \mathcal v}$

Aus diesem Lemma lässt sich die folgende Regel zur Umbenennung der gebundenen Variablen ableiten.

>[!DEFINITION] Proposition
>Sei $\varphi = \mathcal Q x\varphi$  eine Formel, bei der $\mathcal Q \in \lbrace \forall, \exists\rbrace$. Sei $y$ eine nicht in $\psi$ vorkommende Variable. Dann gilt $\varphi \equiv \mathcal Qy(\psi[y/x])$

