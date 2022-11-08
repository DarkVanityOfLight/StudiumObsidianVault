*Weiterführung des Beispiels aus [Baumsprachen](Baumsprachen.md)*

Bei der umgangssprachlichen Beschreibung der Bedeutung arithmetischer Ausdrücke haben wir wenn-dann Aussagen formuliert:
- Wenn $a11$ zu $1$ auswertet, dann wertet $a11+ 815$ zu $816$ aus
- Wenn $a11 + 815$ zu $816$ auswertet, dann wertet $4711 \cdot (a11 +815)$ zu $3844176$ aus.
 
 Wenn-dann Aussagen lassen sich mit Beweisregeln formalisieren.
Beweisregeln:
$$
{ident(a11) \Downarrow 1 \over add(ident(a11), num(815)) \Downarrow 816}
\atop
{
add(ident(a11), num(815))\Downarrow 816 \over 
mul(num(4711), add(ident(a11), num(815))) \Downarrow 3844176
}
$$
---

Beweisregeln können zu Beweisbäumen zusammengesetzt werden.
$$
{{\vdots \over ident(a11) \Downarrow 1} \over {add(ident(a11), num(815)) \Downarrow816}} \over {mul(num(4711), add(ident(a11), num(815))) \Downarrow 3844176}
$$
## Beweisbäume

Ohne Auslassungen:

$$
{{{\over num(4711 \Downarrow 4711)}\ {{{\vdots\over ident(a11) \Downarrow 1}{\over num(815) \Downarrow 815}}\over add (ident (a11), num (815)) \Downarrow 816}}\over mul (num (4711), add (ident (a11), num (815))) \Downarrow 3844176}
$$
---
Die Menge aller Beweisbäume ist induktiv definiert: $P_1, ..., P_n$ Beweisbäume mit den Wurzeln $\phi_1, ..., \phi_n$  und ist
$$
\phi_1 ... \phi_n \over \phi
$$
eine Beweisregel, dann ist

$$P_1 ... P_n \over \phi$$
ein Beweisbaum mit der Wurzel $\phi$.
Ist $P$ ein Beweisbaum mit der Wurzel $\phi$, dann sagt man auch $P$ zeigt oder beweist $\phi$.

## Regelschemata
Die obigen Beweisregeln für die Auswertung arithmetischer Ausdrücke sind sehr speziell; allgemeinere Regeln lassen sich mit Hilfe von Metavariablen formulieren.
$$
{\over num(n) \Downarrow n}
\atop
{e_1 \Downarrow n_1\ e_2 \Downarrow n_2\over add(e_1, e_2)\Downarrow n_1+n_2}\ {e_1 \Downarrow n_1 \ e_2 \Downarrow n_2\over mul(e_1, e_2) \Downarrow n_1 \cdot n_2}
$$

Die erste Regel - ein Axiom - legt fest, dass Konstanten zu sich selbst auswerten. Die beiden anderen Regeln formalisieren, dass sich zunächst beide Teilausdrücke ausgerechnet werden und dass das Ergebnis die Summe bzw. das Produkt der Teilergebnisse ist.

Regeln, die Metavariablen enthalten, heißen Regelschemata.

## Regelinstanzen
Bevor Regelschemata zu Beweisbäumen zusammengesetzt werden können, müssen die Metavariablen erst durch konkrete Konstanten bzw. Ausdrücke ersetzt werden. Für unser laufendes Beispiel benötigen wir:
$$

{{{\over num(4711) \Downarrow4711} {\over num(815) \Downarrow 815}}
\atop
{ident(a11) \Downarrow 1\ num(815) \Downarrow815\over add(ident(a11), num(815)) \Downarrow816}
}
\atop
{num(4711) \Downarrow 4711\ add(ident(a11), num(815)) \Downarrow 816 \over
mul (num (4711), add (ident (a11), num (815))) \Downarrow 3844176
}
$$
Das Ergebnis einer solchen Ersetzung nennt man auch Regelinstanz oder kurz Instanz
Mit diesen Instanzen können wir wieder den Beweisbaum zusammensetzen.