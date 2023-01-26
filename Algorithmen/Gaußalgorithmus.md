
$$\begin{align*}
&\text{forall $i$ do $l_{i}=\frac{1}{LC(l_{i})} \cdot l_i$}\\
&\qquad\text{while exists $i\not = j$ with $L(l_{i)} = L(l_{j})$}\\
&\qquad\qquad l_{j}:= l_{i}- l_i\\
&\qquad\qquad\text{if $l_{i} = 0$ then delete $l_{j}$}\\
&\qquad\qquad\qquad \text{ else $l_{j}:=\frac{1}{LC(l_{j})} \cdot l_{j}$}
\end{align*}$$

Sortieren der $l_{i}$ nach $L(l_{i})$ gibt die Zeilenstufenform
