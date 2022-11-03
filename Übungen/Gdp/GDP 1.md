## Aufgabe 1
a)
$$

{{4: Nat\ 5: Nat\over4*5: Nat}\ {17: Nat\ 3: Nat\over 17+3:Bool}\over (4*5) > (17+3): Bool}
$$
$$
{{4\Downarrow4\ 5\Downarrow 5\over4*5\Downarrow20}\ {17\Downarrow17\ 3\Downarrow 3\over 17+3 \Downarrow20}\over (4*5) > (17+3)\Downarrow false}
$$
b) $(5 > 4)> 3$ nicht wohlgetypt, da $5>4:Bool$ und $3:Nat$
c)
$$
{{{{{\over 2: Nat }{\over 6: Nat}\over2+6:Nat}{\over10: Nat}\over(2+6) < 10: Bool} {\over 42: Nat}\ {\over 9:Nat}}\over if (2+6) < 10\ then\ 42 else 9: Nat} 
$$
$$
{{{{{\over 2\Downarrow2 }{\over 6\Downarrow6}\over2+6\Downarrow 8}{\over10\Downarrow10}\over(2+6) < 10\Downarrow true} {\over 42\Downarrow 42}}\over if (2+6) < 10\ then\ 42 else 9\Downarrow42} 
$$
d) $if\ 42\ then\ false\ else\ true$

## Aufgabe 2
a) Es gibt unendlich viele Boolesche Ausdrücke, $n <n+1 \forall n\in N$
b) Es gibt genau zwei Boolesche Werte, nämlich true und false
