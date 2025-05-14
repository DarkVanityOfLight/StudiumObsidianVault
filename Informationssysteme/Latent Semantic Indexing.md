Ansaetze wie zb. [TFxIDF](TFxIDF.md) keonnen nicht mit Synonymie z.b. Auto und PKW und Polysemie umgehen


## Latent Topic Models

LTMs machen die Annahme, dass Dokumente aus einer kleinen Anzahl von versteckten Konzepten bestehen. Wir betrachten hier Latent Sematic Indexing LSI.

Wir betrachten die SVD zerlegung der $m\times n$ [Term Dokument Matrix](Term%20Dokument%20Matrix.md) $A$

![2024-04-28-130714_561x163_scrot](2024-04-28-130714_561x163_scrot.png)

- $U$ bildet Terme auf Topics ab
- $V$ bildet Dokumente auf Topics ab


## Rang-k Approximation

Man möchte $A$ gar nicht korrekt wiederherstellen sonder Approximieren, durch die Auswahl der wichtigsten Topics.

In den Spalten von $U$ stehen Topics beschrieben durch Terme.

Wir wählen die $k$ grössten Singulärwerte aus $\Sigma$ aus und setzen die übrigen Singulärwerte auf $0$ und entsprechend die dazugehörigen Einträge in $U$ und $V^T$ 