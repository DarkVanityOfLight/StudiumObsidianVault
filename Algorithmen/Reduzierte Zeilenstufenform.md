Durch folgenden Algorithmus erreichen wir dass $L(l_{i})$ genau in $l_{i}$ vorkommt.

$$\begin{align*}
&\text{while exist $i\not = j$ with $L(l_{i})$ in tail$(l_i)$ with coff c do}\\
&\qquad l_{i}:=l_{i} - c\cdot l_{j} 
\end{align*}$$
