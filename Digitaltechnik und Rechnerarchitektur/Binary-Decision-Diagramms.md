Ein Binary Decision Diagram (BDD) ist eine Datenstruktur, die verwendet wird, um boolesche Funktionen darzustellen. Es wird häufig in der Schaltkreisentwurfsautomatisierung und in der formalen Verifikation eingesetzt.

Ein BDD besteht aus Knoten und Kanten, die zu einem gerichteten azyklischen Graphen(DAGs) führen. Es gibt einen einzelnen Wurzelknoten $v_{0}$. Jeder Knoten im BDD repräsentiert eine boolesche Variable und hat zwei ausgehende Kanten, die entweder zu den Kindknoten führen oder zu den konstanten Blattknoten, die die Werte "wahr" oder "falsch" repräsentieren($L_{0}, L_{1}$).

Jeder Knoten $v\not\in\lbrace L_{0}, L_{1}\rbrace$:
- hat zwei Nachfolger notiert mit $\texttt{high}(v)$ und $\texttt{low}(v)$
- ist labeled mit einer variable $\texttt{label}(v)$

Blätter sind folgendermaßen benannt:
$\texttt{label}(L_{0}) := 0$ und $\texttt{label}(L_{1}) := 1$

Kannten repraesentieren die Variablen Ordnung -> Geordnete BDDs (OBDDs):
- $D(\texttt{label}(\texttt{high}(v))) < D(\texttt{label}(v))$
- $D(\texttt{label}(\texttt{low}(v))) < D(\texttt{label}(v))$


Die BDD-Struktur ermöglicht es, komplexe boolesche Funktionen effizient darzustellen und Operationen wie die Konjunktion, Disjunktion und Negation durchzuführen. Durch die Reduzierung von redundanten Teilbäumen kann ein BDD eine boolesche Funktion kompakt repräsentieren und Platz sparen.

Um ein BDD für eine bestimmte boolesche Funktion zu erstellen, wird der Funktionsterm rekursiv in Variablen aufgeteilt, wobei jedes Teilterm einem Teilbaum im BDD entspricht. Durch das Durchlaufen der Teilbäume kann die Funktion ausgewertet werden.

## Variablen Ordnung

Gegeben ist ein Set an Variablen $V = \lbrace x_{1},...x_{n}\rbrace$ und eine [bijektive](Bijektiv.md) Funktion $\pi: V \to\lbrace2,..., |V| + 1\rbrace$
$\pi$ ist eine [Totalordnung](Totalordnung.md) der Variablen.
Wir definieren $\pi$ weiter als Funktion über $V \cup\lbrace1,0\rbrace$:
$$
D(v) = \begin{dcases}
\pi(v) : \text{ if } v\in V\\
v: \text{ if } v\in\lbrace1,0\rbrace
\end{dcases}
$$
Dies erlaubt den Vergleich von atomaren Propositionen in $V \cup \lbrace1,0\rbrace$:
$$x \prec_{\pi} y: \iff D(x) < D(y)$$

Atomare Propositionen werden folgendermaßen Sortiert:
$$0\prec_{\pi}1 \prec_{\pi} x_{1} \prec_{\pi} x_{2}\prec_{\pi} ... \prec_{\pi}x_{n}$$


## Isomorphe BDDs

OBDDs $B_{1}$ und $B_{2}$ sind [Isomorph](Isomorphismen.md) falls es eine [bijektive](Bijektiv.md) Funktion $\Theta: V_{1} \to V_{2}$ gibt, die die Knoten von $B_{1}$ auf die Knoten von $B_{2}$ abbildet, sodass:
- $\texttt{label}(v) = \texttt{label}(\Theta(v))$
- Wenn $v$ ein Blatt ist, dann gilt: $\Theta(v)$ ist auch ein Blatt
- Falls $v$ kein Blatt ist, dann:
	- $\Theta(\texttt{high}(v)) = \texttt{high}(\Theta(v))$
	- $\Theta(\texttt{low}(v)) = \texttt{low}(\Theta(v))$


## Reduzierte OBDDs(ROBDDs)

Ein OBDD heißt reduziert wenn und nur wenn gilt:
- Es existiert kein $v$ mit $\texttt{high}(v) = \texttt{low}(v)$
- Es existiert kein $v, v'$ sodass die Subgraphen von $v, v'$  [Isomorph](Isomorphismen.md) sind

Man verwendet zwei Regeln um OBDDs in ROBDDs umzuwandeln:
- Elimination Regel: Falls $\texttt{high}(v) = \texttt{low}(v)$ gilt, lösche $v$ und hänge alle Kanten die nach $v$ führen nach $\texttt{high}(v)$
- Isomorphie Regel: Falls $\texttt{label}(v'), \texttt{high}(v) = \texttt{high}(v')$ und $\texttt{low}(v) = \texttt{low}(v')$, lösche $v'$ und hänge alle Kanten die nach $v'$ führen nach $v$


