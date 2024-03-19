> Marcel Wirdel, Kilian Lichtner

## Aufgabe 2

_a)_
$$\begin{align}
\gamma_0 =& \langle z:=0; \text{ while } y \le x \text{ do } (z := z+1; x:= x-y), \nu : x \mapsto 17, y \mapsto 5\rangle\\
\gamma_1 =& \langle \text{ while } y \le x \text{ do } (z := z+1; x:= x-y), \nu : x \mapsto 17, y \mapsto 5, z \mapsto 0\rangle\\
\gamma_2 =& \langle \text{if } y \le x\text{ then } (z := z+1; x:=x-y) ;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) \text{ else skip },\\& \nu : x \mapsto 17, y \mapsto 5, z \mapsto 0\rangle\\
\gamma_3 =& \langle  (z := z+1; x:=x-y);\text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 17, y \mapsto 5, z \mapsto 0\rangle\\
\gamma_4 =& \langle  x:=x-y;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 17, y \mapsto 5, z \mapsto 1\rangle\\
\gamma_5 =& \langle \text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 12, y \mapsto 5, z \mapsto 1\rangle\\
\gamma_6 =& \langle\text{if } y \le x\text{ then } (z := z+1; x:=x-y) ;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) \text{ else skip }, \\& \nu : x \mapsto 12, y \mapsto 5, z \mapsto 1\rangle\\
\gamma_7 =& \langle  (z := z+1; x:=x-y);\text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 12, y \mapsto 5, z \mapsto 1\rangle\\
\gamma_7 =& \langle  x:=x-y;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 12, y \mapsto 5, z \mapsto 2\rangle\\
\gamma_8 =& \langle \text{ while } y \le x \text{ do } (z := z+1; x:= x-y),\\& \nu : x \mapsto 7, y \mapsto 5, z \mapsto 2\rangle\\
\gamma_9 =& \langle\text{if } y \le x\text{ then } (z := z+1; x:=x-y) ;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) \text{ else skip }, \\&\nu : x \mapsto 7, y \mapsto 5, z \mapsto 2\rangle\\
\gamma_{10} =& \langle (z := z+1; x:=x-y) ;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) , \\&\nu : x \mapsto 7, y \mapsto 5, z \mapsto 2\rangle\\
\gamma_{11} =& \langle x:=x-y;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) , \\&\nu : x \mapsto 7, y \mapsto 5, z \mapsto 3\rangle\\
\gamma_{12} =& \langle \text{ while } y \le x \text{ do } (z := z+1; x:= x-y) , \\&\nu : x \mapsto 2, y \mapsto 5, z \mapsto 3\rangle\\
\gamma_{13} =& \langle\text{if } y \le x\text{ then } (z := z+1; x:=x-y) ;\text{ while } y \le x \text{ do } (z := z+1; x:= x-y) \text{ else skip }, \\&\nu : x \mapsto 2, y \mapsto 5, z \mapsto 3\rangle\\
\gamma_{14} =& \langle \text{ skip},\nu : x \mapsto 2, y \mapsto 5, z \mapsto 3\rangle\\
\end{align}$$

_b)_
$$s: y\mapsto - 1, x\mapsto 1$$











## Aufgabe 3

Invariante: $\varphi:= (y-a) \cdot x + z = x\cdot y$

$$\begin{align}
\lbrace\varphi \land a \not = y\rbrace z:= z +x; a:= a+1\lbrace\varphi \rbrace\\
\end{align}$$


![|center|110](Übung%2010%202024-01-29%2015.30.59.excalidraw.md)


Komisches Format aber so kann man es besser lesen :3