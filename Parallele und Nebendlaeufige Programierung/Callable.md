
Wenn wir wollen das die Ausführung eines [Threads](Thread.md) ein Ergebnis zurück gibt implementieren wir das `Callable<V>` Interface.

Dazu gibt es die Klasse `Future<V>`, dieses Objekt existiert noch nicht wenn der Auftrag erteilt wird, da der Auftrag nebenlaeufig zu dem Thread sein kann, der Ergebnisse verwenden will, muss dies klar definiert werden.

`Future<V>` ist ein Interface, das hier in Kombination mit `Callable` genutzt wird und folgende Methodensignatur anbietet:


- `isDone()`: ist die Ausführung beendet? (erfolgreich oder nicht)
- `get()/get(long timeout, Timeunit unit)`: Ergebnis wird nach Warten zurückgeliefert (wahlweise mit timeout)
- `cancel(boolean mayInterruptWhenRunning)`: Auftrag abbrechen (falls boolean falsch nur dann, wenn der Auftrag noch nicht begonnen wurde)
- `isCancelled()`: ist die Ausführung abgebrochen?

