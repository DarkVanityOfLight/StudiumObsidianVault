Betrachten wir die [LIA](Logik/Ganzzahlige%20Lineare%20Arithmetik.md).
Wir zeigen, wie $x$ in $\exists x\varphi$ eliminierbar ist, wobei
$$\varphi = \bigwedge^n_{i=1} x \sim_i t_i, \qquad \textbf{mit} \sim_i\in\lbrace <, >, =\rbrace$$

## Fall 1
Ein Konjunkt ist $x=t$. Man verwende:
$$\mathcal Q_+ \vDash \exists x\varphi \leftrightarrow \varphi[t/x]$$
_Andernfalls_: Trenne Ober-/Untergrenzen von $x$

$$\mathcal Q_+ \vDash \exists x\left( \bigwedge^r_{i=1} l_i < x \land \bigwedge^s_{j=1} x< u_j \right) \bigwedge^r_{i=1}\bigwedge^s_{j=1} l_i < u_j$$

### Nicht-Strikte Ungleichungen

Die oben genannte [Äquivalenz](Äquivalenz.md) lässt sich auf $\le$ erweitern(wie auch der Fall bei der Theorie dichter Ordnungen)


## Komplexität

Die Elimination eines Quantors erhöht die Anzahl $m$ von (Un)Gleichungen auf $m^2$. 

Dementsprechend: $n$ Quantoren, ergeben $\ge m^{2^n}$ (Un) Gleichungen

Nach der Eliminierung redundanter [Atome](Atomare%20Aussage.md)/Disjunkte, läuft das Verfahren in $3-EXPTIME$.

