
Der Distance Vector Algorithmus basiert auf der Bellman-Ford(BF) Gleichung:

Sei $D_{x}(y)$ die Kosten des Pfades mit den geringsten Kosten von $x$ nach $y$.
Dann gilt:
$D_{x}(y) = \min_{v}\lbrace c_{x,v} + D_{v}(y)\rbrace$ 

Als Beispiel:
Nehmen wir an das die Nachbarn von $u$, $x, v, w$ und das Ziel $z$:
$D_{v}(z) = 5; D_{w}(z) = 3; D_{x}(z) = 3$ 
dann besagt die Bellman-Ford Gleichung
$D_{u}(z) = \min\lbrace c_{u,v} + D_{v}(z), c_{u,x} + D_{x}(z), c_{u,w} + D_{w}(z)\rbrace = \min\lbrace 2 + 5, 1+ 3, 5 + 3\rbrace = 4$
Der Knoten mit dem kleinsten $(x)$ ist dann der nächste Hop auf dem Pfad mit den Geringsten Kosten nach $z$.

---

Die Schlüsselidee für den Distance Vector Algorithmus ist jetzt das von Zeit zu Zein jeder Knoten seinen eigenen Distance Vector an die Nachbarn schickt.

Wenn $x$ einen neuen DV irgendeines Nachbarn erhält errechnet er seinen eigenen DV neu mithilfe der BF Gleichung. 

Unter echten Bedingungen Konvergiert $D_{x}(y)$ in die Richtung der echten geringsten Kosten $d_{x}(y)$.

Jeder Knoten tut also folgendes:

Warte auf eine aenderung der lokalen Kosten oder eine Nachricht des Nachbarn

Berechne den DV neu mithilfe des erhaltenen DV des Nachbarn. 

Sollte der DV zu irgendeinem Ziel sich verändert haben, schicke das an die Nachbarn


## Good news travels fast
Sollten sich die Link kosten verringern:

$y$ Updated seinen DV und sendet ihn an die Nachbarn
$z$ erhaelt die Nachricht von $y$ und updated seine eigene Tabelle und berechnet die kosten nach $x$ neu und schickt diese an seine Nachbarn
$y$ erhält $z$'s Update und updated seine Tabelle, aber $y$'s kosten ändern sich nicht daher wird keine Nachricht versendet.

## Bad news travels slow

Wenn die Link kosten sich erhöhen kann es zum count-to-infinity Probelm kommen:

$Y$ sieht, dass die direkte Verbindung zu $X$ einen neuen Kostenwert von $60$ hat, aber $Z$ hat mitgeteilt, dass es einen Pfad mit einem Kostenwert von $5$ gibt. Also berechnet $Y$: "Mein neuer Kostenwert für $X$ wird $6$ sein, über $Z$" und benachrichtigt Z über den neuen Kostenwert von $6$ für $X$.

$Z$ erfährt, dass der Pfad zu $X$ über $Y$ einen neuen Kostenwert von 6 hat, also berechnet $Z$: "Mein neuer Kostenwert für $X$ wird 7 sein, über $Y$" und benachrichtigt $Y$ über den neuen Kostenwert von 7 für $X$.

$Y$ erfährt, dass der Pfad zu $X$ über $Z$ einen neuen Kostenwert von $7$ hat, also berechnet $Y$: "Mein neuer Kostenwert für $X$ wird $8$ sein, über $Z$" und benachrichtigt $Z$ über den neuen Kostenwert von $8$ für $X$.

$Z$ erfährt, dass der Pfad zu $X$ über $Y$ einen neuen Kostenwert von $8$ hat, also berechnet $Z$: "Mein neuer Kostenwert für $X$ wird $9$ sein, über $Y$" und benachrichtigt $Y$ über den neuen Kostenwert von $9$ für X.

---
