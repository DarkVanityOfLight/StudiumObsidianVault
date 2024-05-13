
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 2

_a)_

Wir können für $n$ Tiere nur eine Diagnose stellen, wir wollen aber lieber für jedes Tier eine eigene Diagnose haben. Außerdem kann jeder Tierarzt nur eine Diagnose stellen.

behandeln: $\text{Tierarzt} \times \text{Diagnose} \times \text{Medikament} \to \text{Tier}$
behandeln: $\text{Diagnose} \times \text{Medikament} \times \text{Tier} \to \text{Tierarzt}$
behandeln: $\text{Medikament} \times \text{Tier} \times \text{Tierarzt} \to \text{Diagnose}$
behandeln: $\text{Tier} \times \text{Tierarzt} \times \text{Diagnose} \to \text{Medikament}$

Es gibt einige Fälle in denen dieses ER Diagramm nicht sinnvoll ist.

_b)_

Chen-Notation:
![Drawing 2024-05-12 12.27.33.excalidraw](Drawing%202024-05-12%2012.27.33.excalidraw.md)

Min/Max-Notation:

![Drawing 2024-05-12 12.19.59.excalidraw](Drawing%202024-05-12%2012.19.59.excalidraw.md)


$1$ Server hostet $10 000$ Partien, $20$ Spieler spielen $1$ Partie, ist eine Valide konstelation in Chen Notation aber nicht in Min/Max Notation.

## Aufgabe 3

![2024-05-12-130829_1303x773_scrot](2024-05-12-130829_1303x773_scrot.png)

## Aufgabe 4

_a)_

- Angestellte: $\lbrace[\underline{\text{PersNr}}, \text{Name}]\rbrace$
- Professoren: $\lbrace[\underline{\text{PersNr}}, \text{Rang}, \text{Raum}]\rbrace$
- Assistenten: $\lbrace[\underline{\text{PersNr}}, \text{Fachgebiet}]\rbrace$

Vorteile: Wenig Datenredundanz(nur PersNr wird doppelt gespeichert)
Nachteile: Name kann nicht direkt gelesen werden sonder muss erst durch die PersNr abgefragt werden


- Angestellte: $\lbrace[\underline{\text{PersNr}}, \text{Name}]\rbrace$
- Professoren: $\lbrace[\underline{\text{PersNr}}, \text{Name}, \text{Rang}, \text{Raum}]\rbrace$
- Assistenten: $\lbrace[\underline{\text{PersNr}}, \text{Name}, \text{Fachgebiet}]\rbrace$

Vorteile: Jeder Eintrag enthält alle Daten, dadurch sind keine weiteren Anfragen nötig

Nachteile: Jeder Eintrag enthält alle Daten, dadurch gibt es eine erhöhte Datenredundanz, da der Name in jedem Eintrag gespeichert ist.

_b)_

Abbildung auf Relationen:
Abteilung: $\lbrace[\underline{\text{ANR}}, \text{AName},\text{Budget} ]\rbrace$
Personal: $\lbrace[ \underline{\text{PNR}}, \text{GebDat}, \text{Name} ]\rbrace$
Manager: $\lbrace[\underline{\text{PNR}}, \text{Titel}]\rbrace$
leitet: $\lbrace[ \underline{\text{PNR}}, \text{ANR} ]\rbrace$
arbeitet in: $\lbrace \text{ANR}, \underline{\text{PNR}} \rbrace$

Zusammengefasst:
Abteilung: $\lbrace[\underline{\text{ANR}}, \text{AName},\text{Budget} ]\rbrace$
Personal: $\lbrace[ \underline{\text{PNR}}, \text{GebDat}, \text{Name}, arbeitetinRolle, arbeitetinANR]\rbrace$
Manager: $\lbrace[\underline{\text{PNR}}, \text{Titel}, leitetANR]\rbrace$


_c)_

Abbildung auf Relationen:
Protokoll: $\lbrace[ \underline{\text{Datum}}, \text{Leitung} ]\rbrace$
TOP: $\lbrace[\underline{\text{Nummer}},\underline{\text{Datum}, } \text{Text}]\rbrace$
Antrag: $\lbrace[\underline{\text{Steller}},\underline{\text{Nummer}}, \underline{\text{Datum}}, \text{Angenommen}]\rbrace$


Zusammengefasst:
Antrag: $\lbrace[\underline{\text{Steller}},\underline{\text{Nummer}}, \underline{\text{Datum}}, \text{Angenommen}, \text{Text}, \text{Leitung}]\rbrace$
