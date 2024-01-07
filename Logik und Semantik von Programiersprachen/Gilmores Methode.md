
__Eingabe__: Eine Formel $\varphi := \forall x_1, \dots x_n \varphi *$ 
__Aufgabe__: Bestimme die [Erfüllbarkeit](Erfüllbarkeit.md) von $\phi$
__Verfahren__: 
Sei $F_1, F_2, \dots$ eine Aufzählung von $E(\varphi)$
$n:= 1$
Solange $F_1 \land \dots \land F_n$ noch erfüllbar ist:
	$n:= n+1$
Return "Unerfüllbar"

Falls die eingegebene Formel unerfüllbar ist, dann gibt Gilmores Methode Unerfüllbar aus. 