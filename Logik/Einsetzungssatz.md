Gegeben drei aussagenlogische Formeln $F, G, H$, sei $F[G/H]$ die Formel $F$, aber mit jedem Vorkommen von $H$ (als eine Teilformel von $F$)
ersetzt durch $G$. Beispielsweise gilt
   $(x \wedge \neg y)[\neg z/x] = (\neg z \wedge \neg y)$.
Wir formalisieren die informelle Definition oben mit einer rekursiven Definition (Sie sollten am Ende des Semesters in der Lage sein, selbst solche formale Definitionen aus einer informalen Definition wie oben, herzuleiten). Für den Fall wenn $F = H$, wir definieren $F[G/H] = G$. Falls 
$F \ne H$,
dann gehen wir rekursiv vor:
- Induktionsanfang:
  - $x[G/H] := x$,   für jede Variable $x$
  - $\top [G/H] := \top$
  - $\bot [G/H] := \bot$

- Induktionsschritt:
  - $(\neg F)[G/H] := \neg F[G/H]$
  - $(F \wedge F')[G/H] := F[G/H] \wedge F'[G/H]$
  - $(F \vee F')[G/H] := F[G/H] \vee F'[G/H]$
  
>[!SATZ] (Einsetzungssatz):
> Falls $G \equiv H$, dann gilt $F[G/H] \equiv F$.

_Beweis_. Wir nehmen $F \ne H$ an, da sonst $F[G/H] = G \equiv H = F$ gilt. Der Beweis ist mit struktureller Induktion über $F$.
- Induktionsansfang: trivial, da $F[G/H] = F$ gilt wenn $F$ im Induktionsanfang oben definiert ist. 
- Induktionsschritt: Wir werden nur den Fall $F = \neg F$' betrachten.  Nach Definition haben wir 
$F[G/H] = \neg F'[G/H]$
  Wir wenden nun die Induktionsvoraussetzung auf $F'$ an und erhalten: $F'[G/H] \equiv F'$.
  D.h., für jede Interpretation $I$ gilt $I \vDash \neg F'[G/H]$
  gdw. $I \vDash \neg F'$. Also, $F[G/H] = \neg F'[G/H] \equiv \neg F' = F$.
$\blacksquare$


