## Aufgabe 1
$(a_n + b_n)$ auch CF
$$a_n: CF \implies \forall \varepsilon > 0 \exists N_a \in\mathbb N\forall n, m \ge N_a |a_n - a_m| < \varepsilon$$
Sei $\varepsilon > 0$ fest, beliebig $|a_n - a_m| < \frac{\varepsilon}{2} \forall n, m \ge N_a$
$\exists N_b \in \mathbb N \quad |b_n - b_m| < \frac{\varepsilon}{2} \quad \forall n, m \ge N_b$
$\forall n, m \geq N$ Setze $N:= max\{N_a, N_b\}$ 
$\implies |a_n + b_n| - |a_m + b_m| = |a_n - a_m + b_n -b_m| \leq |a_n - a_m| + |b_n -b_m| < \frac{\varepsilon}{2}\frac{\varepsilon}{2} = \varepsilon$


## Aufgabe 2

### a)
Angenommen so ein $C$ existiert nicht

Sei $\varepsilon > 0$ bel. $(a_n)_n\quad CF \implies \exists N \in\mathbb N \forall n, m \ge N \quad |a_n - a_m| < \frac{\varepsilon}{2})$
Nach Ann. existiert mindestens ein $m \in \mathbb N$ sodass für $C := \min\{\frac{\varepsilon}{2},  |a_1|, ..., |a_{n-1}|\} \quad |a_m < C|$

$\implies |a_n| = |a_n -a_m + a_n| \leq |a_n -a_m| + |a_m| < \frac{\varepsilon}{2} + C \leq \frac{\varepsilon}{2} + \frac{varepsilon}{2}  = \varepsilon \implies \lim_{n \to \infty}a_n = 0$ Widerspruch

### b)
$(\frac{1}{a_n})$ CF

Aus a) $\exists C > 0$ sodass $|a_n| \geq C \quad\forall n \in \mathbb N$

Sei $\varepsilon > 0$ beliebig $a_n CF \implies \exists N\in\mathbb N \quad\forall n, m \ge N: |a_n - a_m| < \varepsilon \cdot C^2$

$|\frac{1}{a_n} - \frac{1}{a_m}| = \frac{1}{|a_n| - |a_m|} \cdot |a_n - a_m| < \frac{1}{C^2} \cdot \varepsilon \cdot C^2 = \varepsilon$


