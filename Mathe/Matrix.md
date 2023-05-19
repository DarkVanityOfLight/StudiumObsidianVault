Eine $n\times m$ __Matrix__ $A$ ueber $K$ ist eine Tabelle

$$\begin{pmatrix} a_{1,1} & \cdots & a_{1,m} \\ \vdots &&\vdots \\ a_{n,1} &\cdots & a_{n,m}\end{pmatrix} = (a_{i,j})_{\begin{array}{}i = 1, ..., n\\j = 1, ..., m\end{array}}$$
Die Menge $n\times m$-Matrizen bezeichnen wir mit $K^{n\times m}$.
Durch die Matrixmultiplikation
$$\begin{pmatrix}a_{11} & \cdots & a_{1,m} \\ \vdots & & \vdots \\a_{n,1} & \cdots & a_{n,m}\end{pmatrix} \cdot \left(\begin{array}{}x_{1} \\ \vdots \\ x_{m}\end{array}\right) := \begin{pmatrix}\left(\sum\limits^{m}_{j=1} a_{1, j} x_{j}\right) \\ \vdots \\ \left(\sum\limits^{m}_{j=1} a_{n,j} x_{j}\right)\end{pmatrix}$$
ist ein Vektorraumhomomorphismus
$$K^{m} \to K^{n}, x\mapsto A \cdot x$$
gegeben, den wir wieder mit $A$ bezeichnen. Das Bild von $x$ ist also einfach die $x_{j}$-Linearkombination der Spalten $A_{i} \in K^{n}$ von $A = (A_{1} | ... | A_{m})$, d.h.