Wir definieren Substitutionen für freie Variablen von [Termen](Term.md). Gegeben ein Term $t$ und eine freie Variable $x$, schreiben wir $\varphi[t/x]$, um diejenige Formel, die man aus $\varphi$ erhält, indem jedes freie Vorkommen von $x$ in $\varphi$ durch $t$ ersetzt wird. 


## Beispiel

$\varphi := \forall x(P(x)) \land Q(x)$. Wenn $t:= f(y)$, dann bezeichnet $\varphi[t/x]$ die Formel $\forall x(P(x)) \land Q(f(y))$. Zu beachten ist, dass quantifiziertes Vorkommen von $x$ in $P(x)$ nicht durch $t$ ersetzt wird.

## Einsetzbar

Ein Term $t$ ist einsetzbar für $x$  in $\varphi$, wenn es für jede Variable $y$ in $t$ gilt, dass jedes Vorkommen von $y$ in $\varphi$ gebunden ist.

Jede Substitution mit der Notation $\nu[a/x]$ für eine [Bewertung](Logik%20und%20Semantik%20von%20Programiersprachen/Bewertung.md) stimmt überein, wenn deren Anwendung auf einsetzbare Terme beschränkt wird.

>[!NOTE] Lemma
>Sei $\varphi$ eine Formel und $t$ ein fuer $x$ einsetzbarere Term in $\varphi$. Dann gilt es, dass 
>$$(\mathfrak S, \nu) \vDash \varphi[t/x] \text{ g.d.w } (\mathfrak S, \nu[\textbf{val}(t)/x])\vDash \varphi$$
>wobei $\textbf{val} := \textbf{val}_{\mathfrak S, \nu}$

Aus diesem Lemma lässt sich die folgende Regel zur Umbenennung der gebundenen Variablen ableiten.

>[!DEFINITION] Proposition
>Sei $\varphi = \mathcal Q x\varphi$  eine Formel, bei der $\mathcal Q \in \lbrace \forall, \exists\rbrace$. Sei $y$ eine nicht in $\psi$ vorkommende Variable. Dann gilt $\varphi \equiv \mathcal Qy(\psi[y/x])$


## Gleichzeitige Substitution

Eine __(gleichzeitige) Substitution__ ist eine Abbildung $\theta: VAR \to TERMS$
Die Notation $\lbrace t_1 / x_1, \dots, t_n / x_n\rbrace$ bezeichnet die Substitution 
$$\begin{align}
\theta :& x_1 \mapsto t_1\\
&\vdots\\
& x_n \mapsto t_n\\
&y\mapsto y
\end{align}$$

### Substitutionen Anwenden

Gegeben sei ein Ausdruck $E$ ([Term](Term.md), [Literal](Literal.md), [Klausel](Klausel.md)), schreibe 
$$E\theta \text{ oder } E[\theta]$$
um Folgendes zu bezeichnen: "gleichzeitig jedes Vorkommen von $x$ durch $\theta$(x)" ersetzen.

### Beispiel

$E = \lbrace P(x), Q(f(y)) \rbrace$, $\theta = \lbrace y/x, f(a)/y$, dann
$$E\theta = \lbrace P(y), Q(f(f(a))) \rbrace$$


### Substitutionen Verknüpfen

Gegeben sind zwei Substitutionen 
$\theta_1: VAR \to TERMS$ $\theta_2: VAR \to TERMS$
IHre Komposition
$$\theta_1 \circ \theta_2: VAR \to TERMS$$
ist die Substitution 
$$x\mapsto\theta_1(x)[\theta_2]$$

>[!NOTE]
>Es gilt für jeden Ausdruck $E$, dass $E[\theta\sigma] = (E\theta)\sigma$

>[!NOTE] Assoziativität
>$$(\theta_1\theta_2)\theta_3 = \theta_1(\theta_2\theta_3)$$

