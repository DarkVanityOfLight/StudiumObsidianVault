$$\begin{align}
&e::...\\
&\quad |fun(x:t) \to e\\
&\quad |e\; e_1   
\end{align}
$$

$fun(x:t) \to e$ ist eine anonyme Funktion mit dem formalen Parameter x und dem Rumpf e.
Funktionsaurufe werden ebenfalls verallgemeinert: da Funktionen berechnet werden können, verallgemeinert sich $f e_1$ zu $e e_1$.

## [Statische Semantik](Semantik.md#Statische%20Semantik)
$$
\sum, \{x_1 \mapsto t_1\} \vdash e:t_2\over
\sum\vdash (fun(x_1:t_1)\to e) : t_1 \to t_2
$$
$$
\sum\vdash e:t_1 \to t_2\qquad\sum\vdash e_1:t_1\over \sum e e_1:t_2

$$
#prüfungszettel 

## [Dynamische Semantik](Semantik#Dynamische%20Semantik)
Auswertungsregeln:
$$\over \delta \vdash (fun x\to e) \Downarrow \langle\delta, x, e\rangle$$
$$
\delta\vdash\Downarrow\langle\delta', x, e'\rangle \qquad \delta\vdash e_1 \Downarrow v_1 \qquad \delta', \{x_1\mapsto v_1\} \vdash e' \Downarrow v'\over\delta\vdash e e_1 \Downarrow v' 
$$
#prüfungszettel 