Jedes $u \in \mathbb Z\setminus\{-1, 0, 1\}$ hat eine eindeutige Zerlegung von der Form
$$n = \pm p_1^{r_1} \cdot ... \cdot p_3^{r_3}$$mit $p_i$ prim, $p_1 <$
#zuhause

## Beweis
### Existenz: 
Indunktion über $n$
$n= 2$ prim
$n > 2$ nicht prim 
($n = a \cdot b\quad a,b \not = 1$)
$\implies a,b < n$
$\implies a, b$ haben eine [[Primfaktorzerlegung]]

IV:
Kombinieren, Sortieren -> [[Primfaktorzerlegung]] von $a\cdot b = n$

### Eindeutigkeit
Induktion über $n$
$n=2$: wahr
$n> 2$: 
$n = p_1 \cdot ... \cdot p_s = q_1 \cdot ... \cdot q_t$
$p_1 \leq ... \leq p_s \quad q_1 \leq ... \leq q_t$
$p_i$ prim, $q_i$ prim

- Ist $s=1$ oder $t=1 \implies n$ prim
- $s, t \geq 2$
	- $p_1 = q_1 \implies p_2 \cdot ... \cdot p_s = q_2 \cdot ... \cdot q_t< n$
		- nach IV eine eindeutige Zerlegung
	- $p_1 < q_1$
	- $n>\underbrace{p_1 \cdot (p_2 \cdot ... p_s = q_1 \cdot ... \cdot q_t)}_{=: N_1} = \underbrace{(q_1 - p_1)\cdot q_2 \cdot ... q_t}_{:= N_2} \geq 2$
	- $N > \underbrace{N_1 = N_2}_{hat nach IV eine eindeutige Zerlegung} \geq 2$
	- $p_1$ Primfaktor von $n_1$
	- $p_1<q_1 \leq q_2 \leq ... \leq q_t \implies p_1 \not = q_i \forall i$
	- $p_1 + (q_1 - p_1)$ sonst $p_1 / q_q$ wiederspruch $\implies$ $p_q$ kein Primfaktor von $N_2$
	- 
