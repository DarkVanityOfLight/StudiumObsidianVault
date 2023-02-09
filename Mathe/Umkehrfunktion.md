Jede [bijektive](Bijektiv.md) [Abbildung](Abbildungen.md) hat eine Umkehrabbildung. Insbesondere hat also jede [injektive](Injektiv.md) [Funktion](Mathe/Funktionen.md) auf ihrem [Bild](Abbildungen.md#Bild) eine Umkehrabbildung, genannt Umkehrfunktion. Ein einfaches Kriterium für [Injektivität](Injektiv.md) erhalten wir für [stetige](Stetigkeit%20und%20Zwischenwertsatz.md) [Funktionen](Mathe/Funktionen.md) auf einem [Intervall](Intervalle.md) durch den Begriff der [Monotonie](Folgen.md#Monotonie).
Eine wesentliche Anwendung der Umkehrfunktion ist die Konstruktion des Logarithmus als Umkehrfunktion der [Exponentialfunktion](Exponentialfunktion.md). Dies erlaubt es uns, die Definition der [Logarithmusfunktion](Logarithmusfunktion.md) über die auf $]0, 2[$ konvergenten [Logarithmusreihe](Logarithmusreihe) auf ganz $]0, \infty[$ auszudehnen. Weiter zeigt dies, dass
$$\exp(\ln(x)) = x$$
für alle $x\in ]0, \infty[$ und 
$$\ln(\exp(x)) = x$$
für alle $x\in\mathbb R$. Das Verhalten der Logarithmusfunktion für große $x$(ebenso wie das der Exponentialfunktion) spielt eine entscheidende Rolle bei Laufzeitabschätzungen in der Informatik.

---

Eine [Funktion](Mathe/Funktionen.md) $f: D\to\mathbb R$ nennen wir
- monoton wachsend $x_{1} < x_{2} \implies f(x_{1}) \le f(x_{2})$
- streng monoton wachsend $x_{1} < x_{2} \implies f(x_{1}) < f(x_{2})$
- monoton fallend $x_{1}> x_{2} \implies f(x_{1}) \ge f(x_{2})$
- streng monoton fallend $x_{1} > x_{2} \implies f(x_{1}) > f(x_{2})$
für alle $x_{i} \in D$.

---

Ist $f: [r, s] \to\mathbb R$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und streng monoton wachsend, dann gibt es eine eindeutige Umkehrfunktion
$$f^{-1}: [f(r), f(s)] \to \mathbb R$$
mit
$$f\circ f^{-1} = id\;\text{und}\; f^{-1} \circ f = id$$
Weiter ist $f^{-1}$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und streng monoton wachsend.

