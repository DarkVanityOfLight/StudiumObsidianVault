Seien $a, b \in\mathbb Z$. Man sagt $b$ teilt $a$
$$b|a$$
wenn es ein $q\in\mathbb Z$ gibt mit $a = b\cdot q$. Dies bedeutet, dass die Division von $a$ durch $b$ Rest $r=0$ liefert.
Zwei Zahlen $a, b$ heißen teilerfremd, wenn für $t\in\mathbb N$ mit $t|a$ und $t|b$ folgt $t=1$.
Sei $m\in\mathbb N$ und $a, b \in\mathbb Z$. Dann heißt $a$ __kongruent__ zu $b$ modulo $m$, geschrieben
$$a \equiv b \mod m$$
wenn $m|(a-b)$



## Beispiel

$1\equiv 7 \mod 3$.

Kongruent modulo $m$ zu sein ist eine [Äquivalenzrelationen](Äquivalenzrelationen.md). Fuer festgelegtes $m$schreiben wir die [Äquivalenzklasse](Äquivalenzrelationen.md#Äquivalenzklassen) (genannt __Restklasse__)von $a$ als
$$\begin{align*}
\overline a &= \lbrace b\in\mathbb Z | a\equiv b \mod m\rbrace\\
&= \lbrace a+k \cdot m | k\in\mathbb Z \rbrace
\end{align*}$$
Somit ist $a\equiv b\mod m$  genau dann, wenn $\overline a = \overline b$.

## Beispiel

Kongruenz modulo $3$ partinoiert $\mathbb Z$ in die $3$ Restklassen
$$\begin{align*}
\overline 0 &= \lbrace..., -3, 0, 3, 6, ... \rbrace\\
\overline 1 &= \lbrace ..., -2, 1, 4, 7, ... \rbrace\\
\overline 2 &= \lbrace ..., -1, 2, 5, 8, ... \rbrace
\end{align*}$$
denn bei der Division mit Rest von ganzen Zahlen nach $3$ treten genau die Reste $0, 1, 2$ auf.

