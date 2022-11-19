## Syntax
```csharp
type Date = {day: Nat; month: Nat; year:Nat};
type Person = {forename: String; surname: String}
```

## [Abstrakte Syntax](Syntax.md#Abstrakte%20Syntax)
$$\begin{align}
&T \in \text{TypeIdent}\\
&l \in \text{Lab}\\
&d::=...\\
&\quad | \text{type T} = \{l_1:t_1, l_2: t_2\}\\
&\quad | e.l
\end{align}$$


## [Statische Semantik](Semantik.md#Statische%20Semantik)
$\text{type T}= \{l_1:t_1, l_2: t_2\}$


$$\sum \vdash e_1:t_1 \qquad \sum \vdash e_2: t_2 \over
\sum \vdash \{l_1 = e_1; l_2 = e_2\}: T$$
$$
\sum \vdash e: T \over
\sum \vdash e.l_i: t_i
$$
## [Dynamische Semantik](Semantik.md#Dynamische%20Semantik)

$$\begin{align}
&v::= ...\\
&\quad| \{l_1 = v_1; l_2 = v_2\}
\end{align}$$

$$
\delta \vdash e_1 \Downarrow v_1 \qquad \delta \vdash e_2 \Downarrow v_2 \over \delta \vdash \{l_1 = e_1; l_2 = e_2\} \Downarrow \{l_1 = v_1; l_2 = v_2\}
$$
$$\delta\vdash e \Downarrow \{l_1 = v_1; l_2 = v_2\} \over \delta \vdash e.l_1 \Downarrow v_2$$

