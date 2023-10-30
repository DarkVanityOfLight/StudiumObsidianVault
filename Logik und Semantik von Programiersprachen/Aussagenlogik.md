
Eine aussagenlogische Formel ist eine Zeichenkette über das Alphabet $$\Sigma = \mathcal V \cup \mathcal C \cup O \cup P$$

1. $\mathcal V = \lbrace p, q, x, y\rbrace$, Menge von Variablen
2. $\mathcal C = \lbrace \top, \bot\rbrace$, Menge von Konstanten
3. $\mathcal O = \lbrace \neg, \land, \lor$, Mege von Verknüpfungen
4. $\mathcal P = \lbrace (,)\rbrace$, Menge von Klammerzeichen.

> [!NOTE] EIne Variable wird auch als atomare Aussage bezeichnet

## Syntax

Eine aussagenlogische Formel $\varphi$ wird durch Rekursion definiert:

1. Eine Variable $x$ ist eine Formel
2. Eine Konstante (d.h. $\top$ oder $\bot$) ist eine Formel
3. Für Formeln $\varphi_1, \varphi_2$ sind die Folgenden auch Formeln:
$$(\neg \varphi_1)\, (\varphi_1 \land \varphi_2)\, (\varphi_1 \lor \varphi_2)$$

Dies lässt sich als BNF-Grammatik zusammenfassen:
$$\varphi ::= \top | \bot | (\neg\varphi) | (\varphi \land \varphi) | (\varphi\lor\varphi)$$

>[!IMPORTANT] $PROP$ bezeichnet die Menge aller aussagenlogischen Formeln


## Entklammerung

Klammerung macht eine Formel manchmal unlesbar,
wir entfernen das äußerste Klammerpaar und definieren Folgende Operatorfolge:

|Operator|Rang|
|---------|------|
|$\neg$ | $1$|
|$\land$|$2$|
|$\lor$ | $3$|
|$\implies$|$4$|

---

Bis jetzt ist eine Formel nur eine Zeichenreihe von Symbolen ohne Bedeutung.

## Semantik

> [!DEFINITION] Eine Belegung ist eine Funktion
> $$I : \mathcal V \to \lbrace1, 0\rbrace$$

Die Semantik einer Formel ist eine __Boolsche Funktion__:
$$f : \lbrace0,1\rbrace^{\mathcal V} \to \lbrace 0, 1\rbrace$$

Eine Belegung lässt sich zu $I: PROP \to \lbrace 0, 1 \rbrace$ erweitern:
1. $I(\top) = 1, I(\bot) = 0$
2. $I(\neg \varphi) = 1 - I(\varphi)$
3. $I(\varphi \lor \psi) = \max\lbrace I(\varphi), I(\psi) \rbrace$
4. $I(\varphi \land \psi) = \min\lbrace I(\varphi), I(\psi) \rbrace$

Eine Formel $\varphi$ gilt unter der Belegung $I$ so schreiben wir $I \vDash \varphi$, falls $I(\varphi) = 1$.

auch als $I$ erfüllt $\varphi$ oder $I$ ist ein Modell für $\varphi$ gelesen

## Boolesche Funktion

Aus einer Formel  $\varphi$ entsteht eine Boolesche Funktion

$$[[\varphi]] : \lbrace0, 1\rbrace^{\mathcal V} \to \lbrace0, 1\rbrace$$

wobei 
$$[[ \varphi]](I) := I(\varphi)$$
gilt.

Die in einer Formel fehlenden Variablen beeinflussen den Warheitswert einer Formel nicht, d.h. die Variable irrelevant
 
Sei $\varphi$ eine Formel und seien $I_1, I_2 : \mathcal V \to \lbrace 0, 1\rbrace$ zwei Belegungen, so dass die Zeilwerte von $I_1$ und $I_2$ für jede in $\varphi$ vorkommende Variable übereinstimmen. Dann gilt es, dass $I_1 (\varphi) = I_2(\varphi)$.

Infolgedessen, lässt sich $[[\varphi]]$ als eine Boolesche Funktion ansehen:
$$\lbrace0, 1\rbrace^{\mathcal Var(\varphi)} \to \lbrace 0, 1\rbrace$$


## Semantische Implikation

Eine Formel $\varphi$ impliziert (semantisch) eine Formel $\psi$ $\varphi \vDash \psi$ genau dann, wenn jedes Modell von $\varphi$ auch ein Modell von $\psi$ ist.



