
Bei BCP wird die [Einheitsresolution](Einheitsresolution.md) iterativ angewendet

![](Boolean%20Constraint%20Propagation.excalidraw.md)

Für eine effiziente Implementierung von BCP brauchen wir zusätzliche Regeln. Nach jeder Anwendung der Unit Resolution mit $\lbrace l\rbrace$:
1. Lösche alle Klauseln mit $l$
2. Lösche alle Vorkommen von $\neg l$ in anderen Klauseln


>[!NOTE] Satz
>Sei $l\land \varphi$ eine Formel in [Konjunktiver Normalform (CNF)](Normalformen%20in%20der%20Aussagenlogik.md#Konjunktive%20Normalform%20(CNF)). Dann ist sie [erfüllbarkeitsäquivalent](Erfüllbarkeitsäquivalent.md) zu $\varphi[\top/l, \bot/\neg l]$

BCP kann in polynomischer Zeit implementiert werden, allerdings haben naive Implementierungen eine quadratische Laufzeit, der Trick ist drei [Wörterbücher](Wörterbücher.md) für die Formel zu verwenden.
