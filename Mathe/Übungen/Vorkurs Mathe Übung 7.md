## Aufgabe 7.1
$lim_{n \rightarrow \infty}(-1)^n {1\over n^2} = 0$
Sei $\epsilon > 0$ vorgegeben. Wir müssen $n_\epsilon$ bestimmen, so dass
$|(-1)^n {1\over n^2} - 0|<\epsilon$ für alle $n \geq n_\epsilon$

Sei $\epsilon > 0$ beliebig.
$n_\epsilon := \lceil {2\over \epsilon} \rceil$. Dann gilt für alle $n \geq n_\epsilon$
$$(-1)^n {1\over n^2} \leq (-1)^{n_\epsilon} {1 \over n_\epsilon^2} = (-1)^{\lceil {2 \over \epsilon} \rceil} {1 \over \lceil {2 \over \epsilon} \rceil} \leq (-1)^{ {2 \over \epsilon}} {1 \over {2 \over \epsilon} } = (-1)^{\lceil {2 \over \epsilon} \rceil} {\epsilon \over 2} < (-1)^{ {2 \over \epsilon}} \epsilon$$

## Aufgabe 7.2
a
$lim_{n \rightarrow \infty} {5n-7n^2 \over (n+1)^2 - 8n}$

