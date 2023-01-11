## Cauchykriterium
$$\begin{align}
\sum^{\infty}_{n = 1} b_n \text{Konvergent}\\
\iff \forall \varepsilon > 0 \exists N: \left|\sum^{k}_{n = l}b_n\right| < \varepsilon \forall k \ge l \ge N
\end{align}$$

## Nullfolgenkriterium

$$\sum^{\infty}_n = b_n \text{Konvergent} \implies \lim_{n \to \infty} b = 0$$

## Majorantenkriterium

$$\sum^{\infty}_{n = 1} c_n \text{konvergent} \qquad |b_n| \le c_n \forall n \implies \sum^{\infty}_{n=1} b_n \text{konvergent}$$


### Beispiel Minorantenkriterium

$$\begin{align}
&\sum^{\infty}_{n = 1} \frac{1}{n+1000}\\
&\frac{1}{1000} \cdot \frac{1}{n} \le \frac{1}{n+1000} \quad \forall n\\
&\text{Falls} \sum^{\infty}_{n = 1} \frac{1}{n+1000} \text{konvergent} \implies \sum \frac{1}{1000 \cdot n} \implies \sum^{\infty}_{k = 1} \frac{1}{n} \text{Konvergent(Wiederspruch)}
\end{align}$$

## Quotientenkriterium

$$\begin{align}
\sum^{\infty}_{n = 1} b_n \qquad, b_n \not = 0 \forall n\qquad \exists 0 < \lambda < 1:
\left|\frac{b_{n+1}}{b_n} \right|\le \lambda \forall n
\end{align}$$

Falsch für $\lambda = 1$

## Leibnizkriterium
$(C_n)$ monoton fallende Nullfolge
$\implies \sum (-1)^n \cdot C_n$ konvergent

---

$$\sum^{\infty}_{n=1} = \frac{1}{n^s} \quad S\in \mathbb N \quad S \ge 2$$

$\forall k \quad \exists w: k\le 2^w - 1$
$$\begin{align}
&a_k \le a_{2^w - 1} = \sum^{w}_{i=1} \sum^{2^{i-1}}_{n = 2^{i-1}} \frac{1}{n^S}\\
&\le \sum^{w}_{i = 1} 2^{i-1} \cdot \frac{1}{2^{(i-1) \cdot S}} = \sum^{w-1}_{i=0} \frac{1}{2^{i\cdot (S-1)}}\\
&= \sum^{w-1}_{i=0}\left(\frac{1}{2^{S-1}}\right) < \sum^{\infty}_{i=0}\left(\frac{1}{2^{S-1}}\right) = \frac{1}{1 - \frac{1}{2^{S-1}}} \implies \sum \frac{1}{n^S} \text{Konvergent}
\end{align}$$
