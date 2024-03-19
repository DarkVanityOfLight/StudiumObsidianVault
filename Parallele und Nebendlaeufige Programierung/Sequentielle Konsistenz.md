
Die Sequentielle Konsistenz beschreibt ein einfaches [Speichermodell](Speichermodell.md). Dabei werden Lese und Schreibzugriffe eines (sequentiellen) Prozesses in der Reihenfolge ausgeführt wie im Code vorgegeben. 

Jede Ausführung des Gesamtprozesses hat dasselbe Resultat wie eine sequentielle Ausführung der Ereignisse



Lese und Schreibereignisse verschiedener Threads können in irgendeiner sequentiellen Reihenfolge ausgeführt werden, es sei denn, dies wird durch Synchronisationsoperationen eingeschränkt.

Schreiboperationen auf gemeinsamen Variablen/Objekten müssen von allen [Prozessen](Prozess.md) in derselben Reihenfolge gesehen werden.


> [!DANGER]
>Java ist nicht sequentiell konsistent.


Sequentielle Konsistenz gibt wenig Spielraum für Codeoptimierungen durch den Compiler bzw. für Laufzeitoptimierungen durch Hardware. 
