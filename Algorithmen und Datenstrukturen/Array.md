
![arr](arr.png)

Auf ein Array $A$ der Groesse $n$ können wir wie folgt zugreifen:

__Auswertung__: 
Gegeben $1\leq i \leq n$, gib das $i$-te Element zurück
- $A[i]$
- $A.get(i)$

Laufzeit: $O(1)$

__Zuweisung__: 
Gegeben $1\leq i \leq n$ und $x$ setze das $i$-te Element auf $x$
- $A[i] = x$
- $A.set(i, x)$
Laufzeit $O(1)$

__Initialisierung__:

Den Speicherbereich für eine Array zu reservieren ist in konstanter Zeit möglich.

>[!ATTENTION] Achtung
> Ohne besondere Initialisierung können wir keine Annahmen über den Inhalt machen!




