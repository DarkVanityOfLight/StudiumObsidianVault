> Marcel Wirdel, Kilian Lichtner


## Aufgabe 3

$$\begin{align}
\underline{x,\; x \rightarrow((x\rightarrow y) \rightarrow y)}\\
\underline{x,\; ((x\rightarrow y) \rightarrow y)}\\
\underline{\mathcal H_1, \; y \rightarrow y}\\
\top
\end{align}$$

$$\begin{align}
\underline{\mathcal H_4, \; \neg p \rightarrow (p\rightarrow (p \rightarrow q))}\\
\top
\end{align}$$
## Aufgabe 4

__1__
_a_

Formel I:
$$
a \lor b
$$

Formel II:
$$
(a \lor n) \land (b\lor \neg n)
$$

### Equisatisfiable
Formel I ist genau dann erfüllbar wenn Formel II erfüllbar ist:

$'\rightarrow'$:

Angenommen Formel I ist erfüllbar, also entweder $a$ oder $b$ ist wahr, oder beide:


Wenn $a$ wahr ist, wählen wir $n$ als falsch, damit ist 
$$\begin{align}
&(\top \lor \bot) \land (b\lor \neg\bot)\\
\iff&(\top) \land (\top)\\
\iff&\top
\end{align}$$
Wenn $b$ wahr ist, wählen wir $n$ als wahr:
$$\begin{align}
&(a \lor \top)\land (\top \lor \neg \top)\\
\iff&\top \land \top\\
\iff&\top
\end{align}$$
In jedem Fall, in dem Formel I erfüllbar ist, ist auch Formel II erfüllbar.

$'\leftarrow'$

Wenn Formel II erfüllbar ist, dann muss mindestens einer der beiden Variablen $a, b$ wahr sein, denn:
Nehmen wir an $n = \top$:
$$\begin{align}
&(a\lor \top) \land (b \lor \neg \top)\\
\iff&\top \land b\\
\end{align}$$
Dies ist genau dann erfüllbar wenn $b  = \top$

Nehmen wir an $n = \bot$
$$\begin{align}
&(a\lor \bot) \land (b\lor \neg \bot)\\
\iff&(a) \land (b \lor \top)\\
\iff& a \land \top
\end{align}$$
Dies ist genau dann erfüllbar wenn $a = \top$.

### Equivalent

Die beiden Formeln sind nicht Äquivalent, da die Belegung:
$I(a) = I(n) = 1, I(b) = 0$ ein Modell für I aber nicht für II ist:

$$\begin{align}
&I(a \lor b)\\
\iff& max\lbrace I(a), I(b)\rbrace\\
\iff& max\lbrace 1, 0\rbrace\\
\iff&1
\end{align}$$

$$\begin{align}
&I((a\lor n) \land (b\lor \neg n))\\
\iff&\min\lbrace I(a\lor n), I(b \lor \neg n)\rbrace\\
\iff&\min\lbrace \max\lbrace I(a), I(n)\rbrace, \max\lbrace I(b), I(\neg n)\rbrace\rbrace\\
\iff& \min\lbrace\max\lbrace1, 1\rbrace, \max\lbrace 0, (1 - I(n))\rbrace\rbrace\\
\iff& \min\lbrace1, \max\lbrace0, 1-1\rbrace\rbrace\\
\iff&\min\lbrace1, 0\rbrace\\
\iff& 0
\end{align}$$

_b_

$$

$$

---

__2__

_a_

$$(x_1 \land y_1) \lor (x_2 \land y_2) \lor (x_3 \land y_3) \lor (x_4 \land y_4)$$
Die Formel ist bereits in DNF. Dementsprechend müssen wir Tseitin's Transformation nicht anwenden.

$C = \emptyset$

$$\begin{align}
\varphi_1 \leftrightarrow x_1
\end{align}$$



_b_

$$x_1 \lor (x_2 \land x_3 \land x_4 \land x_5)$$Die Formel ist bereits in DNF. Dementsprechend müssen wir Tseitin's Transformation nicht anwenden.