
Seien $`F`$, $`G`$ und $`H`$ beliebige aussagenlogische Formeln. Dann gelten folgende Äquivalenzen.
  1. **Idempotenz**
     $F \wedge F \equiv F$
  
     $F \vee F \equiv F$
  
  2. **Kommutativität**
     $F \wedge G \equiv G \wedge F$
  
     $F \vee G \equiv G \vee F$
  
  3. **Assoziativität**
     $(F \wedge G) \wedge H \equiv F \wedge (G \wedge H)$
  
     $(F \vee G) \vee H \equiv F \vee (G \vee H)$
  
  4. **Absorption**
     $F \wedge (F \vee G) \equiv F$
  
     $F \vee (F \wedge G) \equiv F$
  
  5. **Distributivität**
     $F \wedge (G \vee H) \equiv (F \wedge G) \vee (F \wedge H)$
  
     $F \vee (G \wedge H) \equiv (F \vee G) \wedge (F \vee H)$
  
  6. **Doppelte Negation**
     $\neg \neg F \equiv F$
  
  7. **De Morgansche Gesetze**
     $\neg (F \wedge G) \equiv \neg F \vee \neg G$
  
     $\neg (F \vee G) \equiv \neg F \wedge \neg G$
  
  8. **Komplementärgesetze**
     $F \wedge \neg F \equiv \bot$
  
     $F \vee \neg F \equiv \top$
  
  9. **Neutralitätsgesetze**
     $F \wedge \top \equiv F$
     $F \vee \bot \equiv F$
  
  10. **Extremalgesetze**
      $F \wedge \bot \equiv \bot$
  
      $F \vee \top \equiv \top$
Alle diese Äquivalenzen können leicht mittels Wahrheitstabellen bewiesen werden.
## Herleitung von äquivalenten Formeln
**Motivation**: Die Größe der Wahrheitstabelle wächst exponentiell mit der Anzahl der Variablen in der Formel. Für Große Formeln kann also die Wahrheitstabelle in der Praxis unfassbar Groß werden.
**Ziel**: leite algebraische Methoden (d.h. Methoden die Formeln symbolisch manipulieren), die die effiziente Konstruktion äquivalenter Formeln ermöglichen, her.
Um die Axiome der Boolschen Algebra oben benutzen zu können, brauchen wir die Möglichkeit, sie auf  anzuwenden. Dies ist korrekt wegen dem folgenden [Einsetzungssatz](Einsetzungssatz.md).