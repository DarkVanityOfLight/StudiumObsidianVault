
Die einzelnen Einträge $q_t$ und $d_t$ für einen Term $t$ im [Vektorraummodell](Vektorraummodell.md) können unterschiedlich berechnet werden.

__Termfrequenz__ $tf_{t, d}$ ist die Anzahl des Auftretens von Term $t$ in Dokument $d$. Allerdings sollte die Termfrequenz gewichtet werden und nicht direkt benutzt werden.

__Dokumentfrequenz__ $df_t$ ist die Anzahl an Dokumenten in denen der Term $t$ auftritt.

__Inverse Dokumentfrequenz__ $idf_t$ ist definiert als $idf_t = \frac{|D|}{df_t}$
wobei $|D|$ die Anzahl an Dokumenten ist.

Das $tf.idf$ Gewicht von Term $t$ in Dokument $d$ ist dann definiert als 
$$tf.idf_{t, d} = tf_{t, d} \times idf_t$$

Beobachtungen $tf.idf_{t, d}$ ist
- groesser falls $t$ oft in $d$ auftritt
- kleiner falls $t$ nicht oft in $d$ auftritt und/oder $t$ in vielen Dokumenten auftritt

Nun koennen wir im Vektorraummodell die einzelnen Komponenten der Vektoren bestimmen:
$$d_t = tf.idf_{t, d}$$
$$q_t = tf.idf_{t, q}$$
Eine einfachere Moeglichkeit die Guete von Dokumenten $d$ zu berechnen ist durch eine einfache Summe der einzelnen $tf.idf$ Werte:
$$\text{score}(q, d) = \sum_{t\in q} tf.idf_{t, d}$$


## Normalisierung, Dämpfung

__Logarithmische Dämpfung__

$$idf_t = \log \frac{|D|}{df_t}$$

verhindert, dass zu sehr exotische Terme zu viel Gewicht erhalten.

__Sub lineare Skalierung__
$$
wf_{t, d} = \begin{cases} 1 + \log tf_{t, d} \qquad \text{falls } tf_{t, d} > 0\\
0 \qquad \text{sonst}
\end{cases}
$$

__Laengennormalisierung und max-tf Normalisierung__

$$rtf_{t, d} = \frac{tf_{t, d}}{\sum_{v\in d} tf_{v, d}}$$

$$
ntf_{t, d} = \frac{tf_{t, d}}{\max_{v \in d} tf_{v, d}}
$$

verhindern, dass sehr lange Dokumente zu sehr favorisiert werden.

