
```fsharp
//Nr4
//a)
fun(a: Bool) -> fun(b: Nat) -> if a then b+4N else b+5N
//b)
fun(f:Bool->Bool)-> if f true then 4N else 5N
//c)
fun(f:Nat->Nat)-> fun(a: Nat)-> f 3N + a
//d)
fun(a: Bool) -> fun(f:(Nat->Nat))-> f 3N > 2N || a
```

