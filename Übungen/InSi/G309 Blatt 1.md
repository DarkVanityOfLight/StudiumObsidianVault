> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

### a)

__Hamming-Editier-Distanz__

|         |
| ------- |
| Oktopus |
| Kaktus_ |
| 1111111 |
$d(\text{Oktopus}, \text{Kaktus}) = 7$

__Längste-Gemeinsame-Teilsequenz-Distanz__


|     |            |            |            |            |            |            |            |
| --- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
|     | -          | K          | a          | k          | t          | u          | s          |
| -   | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ |
| O   | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ | $\epsilon$ |
| k   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | k          | k          | k          |
| t   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | kt         | kt         | kt         |
| o   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | kt         | kt         | kt         |
| p   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | kt         | kt         | kt         |
| u   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | kt         | ktu        | ktu        |
| s   | $\epsilon$ | $\epsilon$ | $\epsilon$ | k          | kt         | ktu        | ktus       |

Längste Teilsequenz: $4$

$$d(\text{Oktopus}, \text{Kaktus}) = \max\lbrace6, 7\rbrace - 4 = 7 - 4 = 3$$

__Levenshtein-Distanz__


|     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     | -   | K   | a   | k   | t   | u   | s   |
| -   | 0   | 1   | 2   | 3   | 4   | 5   | 6   |
| O   | 1   | 1   | 2   | 3   | 4   | 5   | 6   |
| k   | 2   | 2   | 2   | 2   | 3   | 4   | 5   |
| t   | 3   | 3   | 3   | 3   | 2   | 3   | 4   |
| o   | 4   | 4   | 4   | 4   | 3   | 3   | 4   |
| p   | 5   | 5   | 5   | 5   | 4   | 4   | 4   |
| u   | 6   | 6   | 6   | 6   | 5   | 4   | 5   |
| s   | 7   | 7   | 7   | 7   | 6   | 5   | 4   |

### b)

```
Eingabe: Wort N, M mit längen n, m
Erstelle eine n x m Tabelle T

Fülle die erste Zeile und Spalte mit 0

Für jede Zeile i von T:
	Für jede Spalte j der Zeile i:
		let max = Max{T[i-1, j], T[i, j-1], T[i-1, j-1]}
		If N[i, j] = M[i, j]:
			T[i, j] = max + 1
		Else:
			T[i, j] = max

Ausgabe: T[n, m]
```

Laufzeit: $O(n*m)$

Die einzelnen Zellen enthalten jeweils die Optimale lösung für die Teilworte ihres Indexes. Sollten die Beiden Endbuchstaben gleich sein können wir ihn zu unserer Sequenz Hinzufügungen und so um $1$ verlängern. 

## c)

_1._
$k=2$
$$\begin{align}
S(d_1) =& \lbrace\text{Im Sommer}, \text{Sommer ist}, \text{ist es},\\
&\text{es wärmer}, \text{wärmer als},\text{als zuvor}, \text{zuvor im}, \text{im Winter}\rbrace
\end{align}$$
$$\begin{align}
S(d_2) = \lbrace\text{Dieser Sommer}, \text{Sommer ist}, \text{ist wärmer}, \text{wärmer als}, \text{als je}, \text{je zuvor}\rbrace
\end{align}$$
$k=3$

$$\begin{align}
S(d_{1})=& \lbrace\text{Im Sommer ist},\text{Sommer ist es},\text{ist es wärmer},\text{es wärmer als},\text{wärmer als zuvor},\\
&\text{als zuvor im},\text{zuvor im Winter}\rbrace
\end{align}$$

$$\begin{align}
S(d_{2})=\lbrace\text{Dieser Sommer ist},\text{Sommer ist wärmer},\text{ist wärmer als},\text{wärmer als je},\text{als je zuvor}\rbrace
\end{align}$$

_2._

$k=2$


$$|A\cap B| = |\lbrace \text{Sommer ist}, \text{wärmer als} \rbrace| = 2$$

$$\begin{align}
|A\cup B| =& |\lbrace
\text{Im Sommer}, \text{Sommer ist}, \text{ist es},
\text{es wärmer}, \text{wärmer als},\text{als zuvor},\\
&\text{zuvor im}, \text{im Winter}, 
\text{Dieser Sommer}, \text{ist wärmer}, \text{als je}, \text{je zuvor}
\rbrace| \\ =& 12 
\end{align}$$

$$\frac{|A\cup B|}{|A\cap B|} = \frac{2}{12} = \frac{1}{6}$$

$k=3$

$|A\cap B| = |\lbrace\rbrace| = 0$
$$\begin{align}
|A\cup B| =& |\lbrace
\text{Im Sommer ist},\text{Sommer ist es},\text{ist es wärmer},\\
&\text{es wärmer als},\text{wärmer als zuvor},\text{als zuvor im},\text{zuvor im Winter}\\
&\text{Dieser Sommer ist},\text{Sommer ist wärmer},\text{ist wärmer als},\text{wärmer als je},\text{als je zuvor}
\rbrace| \\=& 12
\end{align}$$
$$\frac{|A\cup B|}{|A\cap B|} = \frac{0}{12} = 0$$

_3._

$|A\cap B| = |\lbrace \text{Sommer},\text{ist},\text{wärmer},\text{als},\text{zuvor} \rbrace|$
$|A\cup B| = |\lbrace \text{Im, Sommer, ist, es, wärmer, als, zuvor, im, Winter, Dieser, je} \rbrace|$


$$\frac{|A\cup B|}{|A\cap B|} = \frac{5}{11}$$


Vergleich der Resultate:
$$\frac{5}{11} > \frac{1}{6} > 0$$

## Aufgabe 2

### a)

$$\text{Precision} = \frac{22}{50} = \frac{11}{25}$$
$$\text{Recall} = \frac{22}{90} =\frac{11}{45}$$

$$F_1\text{-measure} = \frac{(1^2 + 1) \frac{11}{25} \cdot \frac{11}{45}}{1^2 \cdot \frac{11}{25} + \frac{11}{45}} = \frac{11}{35}$$

$$\text{Precision@10} = \frac{8}{10} = \frac{4}{5}$$
$$\text{Precision@20} = \frac{12}{20}$$

## b)

$$AP(q) = \frac{1}{10} \cdot \left( \frac{1}{1} + \frac{2}{2} + \frac{3}{5} + \frac{4}{7} + \frac{5}{8} + \frac{6}{10} + \frac{7}{11} \right) = \frac{15501}{30800} \approx 0.503$$


## c)

$$\text{Precision} = \frac{20}{60} = \frac{2}{6} = \frac{1}{3}$$

$$\text{Recall} = \frac{20}{25} = \frac{4}{5}$$

Wir würden die Software nicht einsetzen da viele Dokumente fälschlicher weise als Plagiat eingestuft werden.

## Aufgabe 3

## a)

$$\begin{align}
&idf_3 = \frac{7}{5}\\
&idf_4 = \frac{7}{5}
\end{align}$$

$$\begin{align}
&\text{score}(q, d_1) = 7 \cdot \frac{7}{5} + 2 \cdot \frac{7}{5} = \frac{63}{5}\\
&\text{score}(q, d_2) = 0 + 3 \cdot \frac{7}{5} = \frac{21}{5}\\
&\text{score}(q, d_3) = 2 \cdot \frac{7}{5} + 5 \cdot \frac{7}{5} = \frac{49}{5}\\
&\text{score}(q, d_4) = 3 \cdot \frac{7}{5} + 1\cdot \frac{7}{5} = \frac{28}{5}\\
&\text{score}(q, d_5) = 0 + 3 \cdot \frac{7}{5} = \frac{21}{5}\\
&\text{score}(q, d_6) = 4 \cdot \frac{7}{5} + 0 = \frac{28}{5}\\
&score(q,d_{7})=  2 \cdot \frac{7}{5} + 0 = \frac{14}{5}
\end{align}$$


## b)




$$\begin{align}
&mmr(q, d_2) = 0.5 \cdot \frac{21}{5} - 0.5 \cdot 0.14 = 2.03\\
&mmr(q, d_3) = 0.5 \cdot \frac{49}{5} - 0.5 \cdot 0.52 = 4.64\\
&mmr(q, d_4) = 0.5 \cdot \frac{28}{5} - 0.5 \cdot 0.16 = 2.72\\
&mmr(q, d_5) = 0.5 \cdot \frac{21}{5} - 0.5 \cdot 0.14 = 2.03\\
&mmr(q, d_6) = 0.5 \cdot \frac{28}{5} - 0.5 \cdot 0.18 = 2.71\\
&mmr(q, d_7) = 0.5 \cdot \frac{14}{5} - 0.5 \cdot 0.11 = 1.345\\
\end{align}$$

---

$$\begin{align}
&mmr(q, d_2) = 0.5 \cdot \frac{21}{5} - 0.5 \cdot 0.14 = 2.03\\
&mmr(q, d_4) = 0.5 \cdot \frac{28}{5} - 0.5 \cdot 0.23 = 2.685\\
&mmr(q, d_5) = 0.5 \cdot \frac{21}{5} - 0.5 \cdot 0.14 = 2.03\\
&mmr(q, d_6) = 0.5 \cdot \frac{28}{5} - 0.5 \cdot 0.21 = 2.695\\
&mmr(q, d_7) = 0.5 \cdot \frac{14}{5} - 0.5 \cdot 0.11 = 1.345\\
\end{align}$$

---


$$\begin{align}
&mmr(q, d_1) = 6.5\\
&mmr(q, d_3) = 4.64\\
&mmr(q, d_6) = 2.695
\end{align}$$


## Aufgabe 4

`0.382,0.317,0.532,0.068,0.289,0.524,0.196`

Wir sehen das Dokument 3 von LSI am besten gerankt wurde wobei es bei TF\*IDF es das 2. beste ist, Dokument 1 liegt hier bei uns auf Platz 3. Allem in allem sind die Ergebnisse sich ähnlich, Dokumente mit einem hohen Ranking in TF\*IDF haben auch hier ein besser abgeschnitten, trotzdem gibt es unterschiede im Ranking