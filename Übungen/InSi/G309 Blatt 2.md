
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1
__a)__
$$\begin{pmatrix} 0&1&0&0&0&0\\0&0&1/2&1/2&0&0 \\ 0&1&0&0&0&0 \\ 1/6&1/6&1/6&1/6&1/6&1/6 \\ 0&1&0&0&0&0 \\ 0&1/2&0&1/2&0&0 \end{pmatrix}$$

$$\begin{align}
&P = (1 - \epsilon) T + \epsilon \left(\begin{matrix}
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\end{matrix}\right)\\
&P = (1-0.1) T + 0.1 \cdot \left(\begin{matrix}
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} \\
\end{matrix}\right)\\
\end{align}$$


Mithilfe der Power Iteration erhalten wir $\begin{bmatrix} 0.04166667 \\ 0.5666667 \\ 0.1166667 \\ 0.1916667 \\ 0.04166667 \\0.04166667\end{bmatrix}$

Als Abbruchkriterium wählen wir eine Änderungsrate $\leq 0.001$.
Die einzelnen Werte beschreiben die Wahrscheinlichkeit das ein User nach $k$(Anzahl an Iterationen) Schritten auf dieser Website landet, entweder durch das folgen von links oder durch eingeben des links in die Adresszeile.

__b)__

Links die in einem Loop beteiligt sind, werden weniger Gewichtung zugerechnet. Das finden von Loops benötigt viel Rechenaufwand und Webseiten die wirklich aufeinander verweisen werden auch betroffen.

## Aufgabe 2
__a)__

![apriori.excalidraw|1000](apriori.excalidraw.md)

__b)__
$F = \lbrace \lbrace a\rbrace, \lbrace b\rbrace, \lbrace c\rbrace, \lbrace d\rbrace, \lbrace a, b\rbrace, \lbrace b, c\rbrace\rbrace$


$Z = \lbrace a, b\rbrace$


$A^{(0)} = \lbrace \lbrace a\rbrace, \lbrace b\rbrace\rbrace$
$X = \lbrace a\rbrace$
$c = \frac{2}{3}$
_Ausgabe:_ $\lbrace a\rbrace \to \lbrace b\rbrace, 2, \frac{2}{3}$

$A^{(1)} = \lbrace\lbrace b \rbrace\rbrace$
$X = b$
$c = \frac{2}{4}$
_Ausgabe:_ $\lbrace b\rbrace\to \lbrace a\rbrace, 2, \frac{2}{4}$

---

$Z = \lbrace b, c\rbrace$

$A^{(0)} = \lbrace \lbrace b\rbrace, \lbrace c\rbrace\rbrace$
$X = {b}$
$c = \frac{3}{4}$
_Ausgabe:_ $\lbrace b\rbrace \to \lbrace c\rbrace, 3, \frac{3}{4}$

$A^{(1)} = \lbrace \lbrace c\rbrace\rbrace$
$X = {c}$
$c = \frac{3}{3}$
_Ausgabe:_ $\lbrace c\rbrace \to \lbrace b\rbrace, 3, \frac{3}{3}$

## Aufgabe 4

`

__a)__

$$\begin{align}
|o_{3}-o_{1}|=|0.8-0.4|=0.4\\
|o_{3}-o_{2}|=|0.8-0.5|=0.3\\
|o_{3}-o_{4}|=|0.8-1.4|=0.6\\
|o_{3}-o_{5}|=|0.8-2.9|=2.1\\
\end{align}$$
Da $|o_{3}-o_{5}|$ größer ist als $\frac{|o_{3}-o_{6}|}{2}$ gehört das Element $o_5$ nicht mehr zum Cluster mit dem Centroid $o_3$
 
$$\begin{align}
|o_{6}-o_{5}|=|3.4-2.9|=0.5\\
|o_{6}-o_{7}|=|3.4-5.4|=2.0\\
|o_{6}-o_{8}|=|3.4-5.7|=2.3\\
|o_{6}-o_{9}|=|3.4-6.7|=3.3\\
|o_{6}-o_{10}|=|3.4-7.6|=4.2\\
\end{align}$$
$C_{1}=\lbrace o_{1},o_{2},o_3,o_{4}\rbrace$ 
$C_{2}=\lbrace o_5,o_6,o_7,o_8,o_9,o_{10}\rbrace$

Der neue Centroid von $C_1$ ist bei $c_1=0.8$ und der neue Centroid von $C_2$ ist bei $c_2=5.3$
$$\begin{align}
|c_{1}-o_{1}|=|0.8-0.4|=0.4\\
|c_{1}-o_{2}|=|0.8-0.5|=0.3\\
|c_{1}-o_{3}|=|0.8-0.8|=0\\
|c_{1}-o_{4}|=|0.8-1.4|=0.6\\
|c_{1}-o_{5}|=|0.8-2.9|=2.1\\
\end{align}$$
Da $|c_{1}-o_{5}|$ kleiner ist als $\frac{|c_{1}-c_{2}|}{2}$ gehört das Element $o_5$ noch zum Cluster mit dem Centroid $c_1$
$$\begin{align}
|c_{2}-o_{5}|=|5.3-2.9|=2.4\\
|c_{2}-o_{6}|=|5.3-3.4|=1.9\\
|c_{2}-o_{7}|=|5.3-5.4|=0.1\\
|c_{2}-o_{8}|=|5.3-5.7|=0.4\\
|c_{2}-o_{9}|=|5.3-6.7|=1.4\\
|c_{2}-o_{10}|=|5.3-7.6|=2.3\\
\end{align}$$
$C_{1}=\lbrace o_{1},o_{2},o_3,o_{4},o_5\rbrace$ 
$C_{2}=\lbrace o_6,o_7,o_8,o_9,o_{10}\rbrace$

Der neue Centroid von $C_1$ ist bei $c_1=1.2$ und der neue Centroid von $C_2$ ist bei $c_2=5.8$
$$\begin{align}
|c_{1}-o_{1}|=|1.2-0.4|=0.8\\
|c_{1}-o_{2}|=|1.2-0.5|=0.7\\
|c_{1}-o_{3}|=|1.2-0.8|=0.4\\
|c_{1}-o_{4}|=|1.2-1.4|=0.2\\
|c_{1}-o_{5}|=|1.2-2.9|=1.7\\
|c_{1}-o_{6}|=|1.2-3.4|=2.2\\
\end{align}$$
Da $|c_{1}-o_{6}|$ kleiner ist als $\frac{|c_{1}-c_{2}|}{2}$ gehört das Element $o_6$ noch zum Cluster mit dem Centroid $c_1$
$$\begin{align}
|c_{2}-o_{6}|=|5.8-3.4|=2.4\\
|c_{2}-o_{7}|=|5.8-5.4|=0.4\\
|c_{2}-o_{8}|=|5.8-5.7|=0.1\\
|c_{2}-o_{9}|=|5.8-6.7|=0.9\\
|c_{2}-o_{10}|=|5.8-7.6|=1.8\\
\end{align}$$
$C_{1}=\lbrace o_{1},o_{2},o_3,o_{4},o_5,o_6\rbrace$ 
$C_{2}=\lbrace o_7,o_8,o_9,o_{10}\rbrace$

Der neue Centroid von $C_1$ ist bei $c_1=1.6$ und der neue Centroid von $C_2$ ist bei $c_2=6.4$
$$\begin{align}
|c_{1}-o_{1}|=|1.6-0.4|=1.2\\
|c_{1}-o_{2}|=|1.6-0.5|=1.1\\
|c_{1}-o_{3}|=|1.6-0.8|=0.8\\
|c_{1}-o_{4}|=|1.6-1.4|=0.2\\
|c_{1}-o_{5}|=|1.6-2.9|=1.3\\
|c_{1}-o_{6}|=|1.6-3.4|=1.8\\
|c_{1}-o_{7}|=|1.6-5.4|=3.8\\
\end{align}$$
Da $|c_{1}-o_{7}|$ größer ist als $\frac{|c_{1}-c_{2}|}{2}$ gehört das Element $o_7$ nicht mehr zum Cluster mit dem Centroid $c_1$
$$\begin{align}
|c_{2}-o_{7}|=|6.4-5.4|=1.0\\
|c_{2}-o_{8}|=|6.4-5.7|=0.7\\
|c_{2}-o_{9}|=|6.4-6.7|=0.3\\
|c_{2}-o_{10}|=|6.4-7.6|=1.2\\
\end{align}$$
$C_{1}=\lbrace o_{1},o_{2},o_3,o_{4},o_5,o_6\rbrace$ 
$C_{2}=\lbrace o_7,o_8,o_9,o_{10}\rbrace$
Der Algorithmus ist fertig da sich am Cluster nicht mehr verändert

__b)__
$$\begin{align}
|c_{1}-o_{1}|=|1.6-0.4|=1.2\qquad 1.2^2=1.44\\
|c_{1}-o_{2}|=|1.6-0.5|=1.1\qquad 1.1^2=1.21\\
|c_{1}-o_{3}|=|1.6-0.8|=0.8\qquad 0.8^2=0.64\\
|c_{1}-o_{4}|=|1.6-1.4|=0.2\qquad 0.2^2=0.04\\
|c_{1}-o_{5}|=|1.6-2.9|=1.3\qquad 1.3^2=1.69\\
|c_{1}-o_{6}|=|1.6-3.4|=1.8\qquad 1.8^2=3.24\\
|c_{2}-o_{7}|=|6.4-5.4|=1.0\qquad 1.0^2=1.0\\
|c_{2}-o_{8}|=|6.4-5.7|=0.7\qquad 0.7^2=0.49\\
|c_{2}-o_{9}|=|6.4-6.7|=0.3\qquad 0.3^2=0.09\\
|c_{2}-o_{10}|=|6.4-7.6|=1.2\qquad 1.2^2=1.44\\
\end{align}$$

