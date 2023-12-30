
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
x_1 \lor x_2
$$
$$\begin{align}
&\varphi \equiv F_1 \leftrightarrow (x_1 \lor x_2)\\
\iff&\varphi \equiv (F_1 \rightarrow(x_1 \lor x_2)) \land (x_1 \lor x_2) \rightarrow F_1\\
\iff&\varphi \equiv (\neg F_1 \lor x_1 \lor x_2) \land (\neg x_1 \lor F_1) \land (\neg x_2 \lor F_1)
\end{align}$$

Wir erhalten also die Formel:
$$\begin{align}
&F_1 \land \varphi \\
\iff& F_1 \land (\neg F_1 \lor x_1 \lor x_2) \land (\neg x_1 \lor F_1) \land (\neg x_2 \lor F_1)
\end{align}$$


Nach der Korrektheit der Tseitin Transformation ist diese Formel Equivsatisfiable.

Die Belegung $I(x_1) = I(x_2) = 1; I(F_1) = 0$ ist ein Modell für die Urspruengliche Formel, aber nicht fuer die Transformierte:

$$\begin{align}
&I(x_1 \lor x_2) \\
\iff& \max\lbrace I(x_1), I(x_2)\rbrace\\
\iff& \max\lbrace 1, 1\rbrace\\
\iff& 1
\end{align}$$

$$\begin{align}
&I(F_1 \land (\neg F_1 \lor x_1 \lor x_2) \land (\neg x_1 \lor F_1) \land (\neg x_2 \lor F_1))\\
\iff& \min\lbrace I(F_1), \min\lbrace \max\lbrace I(\neg F_1), I(x_1), I(x_2) \rbrace, \max\lbrace I(\neg x_1), I(F_1) \rbrace, \max\lbrace I(\neg x_2), F_1\rbrace  \rbrace\rbrace\\\iff&
\min\lbrace 0, \min\lbrace \max\lbrace 1-0, 1, 1 \rbrace, \max\lbrace 1 - 1, 0 \rbrace, \max\lbrace 1 - 1, 0\rbrace  \rbrace\rbrace\\
\iff&\min\lbrace 0, \min\lbrace 1, 0, 0 \rbrace \rbrace\\
\iff&\min\lbrace 0, 0 \rbrace\\
\iff& 0
\end{align}$$

---

__2__

_a_

$$(x_1 \land y_1) \lor (x_2 \land y_2) \lor (x_3 \land y_3) \lor (x_4 \land y_4)$$

$$\begin{align}
&C = \bigcup^4_{i=1}  \varphi_i = F_i \leftrightarrow (x_i\land y_i)\\
\iff&C = \bigcup^4_{i=1}  \varphi_i = F_i \rightarrow(x_i\land y_i), (x_i \land y_i) \rightarrow F_i\\
\iff& C = \bigcup^4_{i=1}  \varphi_i =(\neg F_i \lor x_i) ,(\neg F_i \lor y_i) , (\neg x_i \lor \neg y_i \lor F_i)
\end{align}$$

$$(F_1 \lor F_2 \lor F_3 \lor F_4) \land \varphi_1 \land \varphi_2 \land \varphi_3 \land \varphi_4$$



_b_


$$\begin{align}
&x_1 \lor (x_2 \land x_3 \land x_4\land x_5)\\
\iff& x_1 \lor((x_2 \land x_3) \land (x_4\land x_5))
\end{align}$$

$$\begin{align}
&\varphi_1 \equiv
F_1 \leftrightarrow x_2 \land x_3\\
\iff& \varphi_1 \equiv F_1 \rightarrow (x_2 \land x_3) \land (x_2 \land x_3) \rightarrow F_1\\
\iff&\varphi_1 \equiv (\neg F_1 \lor x_2) \land (\neg F_1 \lor x_3) \land (\neg x_2 \lor x_3 \lor F_1)
\end{align}$$


$$\begin{align}
&\varphi_2 \equiv
F_2 \leftrightarrow x_4 \land x_5\\
\iff& \varphi_2 \equiv F_2 \rightarrow (x_4 \land x_5) \land (x_4 \land x_5) \rightarrow F_2\\
\iff&\varphi_2 \equiv (\neg F_2 \lor x_4) \land (\neg F_2 \lor x_5) \land (\neg x_4 \lor x_5 \lor F_2)
\end{align}$$


Unsere Formel sieht damit so aus:
$$x_1 \lor (F_1 \land F_2) \land \varphi_1 \land \varphi_2$$

Nun ersetzen wir $F_1 \land F_2$ mit $F_3$

$$\begin{align}
&\varphi_3 \equiv F_3 \leftrightarrow F_1 \land F_2\\
\iff&\varphi_3 \equiv (F_3 \rightarrow (F_1\land F_2)) \land ((F_1 \land F_2) \rightarrow F_3)\\
\iff& \varphi_3 \equiv (\neg F_3 \land F_1) \land (\neg F_3 \lor F_2) \land(\neg F_1 \lor \neg F_2 \lor F_3)
\end{align}$$

Wir erhalten
$$\begin{align}
&x_1 \lor F_3 \land \varphi_1 \land \varphi_2 \land \varphi_3\\
\iff&(x_1 \lor F_3) \land \varphi_1 \land \varphi_2 \land \varphi_3
\end{align}$$


## Aufgabe 5

__1__
$$(p \lor \neg q \lor \neg r) \land (q \lor \neg p \lor r) \land(r\lor \neg q)$$

![|500](dpll1.excalidraw )

__2__
$$\begin{align}
&((p\land q) \lor (q\rightarrow r)) \lor \neg(t\rightarrow \neg q \land \neg r) \lor (\neg p \land q)\\
\end{align}$$
![|2000](dpll2.excalidraw)

__3__

$$
(\neg p \lor \neg q) \land (\neg r \lor \neg p \lor q) \land (q\lor r) \land(p \lor \neg q) \land (q\lor t) \land(\neg t \lor p\lor \neg q)
$$

![2000](dpll3.excalidraw)


## Aufgabe 6
__1__
![](res1.excalidraw)

__2__

$$\begin{align}
&(((p \rightarrow q) \land (q \rightarrow r)) \land (q \rightarrow r) \rightarrow \neg (\neg r \land p))\\

\end{align}$$

![res2](res2.png)

