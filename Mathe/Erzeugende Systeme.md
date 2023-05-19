Sei $V$ ein $K$-[Vektorraum](Vektorräume.md). 
Vektoren $v_{1}, ..., v_{n} \in V$ heißen Erzeugendensystem von $V$, wenn 
$$V = \langle v_{1}, ..., v_{n} \rangle$$
Vektoren $v_{1}, ..., v_{n} \in V$ heißen __linear unabhängig__, wenn aus
$$\lambda_{1}v_{1} + ... + \lambda_{n} v_{n} = 0$$
folgt dass
$$\lambda_{1} = ... = \lambda_{n} = 0$$ anderenfalls __linear abhängig__

$$\langle v_{1}..., v_{n}\rangle = \lbrace \sum\limits^{n}_{i=1} \lambda_{i}\cdot v_{i} | \lambda \in k \rbrace$$



## Basis

Die __Einheitsvektoren__
$$e_{1} = \left(\begin{array}{}1 \\ 0 \\ \vdots \\ 0\end{array}\right), ..., e_{n} = \left(\begin{array}{}0 \\ \vdots \\ 0 \\ 1\end{array}\right) \in K^{n}$$
bilden eine Basis von $K^{n}$, die sogenannte __Standardbasis__: 
Jeder Vektor in $K^{n}$ laesst sich schreiben als
$$\left(\begin{array}{}a_{1} \\ \vdots \\ a_{n}\end{array}\right) = a_{1}e_{1} + ... + a_{n}e_{n}$$
und $e_{1}, ..., e_{n}$ sind linear unabhängig, denn
$$a_{1}e_{1}+ ... + a_{n}e_{n}= 0 \implies a_{1} = ... = a_{n}= 0$$
Die Polynome $1, x, ..., x^{d}$ bilden eine Basis von $K[x]_{\le d}$, denn
$$a_{0} \cdot 1 + ... + a_{d} \cdot x^{d} = 0 \implies a_{1} = ... = a_{d} = 0$$
Mit Hilfe einer Basis kann man den Lösungsraums eines homogenen linearen Gleichungssystems wesentlich kompakter schreiben. Die Basis liest man von der reduzierten Zeilenstufenform ab:

Eine Basis des Lösungsraums eines homogenen linearen Gleichungssystems erhalten wir in der parametrischen Darstellung der Lösungsmenge für die freien Variablen eine Einheitsbasis einsetzen.

## Beispiel

Das System 
$$\begin{align*}
l_{1} &= x_{1} + 2x  - 2x_{5} &= 0\\
l_{2}&= x_{3}+ x_{5} &= 0\\
l_{3} &=  x_{4}+ 2x_{5} &= 0
\end{align*}$$
in $\mathbb Q[x]$ ist schon in reduzierter Zeilenstufenform, also die Lösungsmenge

$$V = \left\lbrace \left(\begin{array}{}-2x_{2} + 2x_{5} \\ x_{2} \\ -x_{5} \\ -2x_{5} \\ x_{5}\end{array}\right)|x_{2}, x_{5}\in\mathbb Q\right\rbrace$$
und somit erhalten wir mit $(x_{2}, x_{5}) = (1, 0)$ und $(x_{2}, x_{5}) = (0, 1)$ eine Basis:

$$V = \left\langle \left(\begin{array}{}-2 \\ 1 \\ 0 \\ 0\\ 0\end{array}\right), \left(\begin{array}{} - 2\\ 0 \\ -1 \\ -2 \\ 1\end{array}\right)\right\rangle$$


## Basis der Lösungsmenge von homogenen LGLS

1) red ZSF
2) impl. Darst der Lösungsmenge
3) param """" freie Var $x_{i1},..., x_{id}$
4) Setze Einheitsbasis ein $(x_{i1}, ... x_{id}) = (1, 0, ..., 0), ..., (0, ... 0, 1)$

#klausur 