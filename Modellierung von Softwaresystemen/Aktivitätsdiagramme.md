Aktivitätsdiagramme sind UML Diagramme, mit denen Ablaufpläne, Reihenfolgen von Aktivitäten, parallele Aktivitäten, und co. modellieren kann.

Sie werden verwendet, um Geschäftsprozesse des Auftraggebers zu modellieren. Sie können aber auch dafür eingesetzt werden um interne Systemprozesse zu beschreiben.

## Aktionen

Eine __Aktion__ wird im Aktivitaetsdiagramm durch ein Rechteck mit abgerundeten Ecken dargestellt.
```mermaid
stateDiagram-v2
	state "Plan erstellen" as s1
```

## Kontrollfluss

Als __Kontrollfluss__ werden die Kanten zwischen Aktionen bezeichnet.

```mermaid
stateDiagram-v2
	state "Bauplatz waehlen" as s1
	state "Architekt suchen" as s2
	state "Plan erstellen" as s3
	s1 --> s2 
	s2 --> s3
 
```

## Signale

__Signale__ werden vom Sender erzeugt und vom Empfänger empfangen. Signale können Daten enthalten.

![](signal.png)

## Objektknoten

__Objektknoten__ beschreiben Speicher für die Übergabe von Objekten bzw. Ressourcen.

![](objk.png)


## Verzweigungs und Verbindungsknoten

__Verzweigungsknoten__ beschreiben eine Verzweigung des Kontrollflusses, wobei aus den möglichen Kontrollflüssen genau einer ausgewählt wird.

```mermaid
stateDiagram-v2
	classDef inv opacity:0.0
	state if_state <<choice>>
	state "Plan einreichen" as s1

	state Invis1
	state Invis2

	class Invis1 inv
	class Invis2 inv

	s1 --> if_state

	if_state --> Invis1 : [nicht angenommen]
	if_state --> Invis2 : [angenommen]

```
Die Ueberwachungsbedingungen, auch genannt guard, die den Kontrollfluss steuern, werden in eckigen Klammern an den ausgehenden Kontrollflüssen notier.

---

__Verbindungsknoten__ führen mehrere alternative Kontrollflüsse zusammen.

```mermaid
stateDiagram-v2
	classDef invisible opacity:0.0
	state mergeState <<choice>>
	state Invis1
	state Invis2
	state Invis3

	class Invis1 invisible
	class Invis2 invisible
	class Invis3 invisible

	Invis1 --> mergeState
	Invis2 --> mergeState
	mergeState --> Invis3
```
Es gibt auch Knoten, die sowohl Verzweigungs- als auch Verbindungsknoten sind, d.h mehrere eingehende und mehrere ausgehende Kontrollflüsse haben.

## Gabelungen

Eine __Gabelung__, teilt einen Kontrollfluss in mehrere parallele Kontrollflüsse auf.

```mermaid
stateDiagram-v2
	state fork_state <<fork>>
	classDef invisible opacity:0.0
	state Invis1
	state Invis2
	state Invis3

	class Invis1 invisible
	class Invis2 invisible
	class Invis3 invisible

	Invis1 --> fork_state
	fork_state --> Invis2
	fork_state --> Invis3
```


## Vereinigungen

Analog zu [Gabelungen](Aktivitätsdiagramme.md#Gabelungen) gibt es die __Vereinigung__, die mehrere parallele Kontrollflüsse zusammenfasst.

```mermaid
stateDiagram-v2
	state fork_state <<fork>>
	classDef invisible opacity:0.0
	state Invis1
	state Invis2
	state Invis3

	class Invis1 invisible
	class Invis2 invisible
	class Invis3 invisible

	Invis1 --> fork_state
	Invis2 --> fork_state
	fork_state --> Invis3
```

---

> Kontrollflüsse dürfen nur an [Objektknoten](#Objektknoten), [Entscheidungsknoten](#Entscheidungsknoten), [Gabelungen](#Gabelungen) aufgespalten
> und an [Objektknoten](#Objektknoten), [Verbindungsknoten](#Verzweigungs%20und%20Verbindungsknoten) und [Vereinigungen](#Vereinigungen) wieder zusammengeführt werden.



## Start und Endknoten

Ein __Startknoten__ modelliert den Beginn eines Kontrollflusses. Ein Aktivitätsdiagramm, kann mehrere Startknoten haben, die dann mehrerer parallel laufende Kontrollflüsse starten(entspricht einem Startknoten gefolgt von einer Gabelung). In einen Startknoten dürfen keine Kontrollflüsse hineinführen.

```mermaid
stateDiagram-v2
	classDef invisible opacity:0.0
	state Invis1
 
	class Invis1 invisible

	[*] --> Invis1

```

---

Das __Aktivitätsende__ signalisiert, dass die Aktivität, also sämtliche Kontrollflüsse, beendet werden.

```mermaid
stateDiagram-v2
	classDef invisible opacity:0.0
	state Invis1
 
	class Invis1 invisible

	Invis1 --> [*]
```

Es gibt auch ein Symbol für das __Flussende__, das nur den eingehenden Kontrollfluss beendet. Die restliche Aktivität, also andere Kontrollflüsse, laufen weiter.

![](flussende.png)

Beide dieser Elemente dürfen mehrfach in einem Diagramm vorkommen.

## Aktivitätsbereiche

__Aktivitätsbereiche__ fassen mehrere Knoten(Aktionen, Objektknoten, etc.) zu einer Einheit zusammen. Das dient allgemein dazu, um die Verantwortung für bestimmte Aktionen festzulegen.

```mermaid
stateDiagram-v2
	state Gast{
		direction LR
		state "Gericht bestellen" as s1
		state "Gericht verspeisen" as s2
	}

	state Kellner {
		direction LR
		state "Bestellung aufnemehn" as s3
		state "Gericht servieren" as s4
	}

	s1 --> s3
	s3 --> s4
	s4 --> s2
```


## Parameter und Parametersätze 

__Parametersaetze__ legen fest, dass an allen __Pins__ Daten anliegen müssen, um die Verarbeitung durchführen zu können.

![](param.png)

## Unterbrechungsbereiche

Der __Unterbrechungsbereich__ wird genau dann verlassen, wenn die Unterbrechung auftritt. Alle Aktionen im Unterbrechungsbereich werden beendet. Die Verarbeitung wird mit dem Zielknoten der Unterbrechungskante fortgesetzt.

![](unterbrechung.png)

## Mengenverarbeitungsbereich

In __Mengenverarbeitungsbereichen__ werden Sammlungen (z.B. Felder oder Kollektionen) in ihre einzelnen Elemente aufgelöst. Diese werden anschließend einzeln verarbeitet und nach der Verarbeitung wieder zur Sammlung zusammengesetzt.

![](mengen.png)

## Schleifenknoten

__Schleifenknoten__ dienen zur wiederholten Ausführung von Schritten. Der for-Bereich dient der Initialisierung. Der while-Bereich entscheidet, ob der do-Bereich ausgeführt wird. Der while-Bereich kann entfallen(stets "true" -> Endlosschleife). Dann Abbruch durch Unterbrechungskante.

![](schleife.png)

## Entscheidungsknoten

![](if.png)

---

![](activity.png)