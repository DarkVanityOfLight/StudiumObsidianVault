
_Eingabe:_ Eine Menge $\Sigma$ von Klauseln
_Ausgabe_: "Erfüllbar" oder "Unerfüllbar"


1. $S:= \Sigma$
2. Solange $\bot \not \in S$
	1.  Wähle zwei [Kollidierende Klauseln](Kollidierende%20Klauseln.md) $C, C' \in \Sigma$
	2. Nach Variablen-Umbenennung, wähle Resolvent $R$ aus
	3. Falls $\forall C'' \in \Sigma : R \not \in Rename(C'')$, dann $S := S\cup \lbrace R\rbrace$
	4. wird $S$ durch $(1)$-$(3)$ nicht geändert, gebe 'sat' aus
3. Gebe 'unsat' aus

Das Verfahren stoppt für erfüllbare $\Sigma$ nicht unbedingt.

## Resolution als ein Fixpunktalgorithmus

Angegeben ist eine Klauselmenge $F$

$$Res(F) := F \cup \lbrace R : R \text{ is a resolvent of } F \rbrace$$
$$Res^0(F) = F$$
$$Res^{n+1}(F) := Res(Res^n(F))$$

$$Res^*(F) := \bigcup_{n\ge0} Res^n(F)$$