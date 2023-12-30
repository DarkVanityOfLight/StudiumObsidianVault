
Die Semantik einer Formel ist eine [Boolesche Funktion](Boolesche%20Funktion.md):
$$f : \lbrace0,1\rbrace^{\mathcal V} \to \lbrace 0, 1\rbrace$$



Eine [Belegung](Belegung.md) lässt sich zu $I: PROP \to \lbrace 0, 1 \rbrace$ erweitern:
1. $I(\top) = 1, I(\bot) = 0$
2. $I(\neg \varphi) = 1 - I(\varphi)$
3. $I(\varphi \lor \psi) = \max\lbrace I(\varphi), I(\psi) \rbrace$
4. $I(\varphi \land \psi) = \min\lbrace I(\varphi), I(\psi) \rbrace$


> [!DEFINITION] 
> Eine Formel $\varphi$ gilt unter der [Belegung](Belegung.md) $I$, so schreiben wir $I \vDash \varphi$, falls $I(\varphi) = 1$.
> auch als $I$ erfüllt $\varphi$ oder $I$ ist ein Modell für $\varphi$ gelesen
