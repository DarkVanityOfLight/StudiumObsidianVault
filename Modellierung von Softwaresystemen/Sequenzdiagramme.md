
Sequenzdiagramme sind die bekanntesten Vertreter von Interaktionsdiagrammen in der UML.

Sie dienen dazu, Kommunikation und Interaktion zwischen mehreren Kommunikationspartner zu modellieren und beruhen auf dem Basiskonzept der Interaktion:

## Interaktion

Eine __Interaktion__ ist das Zusammenspiel von mehreren Kommunikationspartnern.

Typische Beispiele sind, das versenden von Nachrichten, Datenaustausch oder Methodenaufrufe.


---

Sequenzdiagramme beschreiben Interaktionen in zwei Dimensionen:
- Von links nach rechts: Anordnung der Kommunikationspartner als Lebenslinien. Oft wird der Partner, der den Ablauf initiiert, ganz links angegeben.

- Von oben nach unten: Zeitachse

![seq1](seq1.png)


## Kommunikationspartner

Die __Kommunikationspartner__ in einem Sequenzdiagramm werden ähnlich wie in [Objektdiagrammen](Objektdiagramme.md) als Rechtecke notiert.
Manchmal werden die Rechtecke auch weggelassen. Menschliche Partner werden auch durch ein Strichmännchen symbolisiert. Von jedem Kommunikationspartner führt eine gestrichelte Lebenslinie nach unten.

## Ausführungsbalken

__Aktivitaeten__ eines [Kommunikationspartners](#Kommunikationspartner) werden durch sogenannte __Ausführungsbalken__ dargestellt.

![balken](balken.png)

Parallele Taetigkeiten eines Kommunikationspartners werden dabei durch uebereinander liegende Ausführungsbalken beschrieben. Waehrend die Balken __aktive Zeit__ anzeigen, symbolisieren die gestrichelten Linien __passive Zeit__.


## Nachrichten

Die __Nachrichten__ beschreiben die Kommunikationen bzw. Interaktionen der Kommunikationspartner und werden durch Pfeile dargestellt. Eine Nachricht hat einen __Sender__ und einen __Empfänger__. Die Stellen, an denen die Pfeile auf den Lebenslinien auftreffen, nennt man auch __Sendeereignis__ und __Empfangsereignis__.

![nachricht](nachricht.png)

## Synchrone Nachrichten

Bei __synchroner Kommunikation__ warten Sender und Empfänger aufeinander. Der Sender macht erst dann weiter, wenn er weiß, dass der Empfänger die Nachricht erhalten hat. Sie wird durch eine Schwarze ausgefüllte Pfeilspitze dargestellt.

![sync](sync.png)

## Asynchrone Nachrichten

Bei __asynchroner Kommunikation__ wartet der Sender nicht, bis der Empfänger die Nachricht erhalten hat, sondern arbeitet einfach weiter. Die Nachricht wird durch eine einfache Pfeilspitze dargestellt.

![async](async.png)

Bei asynchronen Nachrichten kann es zu einer Zeitverzögerung zwischen Sende- und Empfangsereignis kommen, die durch einen geneigten Pfeil beschrieben wird.

Bei asynchroner Kommunikation kann der Fall eintreten, dass sich Nachrichten überholen oder kreuzen.

---

Es ist möglich, eine Nachricht an sich selbst zu schicken.
![selfmsg](selfmsg.png)
Bei einer synchronen Nachricht sollte man dabei parallele Ausführungsbalken verwenden, da das Sende- und Empfangsereignis parallel stattfinden müssen.

## Antworten

Nachrichten, die als __Antworten__ auf frühere Nachrichten gedacht sind, werden durch gestrichelte Pfeile notiert. Dabei sollte der Name der ursprünglichen Nachricht wiederholt werden.

![antwort](antwort.png)

---

Wir machen uns nun Gedanken über die Reihenfolge der Ereignisse in einem Sequenzdiagramm. Dazu ist es nützlich sich klar zumachen was eine Ordnung ist.

![Halbordnung](Halbordnung.md)

Die Elemente von Sequenzdiagrammen, die nun geordnet werden, sind die Ereignisse, d.h. Sende und Empfangsereignisse.

In den Sequenzdiagrammen, wie wir sie bisher kennengelernt haben, sind die ereignisse immer [total geordnet](Totalordnung.md), nach folgendem Schema:
- Sendeereignis der Nachricht N < Empfangsereignis von N
- Die restlichen Ereignisse sind entsprechend dem zeitlichen Verlauf geordnet.

Die Darstellung echter Parallelitäten ist daher in Sequenzdiagrammen nicht vorgesehen.

## Äquivalenz von Diagrammen

Zwei Sequenzdiagramme sind __äquivalent__, wenn sie die gleichen Ereignisse enthalten und die Reihenfolge der Ereignisse identisch ist.
Dabei können die Diagramme durchaus verschieden gezeichnet sein.


---

Bisher haben wir gesehen, wie man mit einem Sequenzdiagramm einen möglichen Ablauf beschreiben kann. In manchen Fällen möchte man jedoch mehrere(vielleicht sogar alle Abläufe) beschreiben.

Dazu gibt es die Möglichkeit, kombinierte Fragmente zu verwenden, bei denen mehrere Operanden mit Hilfe von Interaktions-Operatoren zusammengesetzt werden. Wir betrachten im Folgenden einige dieser Interaktions-Operatoren.

## Parallelität

Hier sind die Operanden in beliebiger Reihenfolge ausführbar. Die Reihenfolge der Ereignisse in den Operanden muss aber gewahrt werden, ansonsten gibt es keine Bedingungen.

![par](par.png)

Nachrichten, die von einem Operanden in einen anderen laufen, sind nicht zugelassen.

## Schwache Sequenz

Die Reihenfolge der Ereignisse in den Operanden muss wieder gewahrt werden. Außerdem ist die Reihenfolge der Ereignisse auf den Lebenslinien festgelegt.

![seq](seq.png)

---

Bei Interaktions-Operanden ist es außerdem möglich, zusätzliche Ordnungsbeziehungen einzuführen, die ansonsten nicht angedacht sind


![int](int.png)

Weitere Interaktions-Operatoren:
- strict(strikte Sequenz): Die Reihenfolge der Ereignisse wird von oben nach unten strikt eingehalten
- alt(Alternative): entspricht einer if-then-else Anweisung bzw. switch-Anweisung
- opt(Option): optional
- break(Abbruchfragment): Interaktion in Ausnahmefällen
- neg(Negation): beschreibt eine ungültige Nachrichtenreihenfolge
- loop(Schleife): beschreibt die Wiederholung eines Operanden
- critical(kritischer Bereich): als Ganzes durchzufuehrende Sequenz(atomar)
- ignore: Filter für unwichtige Nachrichten
- consider: Filter für wichtige Nachrichten
- assert: unabdingbare Interaktion(muss auf jeden Fall geschehen)

## Gefundene und verlorene Nachrichten

Bei gefundenen und verlorenen Nachrichten werden das Sende bzw. das Empfangsereignis nicht explizit modelliert. Die Nachrichten tauchen quasi aus der Umgebung auf und verschwinden wieder dorthin.

Solche Nachrichten werden benötigt, wenn die entsprechenden Kommunikationspartner nicht mit modelliert werden sollen.

![lostfound](lostfound.png)


## Erzeugung und Dekonstruktion von Objekten

Außerdem kann es passieren, dass Objekte nicht während des ganzen Ablaufs zur Verfügung stehen. Sie können während des Ablaufs dynamisch erzeugt und auch wieder zerstört werden.


Dies erfolgt zumeist durch sogenannte Erzeugungs und Dekonstruktionsnachrichten und wird folgendermaßen dargestellt:

![createdestroy](createdestroy.png)
