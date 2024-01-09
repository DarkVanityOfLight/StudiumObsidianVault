
_Eingabe:_ Eine Menge $\Sigma$ von Klauseln
_Ausgabe_: "Erfüllbar" oder "Unerfüllbar"


1. $S:= \Sigma$
2. Solange $\bot \not \in S$
	1.  Wähle zwei [Kollidierende Klauseln](Kollidierende%20Klauseln.md) $C, C' \in \Sigma$
	2. Nach Variablen-Umbenennung, wähle Resolvent $R$ aus
	3. Falls $\forall C'' \in \Sigma : R \not \in Rename(C'')$, dann $S := S\cup \lbrace R\rbrace$
	4. wird $