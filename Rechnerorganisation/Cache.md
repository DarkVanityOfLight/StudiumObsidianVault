
Wie können wir wissen ob ein Speicher Wort im Cache ist. 
Wir betrachten $l$ Speicher Level, wobei $\text{Mem}_l$  der [Hauptspeicher](Speicher.md) ist.
$$\text{Mem}_1[0\dots size_1 - 1], \dots, \text{Mem}_l[0\dots size_l - 1]$$ mit $size_1 < size_2 < \dots size_l$.

$adr_k(a_l)$ ist die Adresse eines Speicherwortes $a_l$ im Cache mit dem Level $k$.
Die Definition von $adr_k(a_l)$ ist unterschiedlich für die Verschiedenen Cache Arten

## Direkte Zuweisung

Wir weisen einem einzelnem Wort $adr_k(a_l) := (a_l \mod size_k)$ zu, wir betrachten also die kleinsten Adress Bits.

![dmmw](dmmw.png)

Dabei werden mehre Adressen auf dem Level $k+1$ auf die selbe Adresse auf dem Level $k$ Abgebildet, deshalb Speichern wir neben den Daten auch noch die übrige Adresse auf dem Level $k$. Verwenden wir also $adr_k (a_l) := (a_l \mod size_k)$, dann müssen wir auch noch einen Tag $tag_k(a_l) := (a_l \div size_k)$. Dann ist im Speicher $\text{Mem}_k[i]$, das Speicherwort mit der Adresse $a_l := tag_k[i] \times size_{k} + i$.

Außerdem Speichern wir Flaggen $\text{Valid}_k[0\dots size_k - 1]$. Diese sagt uns ob $\text{Mem}_k[i]$ ist ein Valider Eintrag. Zu beginn sind alle Einträge Falsch.

