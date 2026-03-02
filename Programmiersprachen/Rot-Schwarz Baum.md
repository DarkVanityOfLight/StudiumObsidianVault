Rot-Schwarz Bäume sind selbst balancierend, dass heißt ihre höhe beträgt immer $\log n$.

Jeder Konten bekommt eine Farbe(rot/schwarz), die wir nur zur Balancierung nutzen.

>[!IMPORTANT] Definition
> Ein Rot-Schwarz Baum ist ein [Binäre Suchbäum](Binäre%20Suchbäume.md), in dem die Schlüssel Knoten rot oder schwarz gefärbt sind, sodass:
> - Die Wurzel ist schwarz gefärbt
> - Für jeden roten Knoten muss der Elternknoten schwarz gefärbt sein
> - Die Schwarztiefe jedes Blattes muss gleich sein.

Die Schwarztiefe von $b$ ist definiert als Anzahl schwarzer Knoten auf dem Pfad von der Wurzel zu $b$. Hierbei sind die virtuellen Blätter immer schwarz gefärbt.


## Einfügen

`insert(e)` füge Schlüssel $k = key(e)$  an die entsprechende Stelle im Baum ein -> Knoten $x$ Färbe $x$ rot.

```perl
while (Rotverletzung bei x) do
	behebeRotverletzung(x)
if (x ist die Wurzel) then
	faerbe x noetigenfalls schwarz
```

## Rotverletzungen

Durch das einfügen haben wir maximal eine Rotverletzung an $x$.

__Fall 1:__ Tankel $t$ ist rot

![tankelrot](tankelrot.png)

Wir färben um:
- Elternknoten und Tankel werden von rot-> schwarz
- Großeltern knoten von schwarz->rot

![tankelnew](tankelnew.png)

Wir setzen $x$ um auf $g$.

1. Nach dem Umfärben kann die einzige Rotverletzung am Großeltern Knoten $g$ von $x$ sein.
- Die Rotverletzung an $x$ ist aufgelöst 
- Eltern und Tankelknoten sind schwarz 
- Nur der rot umgefärbte Großeltern Knoten kann eine neue Rotverletzung erzeugen

2. Wir haben keine Tiefenverletzung erzeugt. 

__Fall 2:__ Tankel $t$ von $x$ ist schwarz, wir unterscheiden zwei Unterfälle:

Fall 2a: $x$ ist eckiges Enkelkind von $g$, das heißt $x$ ist linkes Kind vom rechten Kind von $g$ oder rechtes Kind vom linken Kind von $g$.

Wir rotieren $p$ in entgegengesetzte Richtung zu $x$.

![rotrot](rotrot.png)

Danach landen wir in Fall 2b

Fall 2b: $x$ ist gerades Enkelkind von $g$, das heißt $x$ ist linkes Kind vom rechten Kind von $g$ oder rechtes Kind vom linken Kind von $g$.

Wir rotieren $g$ in entgegengesetzte Richtung zu $p$ und $x$.
Wir färben um Großeltern Knoten $g$ wird rot, Elternknoten $p$ wird schwarz.

![rot2b](rot2b.png)

Die Anwendung von Fall 2b löst die Rotverletzung auf. Wir haben keine Tiefenverletzung eingeführt, da jedes Blatt im Teilbaum an $g$ die gleiche Schwarztiefe behält.

Insert läuft in $O(\log n)$

## Entfernen

Das Grundprinzip ist:

Ohne Bedingung der Annahme müssen wir einen Schlüssel knoten $x$ mit höchstens einem Schlüssel knoten $y$ als Kind löschen.

Wenn $x$ rot ist, können wir dies einfach tun.
Wenn $x$ schwarz ist, entsteht eine Tiefenverletzung!
-> Sobald $y$ an die Stelle von $x$ tritt, haben alle Wurzel-Blatt-Pfade durch $y$ einen schwarzen Knoten zu wenig.
Wir sagen: $y$ benötigt ein Extra-Schwarz.

Die Strategie zur Auflösung von Extra-Schwarz an $y$:
- Wenn $y$ rot ist, färbe $y$ schwarz
- Ansonsten wollen wir möglichst das Extra-Schwarz durch Umfärben an den Eltern abgeben
	-> Fahre Rekursiv mit Elter $p$ als $y$ fort.
- Wenn das nicht möglich ist. Löse das Extra-Schwarz durch bis zu drei Rotationen + Umfärbung auf
- Sonderfall: Wenn $y$ die Wurzel ist, dann löst sich das Extra-Schwarz von alleine auf.


__Fall 1__: Der Geschwister knoten $w$ ist schwarz

Fall 1a: Beide Kinder von $w$ sind schwarz

Wir färben $w$ von schwarz nach rot und schieben das Extra-Schwarz zum Eltern Knoten $p$ von $y$

![entf1a](entf1a.png)

Nach der Umfaerbung hat jeder Wurzel-Blatt-Pfad durch $p$ nicht nur $y$ einen schwarzen Knoten zu wenig.
-> Von nun an benötig $p$ (statt $y$) das Extra-Schwarz

Eine Rotverletzung an $w$ tritt dann auf wenn $p$ rot ist. Dann wird allerdings $p$ im nächsten Schritt schwarz gefärbt.

Fall 1b: Nur das linke Kind von $w$ ist rot

Wir rotieren $w$ in die entgegengesetzte Richtung von $y$
Wir färben $w$ rot und das linke Kind $L$ von $w$ schwarz.

![entf1b](entf1b.png)

Es entsteht keine Rotverletzung und wir verändern keine Schwarztiefe.

Fall 1c: Mindestens das rechte Kind von $w$ ist rot

Wir rotieren $p$ in die Richtung von $y$
Wir vertauschen die Farben von $p$ und $w$ und färben das rechte Kind $R$ von $w$ schwarz.

![entf1c](entf1c.png)

Es entsteht keine Rotverletzung
Alle Blätter im Teilbaum haben danach die gleiche Schwarztiefe.
-> Die Tiefenverletzung ist aufgelöst.

__Fall 2:__ Der Geschwisterknoten $w$ ist rot

Wir rotieren $p$ in die Richtung von $y$ und färben $p$ rot und $w$ schwarz.

![entf2_000](entf2_000.png)

Es entsteht keine Rotverletzung. Wir verändern keine Schwarztiefe und Transformieren die Situation lediglich in den 1. Fall.


## Laufzeiten

| Funktion           | Laufzeit    |
| ------------------ | ----------- |
| `S.find(k)`        | $O(\log n)$ |
| `S.insert(e)`      | $O(\log n)$ |
| `S.remove(k)`      | $O(\log n)$ |
| `S.min()`          | $O(\log n)$ |
| `S.max()`          | $O(\log n)$ |
| `S.successor(k)`   | $O(\log n)$ |
| `S.predecessor(k)` | $O(\log n)$ |





