
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_a)_

> Welche Produkte (Name), die in Kaiserslautern verkauft wurden, sind dort jetzt nicht mehr vorrätig aber Nachschub ist bereits bestellt? 

$$ans(\text{name}) \leftarrow \text{Produkt}(\text{nr}, \text{name}, \_,\_), \text{Lager}(nr, \text{'Kaiserslautern'}, 0, \text{'Bestellt'})$$

> Welche Produkte (Name) wurden in Dansenberg immer ohne Rabatt (und mindestens einmal), und in Kaiserslautern nur mit Rabatt (und mindestens einmal) verkauft?

Falls Aussagen nicht in Tupel form nicht erlaubt sind:

$$\begin{align}
ans(\text{name}) \leftarrow
&\text{Produkt}(nr, \text{name}, \_, \_),\\
&\text{Verkauf}(\_, nr, \text{'Dansenberg'}, 0),\\
&\neg\text{Verkauf}(\_, nr, \text{'Kaiserslautern'}, 0),
\text{Verkauf}(\_, nr, \text{'Kaiserslautern'}, \_),
\end{align}$$
sonst:

$$\begin{align}
ans(\text{name}) \leftarrow
&\text{Produkt}(nr, \text{name}, \_, \_),\\
&\text{Verkauf}(\_, nr, \text{'Dansenberg'}, 0),\\
&\text{Verkauf}(\_, nr, \text{'Kaiserslautern'}, \text{rabatt}), \text{rabatt} > 0
\end{align}$$

_b)_


Wir suchen den Ort, sodass im Lager an diesem Ort, das Produkt "MongoDB kompakt" den Status "Bestellt" hat, und die Anzahl $> 0$ ist und der Status dieses Produktes nicht "Vorrätig" ist.

Klarer formuliert:
Wir suchen einen Ort an dem "MongoDB kompakt", bestellt und nicht mehr Vorrätig ist.

---

Wir suchen den Namen, Verkaufspreis und den Rabatt, mit dem ein Produkt in dem selben Ort wie die Filiale von "Dossinger" Verkauft wurde und das selbe Produkt in keinem anderen Ort verkauft wurde.

## Aufgabe 2

_a)_

$$\lbrace  
r | \exists k\text{ArtikelAutor}(\_,\text{13.5.2024}, k) \land \text{Autor}(\_, k, r)
\rbrace$$
---

$$\lbrace n | \exists k \text{Autor}(n, k, \_) \land \forall u\text{ArtikelAutor}(u,\_, k)\land \forall w\text{Artikel}(u, \_,\_, w)  \land w \le 750\rbrace$$

_b)_

Jeder Artikel wird eindeutig durch seine überschrift identifiziert. Jeder Autor sollte eindeutig sowohl durch sein Kürzel als auch durch seinen Namen identifiziert werden


## Aufgabe 3

_a)_
$$\begin{align}
\lbrace a.name |\\
&a\in\text{Autoren}() \land\\
&\exists b \in \text{ArtikelAutor}(b.kuerzel = a.kuerzel,\\
&ueberschrift=\text{'Das deutsche Schulsystem gänzlich erklärt'}) \land\\
&\exists c \in \text{Artikel}(c.ueberschrift = b.ueberschrift, c.AnzWorte = 120)\rbrace
\end{align}$$

_b)_

$$\begin{align}
\lbrace a.ueberschrift |\\
&a \in\text{ArtikelAutor}() \land\\
&\exists b\in  \text{ArtikelAutor}(\\
&b.ueberschrift = a.ueberschrift, b.kuerzel \not = a.kuerzel) \land\\
&\neg \exists c \in \text{ArtikelAutor}(\\
&c.ueberschrift = a.ueberschrift,\\
&a.kuerzel \not = c.kuerzel, c.kuerzel \not = b.kuerzel )
\end{align}$$

## Aufgabe 4

_a)_

Konjunktive regelbasierte Anfragen (ohne Negation) sind monoton, weil das Hinzufügen neuer Fakten zu einer Datenbasis die Menge der erfüllten Anfragen nicht verringern kann. Das Hinzufügen neuer Fakten kann die Erfüllung einer Anfrage nicht unterbrechen, sondern nur zusätzliche Erfüllungen ermöglichen. Daher sind konjunktive regelbasierte Anfragen ohne Negation monoton.
"Finde alle Produkte, die nur an einem einzigen Ort vorrätig sind." Wenn ein weiterer Lagerort hinzugefügt wird, könnte ein zuvor gültiges Produkt ungültig werden.

_b)_

- $\lbrace x,z | R(x, 5) \lor R(10, z)\rbrace$ ist unsicher weil wenn eine der Beiden Bedingungen erfüllt ist, jedes andere $R$ die Gleichung erfüllt und andersherum
- $\lbrace y | \exists x \left(\left(R(x, 5, y) \lor R(x, 8, y)\right)\right) \land \neg R(x, 10, y)\rbrace$ ist aus den selben gründen wie 1. unsicher, mit der weiteren Einschränkung das 10 nicht gewählt werden kann
- $\lbrace z | \forall x\exists y(S(z, y) \land y < x) \rbrace$ Nicht sicher, da $x$ in keiner Domäne Quantifiziert wird und deshalb jedes Element sein kann

_c)_

- Welche Schauspieler haben in genau zehn Filmen mitgespielt?
Diese Anfrage kann im Domänenkalkül ausgedrückt werden, dies funktioniert aehnlich zu Aufgabe 3.b

- In wievielen Filmen hat jeder Schauspieler mitgespielt.
Es gibt keine Möglichkeit zu zählen in wievielen Filmen jemand mitgespielt hat.