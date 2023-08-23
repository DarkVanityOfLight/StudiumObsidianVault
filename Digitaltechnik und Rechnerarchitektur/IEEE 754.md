
| class            | sign | exponent  | mantissa           |
| ---------------- | ---- | --------- | ------------------ |
| $NaN$            | $*$  | $1\dots1$ | $\not=0\dots0$     |
| $\pm\infty$      | $*$  | $1\dots1$ | $0\dots0$          |
| denormale Zahlen | $*$  | $0\dots0$ | $\not = 0 \dots 0$ |
| Nullen           | $*$  | $0\dots0$ | $0\dots0$          |

Normalisierte Zahlen verwenden die Exponenten $0\dots01$ bis $1\dots10$

![iee](iee.png)


## Multiplikation

- Betrachte Fälle wie $0, \infty, NaN$
- Multipliziere die Mantissa
- Normalisiere und Runde $P$ auf $23$ Stellen
- Addiere die Exponenten und Subtrahiere den Bias $127$
- Ueberpruefe auf Overflows


## Division

- Subtrahiere Exponenten
- Dividiere die Mantisse mit [Radix-B](Radix-B.md) Division
- Der Quotient ist zwischen $0.5$ und $2.0$
- Normalisiere sollte der Quotient zwischen $0.5$ und $1.0$ liegen

## Addition

- Betrachte Fälle wie $0, \infty, NaN$
- Passe die Exponenten an
- Addiere die Shifted Mantissa
- Runde und Normalisiere
- Ueberpruefe auf Overflows