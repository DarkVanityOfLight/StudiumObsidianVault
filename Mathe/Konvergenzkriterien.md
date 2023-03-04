
## Supremum
Ein Supremum einer Teilmenge $M \subset \mathbb R$ ist eine kleinste obere [Schranke](Schranken.md) von $M$, d.h. ein $s\in\mathbb R$ mit $s \ge m$ für alle $m\in M$, sodass es kein $s' < s$ gibt mit $s' \ge m$ für alle $m\in M$. 

## Infimum
Ein Infimum ist eine grösste untere [Schranke](Schranken.md)

---

> Jede nach oben beschränkte Teilmenge $\emptyset \not = M \subset \mathbb R$ hat ein Supremum $\sup M$.
> Jede nach unten beschränkte Teilmenge $\emptyset\not= M \subset\mathbb R$ hat ein Infimum $\inf M$.

---

> Jede [monotone](Mathe/Folgen.md#Monotonie) wachsende, von oben [beschränkte](Mathe/Funktionen.md#Beschränkt) [Folge](Mathe/Folgen.md) ist [Konvergent](Mathe/Folgen.md#Konvergent%20und%20Divergent), ebenso jede [monotone](Mathe/Folgen.md#Monotonie) fallende, von unten [beschränkte](Mathe/Funktionen.md#Beschränkt) [Folge](Mathe/Folgen.md).


---
## Cauchykriterium 
Dei [Reihe](Reihe.md) 
$$\sum\limits^{\infty_{n=1}}b_{n}$$
ist konvergent genau dann, wenn es zu jedem $\epsilon > 0$ ein $N$ gibt mit 
$$\left|\sum\limits^{k}_{n=l} b_{n}\right| <\epsilon\forall k \ge l \ge N$$

## Nullfolgenkriterium

[Konvergiert](Konvergenz.md) $\sum\limits^{\infty}_{n=1} b_{n}$ so gilt $\lim_{n\to\infty} b_{n} = 0$.

## Majorantenkriterium
Ist $\sum\limits^{\infty}_{n=1}c_{n}$ konvergent und 
$$|b_{n}|\le c_{n}$$
für alle $n$, dann ist $\sum\limits^{\infty}_{n=1} b_{n}$ konvergent.

## Monoton und beschränkt
Eine Reihe $\sum\limits^{\infty}_{n=1}b_{n}$mit $b_{n} \ge 0$ für alle konvergiert genau dann, wenn die Folge $\sum\limits^{k}_{n=1}b_{n}$ von oben beschränkt ist. 

> Für $s\in\mathbb N, s > 1$ konvergiert die Reihe
> $$\sum\limits^{\infty}_{n=1}\frac{1}{n^{s}}$$

## Quotientenkriterium
Sei $\sum\limits{\infty}_{n=1} b_{n}$ eine Reihe mit $b_{n} \not = 0$ für alle $n$. Gibt es ein $0<\lambda<1$ mit
$$\left|\frac{b_{n+1}}{b_{n}}\right| \le \lambda \forall n$$
dann ist die Reihe konvergent.


## Leibnizkriterium

Ist $(c_{n})$ eine [monoton fallende](Mathe/Funktionen.md#Monoton%20Fallend) [Nullfolge](Nullfolge.md), dann konvergiert die Reihe
$$
\sum\limits^{\infty}_{n=1} (-1)^{n}c_{n}
$$
