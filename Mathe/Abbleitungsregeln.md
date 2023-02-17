
## Summenregel
Sind $f: D\to\mathbb R$ und $g: D\to\mathbb R$ [differenzierbar](Differenzierbarkeit.md), so auch $f+g$ mit der Summenregel
$$(f + g)' = f' + g'$$

## Produktregel

und $f\cdot g$ mit der Produktregel
$$(fg)' = f \cdot g' + f' \cdot g$$

## Quotientenregel
Falls $g(x) \not = 0$ fuer alle $x\in D$, dann ist auch $\frac{f}{g}$ differenzierbar mit der Quotientenregel

$$\left(\frac{f}{g}\right) = \frac{g \cdot f' - f \cdot g'}{g^{2}}$$


## Kettenregel
Sind $f: D \to\mathbb R$ und $g: E\to\mathbb R$ differenzierbar und $g(E) \subset D$, so ist $f\cdot g: E\to\mathbb R$ differenzierbar und
$$(f \circ g)' = (f' \circ g) \cdot g'$$



## Ableiten von Potenzreihen

[Potenzreihen](Potenzreihe.md)
$$P(x) = \sum\limits^{\infty}_{n=0} a_{n}x^{n}$$ sind in ihrem Konvergenzbereich als Funktion differenzierbar mit der gliedweisen Ableitung
$$P'(x) = \sum\limits^{\infty}_{n=1} na_{n} a^{n-1}$$
Damit folgt sofort:

> Eine [Potenzreihe](Potenzreihe.md) $P(x) = \sum\limits^{\infty}_{n=0} a_{n}x^{n}$ ist in ihrem Konvergenzbereich als Funktion beliebig oft differenzierbar, und es gilt:
> $$a_{n} = \frac{P^{(n)}(0)}{n!}$$
> für alle $n$

