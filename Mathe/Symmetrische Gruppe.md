Sei $X$ eine beliebige [Menge](Mengen.md). Die Menge der Selbstabildungen von $X$ 
$$S(X) = \lbrace f: X \to X | f \text{ bijektiv }\rbrace$$
zusammen mit der [Komposition](Komposition.md) ist eine [Gruppe](Gruppe.md).
Speziell für $X = \lbrace 1, ..., n\rbrace$
heißt die Menge der __Permutationen__ von $n$ Elementen
$$S_{n} := S(\lbrace1,..., n\rbrace)$$
die __symmetrische Gruppe__. Offenbar gilt
$$|S_{n}| = n \cdot (n-1) \cdot ... \cdot 2 \cdot 1 = n!$$
Für $\sigma \in S_{n}$ schreiben wir auch
$$\sigma = \left(\begin{array}{}
1 & ... & n\\
\sigma(1) &... & \sigma(n)
\end{array}\right)$$
Ein Element von $S_{n}$ heißt Transposition wenn es genau zwei Elemente von $X$ vertauscht.

---

Durch Nummerieren der Ecken können wir die Drehung des Tetraeders mit der Permutation
$$\left(\begin{array}{}1 & 2& 3&4\\1 & 3 & 2 & 4\end{array}\right) \in S_{4}$$ identifizieren.

