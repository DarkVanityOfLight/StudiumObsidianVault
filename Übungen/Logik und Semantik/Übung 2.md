
> Marcel Wirdel, Kilian Lichtner
## Aufgabe 4

### 1 a

$$\begin{align} 
&(p_{1, a} \lor p_{1, b} \lor p_{1, c}) \land (p_{2, a} \lor p_{2, b} \lor p_{2, c}) \land (p_{3, a} \lor p_{3, b} \lor p_{3, c})\\
\land& (p_{1,a}\implies \neg(p_{1,b}))\land(p_{1,a}\implies \neg(p_{1,c}))\\
\land&(p_{1,b}\implies \neg(p_{1,a}))\land (p_{1,b}\implies \neg(p_{1,c}))\\
\land& (p_{1,c}\implies \neg(p_{1,a}))\land (p_{1,c}\implies \neg(p_{1,b}))\\
\land& (p_{2,a}\implies \neg(p_{2,b}))\land(p_{2,a}\implies \neg(p_{2,c}))\\
\land&(p_{2,b}\implies \neg(p_{2,a}))\land (p_{2,b}\implies \neg(p_{2,c}))\\
\land& (p_{2,c}\implies \neg(p_{2,a}))\land (p_{2,c}\implies \neg(p_{2,b}))\\
\land& (p_{3,a}\implies \neg(p_{3,b}))\land(p_{3,a}\implies \neg(p_{3,c}))\\
\land& (p_{3,b}\implies \neg(p_{3,a}))\land (p_{3,b}\implies \neg(p_{3,c}))\\
\land& (p_{3,c}\implies \neg(p_{3,a}))\land (p_{3,c}\implies \neg(p_{3,b}))
\end{align}$$

### 2

$45\degree$  
$$\begin{align} &((p_{1, a} \implies \neg p_{2, b}) \land(p_{1, a} \implies \neg p_{3, c})) \land (p_{1, b} \implies \neg p_{2, c})\\ \land& ((p_{2, a} \implies \neg p_{3, b}) \land ((p_{2, b} \implies \neg p_{1, a})) \land (p_{2, b} \implies \neg p_{3, c})) \land(p_{2, c} \implies \neg p_{1, b})\\ \land& (p_{3, b} \implies \neg p_{a, 2}) \land ((p_{3, c} \implies \neg p_{2, b}) \land (p_{3,c} \implies \neg p_{1,a})) \end{align}$$  
Schachbrett 2 erfüllt diese Gleichung nicht  
  
$-45\degree$ $$\begin{align} &(p_{1, b} \implies \neg p_{2, b}) \land ((p_{1, c} \implies \neg p_{2, b} ) \land (p_{1, c} \implies \neg p_{3, a}))\\ \land& (p_{2, a} \implies \neg p_{1, b}) \land ((p_{2, b} \implies \neg p_{1, c}) \land (p_{2, b} \implies \neg p_{3, a})) \land (p_{2, c} \implies \neg p_{3, b})\\ \land& ((p_{3, a} \implies \neg p_{2, b} \land (p_{3,a} \land p_{1, c})) \land (p_{3, b} \implies \neg p_{2, c}) \end{align}$$  
Schachbrett 1 erfüllt diese Gleichung nicht  
Spalten  
Maximal eine Queen per Spalte: $$\bigwedge_{i=a}^c \bigwedge^3_{j=1} \bigwedge_{1 \le k \le 3, k\not =j} (p_{j, i} \implies \neg p_{k, i})$$ Mindestens eine Queen per Spalte:  
$$ \bigwedge^{c}_{i=a} \bigvee^3_{j=1} p_{j, i} $$  
  
Schachbrett 3 erfüllt diese Bedingung nicht.

### Schachbrett 1

### 1 a

$$\begin{align} (1 \lor 0 \lor 0) \land ( 0 \lor 0 \lor 1) \land(0\lor1\lor0) \end{align}$$

### 1 b

$$\begin{align} (1\implies \neg0)\land(1\implies \neg0)\\ \land(0\implies \neg1\land (0\implies \neg0)\\ \land (0\implies \neg1)\land (0\implies \neg0)\\ \land (0\implies \neg0)\land(0\implies \neg1)\\ \land(0\implies \neg0\land (0\implies \neg1)\\ \land (1\implies \neg0)\land (1\implies \neg0)\\ \land (0\implies \neg1)\land(0\implies \neg0)\\ \land(1\implies \neg0)\land (1\implies \neg0)\\ \land (0\implies \neg0)\land (0\implies \neg1)\\ = 1 \end{align}$$

### Schachbrett 2

### 1 a

$$\begin{align} (0 \lor 0 \lor 1) \land ( 1 \lor 0 \lor 0) \land(0\lor1\lor0) \end{align}$$

### 1 b

$$\begin{align} (0\implies \neg0)\land(0\implies \neg1)\\ \land(0\implies \neg0\land (0\implies \neg1)\\ \land (1\implies \neg0)\land (1\implies \neg0)\\ \land (0\implies \neg0)\land(0\implies \neg1)\\ \land(1\implies \neg0\land (1\implies \neg0)\\ \land (0\implies \neg1)\land (0\implies \neg0)\\ \land (0\implies \neg1)\land(0\implies \neg0)\\ \land(1\implies \neg0)\land (1\implies \neg0)\\ \land (0\implies \neg0)\land (0\implies \neg1)\\ = 1 \end{align}$$

### Schachbrett 3

### 1 a

$$\begin{align} (0 \lor 1 \lor 0) \land ( 0 \lor 1 \lor 0) \land(0\lor1\lor0) \end{align}$$

### 1 b)

$$\begin{align} (0\implies \neg1)\land(0\implies \neg0)\\ \land(1\implies \neg0\land (1\implies \neg0)\\ \land (0\implies \neg1)\land (0\implies \neg0)\\ \land (0\implies \neg1)\land(0\implies \neg0)\\ \land(1\implies \neg0\land (1\implies \neg0)\\ \land (0\implies \neg0)\land (0\implies \neg1)\\ \land (0\implies \neg1)\land(0\implies \neg0)\\ \land(1\implies \neg0)\land (1\implies \neg0)\\ \land (0\implies \neg0)\land (0\implies \neg1)\\ = 1 \end{align}$$

## Aufgabe 5

### 1)
$$I(p) = 1\; I(q) = I(r) = 0$$

$$\begin{align}
&I(\neg(p \land q) \implies r)\\
\iff& I(\neg (p\land q)) \implies I(r)\\
\iff& (1 - I(p\land q)) \implies 0\\
\iff& (1 - \max\lbrace I(p), I(q)\rbrace) \implies 0\\
\iff& (1- \max\lbrace 1, 0 \rbrace) \implies 0\\
\iff& 1 - 0 \implies 0\\
\iff& 1 \implies 0\\
\iff& 0
\end{align}$$

### 2)

_1)_
$$\begin{align}
&q \implies (r \implies (p \lor q))\\
\iff&q \implies (\neg r \lor (p\lor q))\\
\iff&\neg q \lor (\neg r \lor (p\lor q))\\
\iff&\neg q \lor (\neg r \lor p) \lor (\neg r \lor q)\\
\iff&\neg q \lor \neg r \lor \neg q \lor q  \lor (\neg r \lor p)\\
\iff&\neg q \lor \neg r \lor \top \lor(\neg r \lor p)\\
\iff&\top
\end{align}
$$



_2)_
$$\begin{align}
&q \implies p \vDash p \implies q\\
\end{align}$$

Die Belegung $I(p) = 1; I(q) = 0$ ist eine Wahre Belegung für $q\implies p$ aber nicht für $p \implies q$.


_3)_

$$\begin{align}
&\neg p \lor \neg q \iff \neg (p \land q)\\
&\text{Nach de Morgan}:\\
\equiv& \neg p \lor \neg q \iff \neg p \lor \neg q
\end{align}$$
Dies gilt durch die Reflexivität von $\iff$

_4)_
$$(p \implies q) \land (p \implies \neg q)$$
$I(p) = I(q)= 0$ ist eine erfüllende Belegung.

_5)_

$$ (\neg p \lor \neg q) \land (p \lor \neg r) \land (\neg q \lor \neg r) $$

$I(r) = 0; I(p) = 0; I(q) = \star$ ist eine erfüllende Belegung unabhängig von $I(q)$.

## Aufgabe 6

_1)_

Nehmen wir an es gibt eine Belegung $I$ für die gilt:
$$ I(G) \equiv I(\bot)$$
Damit 
$$F \implies \bot$$
gelten kann muss $I(F) \equiv I(\bot)$. Was aber unserer anmahne widerspricht das $I(F) \equiv I(\top)$.

_2)_

Nehmen wir an das $G$ nicht erfüllbar ist:
$$\forall I : I(G) \equiv I(\bot)$$
und das $F$ erfüllbar ist:
$$\exists I : I(F) \equiv I(\top)$$
dann gilt:
$$\begin{align} 
&I(F) \implies I(G)\\
\iff& I(\top) \implies I(\bot)
\end{align}$$

Was eine Valide Aussage ist, wobei $G$ nicht erfüllbar ist.

_3)_

Nehmen wir $G$ sein unerfüllbar.
$$
\forall I : I(G) \equiv I(\bot)
$$
Es gibt eine Belegung für die $F$ wahr ist.

$$\exists I : I(F) \equiv I(\top)$$
Damit $F\implies G$ valide ist müsste gelten:
$$\begin{align}
I(F) \implies I(G)\\
I(\top) \implies I(\bot)\\
\end{align}$$
Wodurch $F  \implies G$  nicht mehr valide ist. Was unserer Annahme widerspricht.

_4)_




## Aufgabe 7

__Induktionsanfang__

Gegeben sei eine Formel $\varphi := x$  bestehend aus einer Variable und zwei Belegungen  $I_1 , I_2 : \mathcal V \to \lbrace 0, 1 \rbrace$. 

1) Mit $I_1(x) \equiv I_2(x)$.

Zu zeigen ist:

$$\begin{align}
&I_1(\varphi) = I_2(\varphi)\\
\iff& I_1(x) = I_2(x)\\
\end{align}$$

Nach Voraussetzung 1) gilt dies.

__Induktionsvoraussetzung__:

Für zwei beliebige aber feste Formel $\varphi, \phi$ gelte $I_1(\varphi) \equiv I_2(\varphi); I_1(\phi) \equiv I_2(\phi)$.

__Induktionsschritt__

Not Fall:

$$\begin{align}
&I_1(\neg \varphi) = I_2(\neg \varphi)\\
\iff& 1 - I_1(\varphi) = 1 - I_2(\varphi)\\
\end{align}$$

Nach Induktionsvoraussetzung gilt $I_1(\varphi) \equiv I_2(\varphi)$.  Also:
$$1 - I_1(\varphi) = 1 - I_1(\varphi)$$
Dies gilt durch die Reflexivität von $=$.

And Fall:

$$\begin{align}
&I_1(\varphi \land \phi) = I_2(\varphi \land \phi)\\
\iff& \max\lbrace I_1(\varphi), I_1(\phi)\rbrace = \max\lbrace I_2(\varphi), I_2(\phi)\rbrace\\
&\text{Nach IV gilt $I_1(\varphi) \equiv I_2(\varphi)$}\\
\iff& \max\lbrace I_1(\varphi), I_1(\phi)\rbrace = \max\lbrace I_1(\varphi), I_2(\phi)\rbrace\\
&\text{Nach IV gilt  $I_1(\phi) \equiv I_2(\phi)$}\\
\iff& \max\lbrace I_1(\varphi), I_1(\phi)\rbrace = \max\lbrace I_1(\varphi), I_1(\phi)\rbrace\\
\end{align}$$
Nach der Reflexivität von $=$ gilt dies.

Or Fall:

$$\begin{align}
&I_1(\varphi \land \phi) = I_2(\varphi \land \phi)\\
\iff& \min\lbrace I_1(\varphi), I_1(\phi)\rbrace = \min\lbrace I_2(\varphi), I_2(\phi)\rbrace\\
&\text{Nach IV gilt $I_1(\varphi) \equiv I_2(\varphi)$}\\
\iff& \min\lbrace I_1(\varphi), I_1(\phi)\rbrace = \min\lbrace I_1(\varphi), I_2(\phi)\rbrace\\
&\text{Nach IV gilt  $I_1(\phi) \equiv I_2(\phi)$}\\
\iff& \min\lbrace I_1(\varphi), I_1(\phi)\rbrace = \min\lbrace I_1(\varphi), I_1(\phi)\rbrace\\
\end{align}$$

Nach der Reflexivität von $=$ gilt dies.
$\blacksquare$
