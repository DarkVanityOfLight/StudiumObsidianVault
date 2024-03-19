
Wenn mehrere Zugriffe auf dieselbe gemeinsame Variable oder dasselbe Objekt im Konflikt stehen und mindestens einer der Zugriffe ein Schreibzugriff ist. Zwei Zugriffe derselben Programmausfuehrung auf dieselbe Variable heissen __Data Race__, wenn sie in Konflikt stehen und nicht durch [Happens-before Ordnung](Happens-before%20Konsistenz.md) $\text{HB}\atop\rightarrow$ geordnet sind.

 Ein Programm heißt adäquat synchronisiert bzw. frei von Data Races gdw. alle sequentiell konsistenten Programmausführungen frei von Data Races sind.