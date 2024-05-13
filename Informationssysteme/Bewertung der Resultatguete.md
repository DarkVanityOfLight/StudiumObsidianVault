


|                      | Relevant            | nicht relevant      |
| -------------------- | ------------------- | ------------------- |
| zurueckgegeben       | true positives(tp)  | false positives(fp) |
| nicht zurueckgegeben | false negatives(fn) | true negatives(tn)  |


## Precision

Precision $P$ ist der Anteil der relevanten Dokumente in den zurueckgegebene Dokumenten

$$P = \frac{tp}{tp+fp}$$

## Recall

Recall $R$ ist der Anteil der relevanten zurückgegebenen Dokumente an allen relevanten Dokumenten

$$R = \frac{tp}{tp+fn}$$


## F-Measure

F-measure kombiniert Precision und Recall

$$F_\beta = \frac{(\beta^2 PR)}{\beta^2 P + R}$$

wobei $\beta$ zwischen Precision und Recall gewichtet werden kann.


## Average Precision

Sei $\lbrace d_1, \dots, d_m \rbrace$ die Menge der relevanten Dokumente der Anfrage $q$
Sei $R_{k}$ die Menge der geordneten Ergebnisse fuer Anfrage von oben bis zum relevanten Ergebnis $d_k$
$$AP(q) = \frac{1}{m} \sum_{d_k\in\lbrace d_1, \dots, d_m} \text{Precision}(R_k)$$

Ist ein relevantes Dokument $d_k$ nicht zurueckgeliefert worden, wird $\text{Precision}(R_k)$ als $0$ angenommen.

## Mean Average Precision

Für eine [Menge](Mengen.md) $Q$ von Anfragen kann die Mean Average Precision berechnet werden
$$MAP(Q) = \frac{1}{|Q|} \sum_{q\in Q} AP(q)$$

## Precision@k

Anwender werden nicht alle Ergebnisse anschauen sondern nur die top 10 oder top 20. Precision@k ist die Precision die in den ersten $k$ Ergebnissen erreicht wird.
