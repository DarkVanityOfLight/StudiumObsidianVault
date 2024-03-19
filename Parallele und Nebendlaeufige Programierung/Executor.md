
In großen Systemen gibt es viele Threads, da es eventuell mehr Threads als Prozessoren gibt ist es wichtig, dass die Anzahl an laufenden Threads nicht zu hoch wird.
Es ist gut, wenn sich eine Beschränkung an Threads einfach programmieren und testen lässt, dazu sind Exekutor Objekte hilfreich


## Task vs. Runnable Task

Ein Task ist eine Ausführungseinheit, für die das Betriebssystem oder ein dafür vorgesehenes Objekt die Ablaufplanung durchführt.

Ein Runnable Task ist eine Ausführungseinheit die durch eine _run_ Methode definiert wird.

Jeder Runnable Task ist an einen Thread gekoppelt, die wiederholte Ausführung ist schwierig. Der Executor entkoppelt Runnable Task von dem Thread; die Übergabe von Runnable Tasks an Executor Objekte, das die Ablaufplanung durchführt und die Ausführung der Tasks auslöst