
$l_{1}, l_{2} \in K[x_{1},...,x_{n}],0 \not = c \in K$
$$$\left. l_{1}(x)= 0 \atop l_{2}(x) = 0 \right\} \iff \left\{l_{1}(x) = 0 \atop l_{2}(x) + c \cdot l_{1}(x) = 0\right.$$

$$l_{1}(x) = 0 \iff c \cdot l_{1}(x) = 0$$

$$\left. l_{1}(x) = 0 \atop l_{2}(x) = 0 \right\} \iff \left\{l_{2}(x) = 0 \atop l_{1}(x) = 0\right.$$

---

$$f = x_{s} x_{s} + ... + c_{n} x_{n} \in K[x_{1}, ..., x_{n}]$$

__Leitterm__ $LT(f) = c_{s}x_{s}$
__Leitvariable__ $L(f) = x_{s}$
__Leitkoeffiezient__ $LC(f) = c_{s}$

### Beispiel

$f = 2 \cdot x_{2} + 5 \cdot x_{3} + x_{4}$

$LT(f) = 2 \cdot x_{2}$
$L(f) = x_{2}$
$LC(f) = 2$
$\text{tail}(f) = 5 x_{3}+ x_{4}$

---
 Für ein homogenes lineares [[Gleichungssystem]] gegeben durch $l_{1}, ..., l_{r} \in K[x_{1}, x_{n}]$ berechnet der folgende Algorithmus ein äquivalentes System sodass alle leitvariablen verschieden sind.

![Gaußalgorithmus](Algorithmen/Gaußalgorithmus.md)

![Reduzierte Zeilenstufenform](Reduzierte%20Zeilenstufenform.md)

#klausur 