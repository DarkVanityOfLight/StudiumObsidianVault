
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

__a)__

_i)_

πTitel σErscheinungsjahr = pgp πTitel, Erscheinungsjahr, pgp ← Geburtsjahr+33 (S ⨝ SIN ⨝ F)

---
_ii)_
$$\begin{align}
&\pi_\text{Titel} \sigma_\text{Vorname = 'Jonathan' $\land$ Nachname = 'Frakes'}\\&(\text{S}\bowtie_\text{S.SNR = SIN.SNR}(\text{SIN}\Join_\text{SIN.FNR = F.FNR}\; \text{F}))
\end{align}$$
---
_iii)_

πTitel sigma R.Geburtsjahr > j γ Titel, FNR, R.Geburtsjahr;MAX(S.Geburtsjahr) → j(F ⨝ SIN ⨝ S ⨝F.RID = R.RID R)

---
_iv)_

$$\pi_\text{Vorname, Nachname}(\sigma_\text{count > 1} (\gamma_\text{Vorname, Nachname; count(SNR) $\to$ count}(S)))$$

__b)__

_i)_
$$(\pi_\text{SPNR}(\sigma_\text{Verein} = 'VFL'(spielt))) \cup (\pi_\text{SPNR}(\sigma_\text{Verein} = 'FFC'(spielt)))$$

Dieser Ausdruck gibt die Vereinigung der Spielerinnen beim VFL und FFC zurück. Es liefert also alle Spielerinnen, die bei mindestens einem der Vereine gespielt haben, nicht nur bei beiden. **Falsch.**

---
_ii)_

$$(\pi_\text{SPNR}(\sigma_\text{Verein='VFL'}(spielt))) \cap (\pi_\text{SPNR}(\sigma_\text{Verein='FFC'}(spielt)))$$

Dieser Ausdruck gibt den Durchschnitt der Spielernummern zurück, die sowohl beim VFL als auch beim FFC gespielt haben. **Richtig.**

---
_iii)_

$$\pi_\text{SPNR}(\sigma_\text{Verein='VFL'}(spielt) \cap(\sigma_\text{Verein='FFC'}(spielt))$$

Der Ausdruck berechnet erst den Durchschnitt der Spieler die im VFL und im FFC gespielt haben und Projiziert dann die Spielernummern  **Richtig.**


---

_iv)_
$$(\pi_\text{SPNR}(\sigma_\text{Verein='VFL'} (spielt)))\Join(\pi_\text{SPNR}(\sigma_\text{Verein='FFC'}(spielt)))$$

Dieser Ausdruck gibt alle Spieler zurück die beim VFL und beim FFC spielen ohne Duplikate sollte ein Spieler in beiden Vereinen spielen, **Falsch.**

---
 
_v)_

$$\pi_\text{SPNR}(\sigma_\text{Verein='VFL'}(spielt)) \setminus \pi_\text{SPNR}(\sigma_\text{Verein $\not =$ 'FFC'}(spielt))$$

Dieser Ausdruck gibt die Spielerinnen beim VFL zurück, die nicht in einem anderen Verein als FFC gespielt haben. Es entspricht nicht der Anfrage, die Spielerinnen zu finden, die bei beiden Vereinen gespielt haben. **Falsch.**


## Aufgabe 2

_a)_

_i)_
πWohnung.Strasse, freieZimmer ← Wohnung.Zimmer - ph πWohnung.Strasse, Wohnung.Zimmer, ph←p/2 (Wohnung ⨝(γWohnung.Strasse, Wohnung.Nr; sum(Reisegruppe.Personen)→ p (Wohnung ⨝wohnt_in.Nr = Wohnung.Nr (wohnt_in ⨝wohnt_in.GNR=Reisegruppe.GNR Reisegruppe))))

_ii)_

πName,Strasse,Nr(Reisegruppe⟕(Reisegruppe.GNR=wohnt_in.GNR) wohnt_in)

_b)_

- Eindeutige Zuordnung von Wohnungen und Reisegruppen: Jede Zeile in der Tabelle wohnt_in muss eindeutig eine Wohnung einer Reisegruppe zuordnen, d.h. eine Gruppe darf nicht in mehreren Wohnungen gleichzeitig wohnen und umgekehrt.
- Korrekte und vollständige Daten in den Tabellen: Alle Tabellen (Wohnungen, Reisegruppe, wohnt_in) müssen vollständig und korrekt ausgefüllt sein. 
- Alle Gruppen, die in wohnt_in aufgeführt sind, müssen auch in der Tabelle Reisegruppe vorhanden sein. Jede Wohnung, die in wohnt_in aufgeführt ist, muss auch in der Tabelle Wohnungen existieren.
- Die Attribute Strasse und Nr in der Tabelle Wohnungen bilden einen zusammengesetzten Schlüssel, der jede Wohnung eindeutig identifiziert. 
- GNR muss in der Tabelle Reisegruppe ein eindeutiger Schlüssel sein. 
- Es sollte keine doppelten Einträge in wohnt_in geben, die die gleiche GNR mehrfach verschiedenen Wohnungen zuordnen. 
- Jeder Eintrag in wohnt_in muss auf existierende Werte in den Tabellen Wohnungen und Reisegruppe verweisen. 

## Aufgabe 3

__a)__

_i)_
- Wenn die Relationen $R$ und $S$ Multi-Mengen sind, können durch den Join mehrere Tupel entstehen, die mehrfach vorkommen.
- Bei Mengen gibt es keine Duplikate, jedes Tupel kommt höchstens einmal vor.

Das Ergebnis wird also unterschiedlich sein, wenn die Relationen $R$ und $S$ Duplikate enthalten.

_ii)_

- Funktionen MAX liefern das gleiche Ergebnis unabhängig davon, ob Duplikate vorhanden sind oder nicht. Daher spielt es keine Rolle, ob R eine Menge oder eine Multi-Menge ist.

__b)__

$$\lbrace x | \forall y(\exists z B(y, z))\to \exists y' (A(x, y') \land y = y') \rbrace$$

__c)__
Der natürliche Join ist assoziativ. Das bedeutet:

$$𝑅⋈(𝑆\Join 𝑇)=(𝑅\Join 𝑆)⋈T$$

Der natürliche Join kombiniert Tupel basierend auf gemeinsamen Attributen. Durch die Assoziativität können wir die Reihenfolge der Joins ändern, ohne dass sich das Endergebnis ändert, solange alle Joins über die gleichen Attribute durchgeführt werden.

Der linke Semi-Join ist ebenfalls assoziativ. Das bedeutet:

$$𝑅⋉(𝑆⋉𝑇)=(𝑅⋉𝑆)⋉𝑇$$
- Der linke Semi-Join gibt nur die Tupel aus der linken Relation zurück, die mit mindestens einem Tupel aus der rechten Relation übereinstimmen.
- Die Assoziativität gilt, da der Semi-Join nur Tupel aus der linken Relation filtert und die Reihenfolge der Filterungen keinen Einfluss auf das Endergebnis hat, solange die Bedingungen erfüllt sind.

