
## 4-Bit Radix-2 Vergleich

```perl
circuit CMP (? x ,? y ,? lin ,! lout ) {
	nx = NOT ( x) ;
	ls = AND ( n0 ,y );
	nq = XOR (x , y) ;
	eq = NOT ( nq );
	lw = AND ( eq , lin );
	lout = OR (ls , lw );
} 

macro CMP (x ,y , lin ) = ! x & y or (x <-> y ) & lin ;

circuit NatLes ([ N ]bool ?x ,? y ,bool ! ls3 ) {
	ls0 = CMP (x [0] , y [0] ,true) ;
	ls1 = CMP (x [1] , y [1] , ls0 ) ;
	ls2 = CMP (x [2] , y [2] , ls1 ) ;
	ls3 = CMP (x [3] , y [3] , ls2 ) ; 
}
```

![cmp](cmp.png)


## Halbaddierer

Wir Konstruieren einen Schaltkreis mit $x, y$ als Inputs und Outputs $c, s$ sodass $$\langle[c, s]\rangle^\mathbb N_2 = \langle[x]\rangle^\mathbb N_2 + \langle[y]\rangle^\mathbb N_2$$
Also
$s = (x+y) \mod 2$
$c = (x+y) \text{ div } 2$

![ha](ha.png)

## Radix-2 + 1

$$\langle[s_4, s_3, s_2, s_1, s_0]\rangle^\mathbb N_2 = \langle[s_4, s_3, s_2, s_1, s_0]\rangle^\mathbb N_2 +1$$

```perl
circuit HA (? x ,?y ,!c ,! s) {
	s = XOR (x ,y ) ; c = AND (x ,y ) ;
}

circuit NatInc ([4]bool ?x ,[5]bool ! s) {
	(c1 , s0 ) = HA (x0 ,false) ;
	(c2 , s1 ) = HA (x1 , c1 ) ;
	(c3 , s2 ) = HA (x2 , c2 ) ;
	(s3 , s4 ) = HA (x3 , c3 ) ; 
 }
```

![inc](inc.png)

## Full-Adder

Wir Konstruieren einen Schaltkreis mit eingabe $x, y, c_{in}$ und Ausgabe $c_{out}$ sodass:
$$\langle[c_{out}, s]\rangle^\mathbb N _2 = sm = \langle[x]\rangle^\mathbb N_2 + \langle[y]\rangle^\mathbb N_2 + \langle[c_{in}]\rangle^\mathbb N_2$$

![fatt](fatt.png)

Wir sehen
$s = x \oplus \oplus y \oplus c_{in}$
$c_{out} = x \land y \lor c_{in} \land (x \lor y)$

Alternativ können wir mit nur 5 Gattern das selbe erreichen:

![fa](fa.png)

Daraus ergeben sich die Formeln:
$s = (x \oplus y) \oplus c_{in}$ und $c_{out} = x \land y \lor c_{in} \land (x\oplus y)$
Welche Äquivalent zu unseren sind.


## Carry-Ripple für Radix-2

```perl
circuit NatAdd ([4]bool ?x ,? y ,[5]bool s) {
	(s0 , c1 ) = FA ( x [0] , y [0] , cin ) ;
	(s1 , c2 ) = FA ( x [1] , y [1] , c1 );
	(s2 , c3 ) = FA ( x [2] , y [2] , c2 );
	(s3 , s4 ) = FA ( x [3] , y [3] , c3 ); 
}
```

## Carry-Ripple für 2-Komplement

Wir erstellen eine Schaltung sodass für die Eingaben $x, y, c_{in}$ und die Ausgaben $c_{out}, s$, sodass gilt:

$$\langle[c_{out}, s]\rangle^{\mathbb Z}_{2} = sm = \langle[x]\rangle^{\mathbb Z}_{2} + \langle[y]\rangle^{\mathbb Z}_{2} + \langle[c_{in}]\rangle^{\mathbb Z}_{2}$$
also dass

$$\langle[c_{out}, s]\rangle^{\mathbb Z}_{2} = sm = \alpha(x)  + \alpha(y) + c_{in}$$



![fattc](fattc.png)

Wir merken, dass $\alpha(x) = \gamma(x) = -x$ für $B=2$
Aus der Tabelle lesen wir:
$s = x \oplus y \oplus c_in$
$c_{out} = x \land y \lor \not c_{in} \land (x \lor y)$

Daraus ergibt sich
$s = \neg x \oplus \neg y \oplus c_{in}$
$c_{out} = \neg(\neg x \land \neg y \lor c_{in} \land (\neg x \lor \neg y))$

Wir haben also:
$(s, \neg c_{out}) = FA(\neg x, \neg y, c_{in})$

```perl
circuit IntAdd ([4]bool ?x ,? y ,[5]bool s) {
	nx3 = NOT ( x [3]) ; ny3 = NOT ( y [3]) ;
	(s0 , c1 ) = FA ( x [0] , y [0] , cin ) ;
	(s1 , c2 ) = FA ( x [1] , y [1] , c1 );
	(s2 , c3 ) = FA ( x [2] , y [2] , c2 );
	(s3 , c4 ) = FA ( nx3 , ny3 , c3 ) ;
	s4 = NOT ( c4 );
}
```

![cra2](cra2.png)

## Subtraktion von Radix-B

Wir konstruieren einen Schaltkreis mit Eingaben
$x, y, c_{in}$ und den Ausgaben $c_{out}, s$ sodass:
$$\langle[c_{out}, s]\rangle^{\mathbb Z}_{2} = sm = \langle[x]\rangle^{\mathbb N}_{2} - \langle[y]\rangle^{\mathbb N}_{2} + \langle[c_{in}]\rangle^{\mathbb N}_{2}$$

![fst](fst.png)

Aus der Tabelle lesen wir:
$s = x \oplus y \oplus c_{in}$
$c_{out} = \neg x \land y \lor c_{in} \land (\neg x \lor y)$

```perl
circuit FS (?x ,?y ,? cin ,!s ,! cout ) {
	w1 = NOT (x ) ; w2 = XOR (x , y) ;
	s = XOR ( w2 , cin );
	w3 = AND (w1 ,y ) ;
	w4 = OR ( w1 , y) ;
	w5 = AND ( cin , w4 ) ;
	cout = OR ( w3 , w5 ; 
}

circuit NatSub ([4]bool ?x ,? y ,[5]bool s) {
	(s0 , c1 ) = FS ( x [0] , y [0] ,false);
	(s1 , c2 ) = FS ( x [1] , y [1] , c1 );
	(s2 , c3 ) = FS ( x [2] , y [2] , c2 );
	(s3 , s4 ) = FS ( x [3] , y [3] , c3 ); 
}
```

![fs](fs.png)

Wir können die Subtraktion auch per Addition Implementieren:

![fsfa](fsfa.png)

Da gilt:
$s = x \oplus y \oplus c_{in}$
$c_{out} = \neg x \land y \lor c_{in} \land (\neg x \lor y)$

Was Äquivalent ist zu:

$s = x\oplus y \oplus c_{in}$
$c_{out} = \neg(x \land \neg y \lor \neg c_{in} \land (x \lor \neg y))$

Aufgrund des B-Komplements können wir Subtrahieren indem wir das Bit des Subtrahenden flippen, $1$ Addieren(erste $c_{in} = true$) und das letzte Ausgabe bit auch wieder Flippen(overflow)

![fsbyb](fsbyb.png)

![all](all.png)

## Radix-2 Multiplikation

Da wir mit Basis-2 Rechen können wir Partial Produkte als $x_i \land x_j$ Berechen.

Dadurch erhalten wir, dass
$sm = x[i] \cdot y[j] + pin + cin$ so errechnet werden kann:
`dp[i][j] = AND(x[i], y[j])`
`(pp[j][i], cp[j, i]) = FA(dp[i][j], pin, cin)`

```perl
circuit NatMulCRA (
	[ x0 , x1 , x2 ],
	[ y0 ,y1 , y2 ],
	[ w0 ,w9 , w15 , w17 , w19 ,w20 ])
  {
	// compute products of digits
	w2 = AND ( x2 , y0 ) ;
	w1 = AND ( x1 , y0 );
	w0 = AND (x0 , y0 ) ;
	w5 = AND ( x2 , y1 ) ;
	w4 = AND ( x1 , y1 );
	w3 = AND (x0 , y1 ) ;
	w8 = AND ( x2 , y2 ) ;
	w7 = AND ( x1 , y2 );
	w6 = AND (x0 , y2 ) ;
	// add first and second row 
	( w9 , w10 ) = HA (w1 , w3 ) ;
	( w11 , w12 ) = FA ( w2 , w4 , w10 );
	( w13 , w14 ) = HA ( w5 , w12 );
	// add the third row 
	( w15 , w16 ) = HA ( w11 , w6 );
	( w17 , w18 ) = FA ( w13 ,w7 , w16 ) ;
	( w19 , w20 ) = FA ( w14 ,w8 , w18 ) ; 
}
```

![mp](mp.png)

Grüne Gatter sind einfache `AND` Gatter.
Gelbe Gatter sind Halbaddierer mit `AND` Gattern
Blaue Gatter sind Volladdierer mit `AND` Gattern


## 2-Komplement Multiplikation

![bmp](bmp.png)



