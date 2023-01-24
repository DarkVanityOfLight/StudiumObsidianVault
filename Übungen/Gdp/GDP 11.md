## a)
```csharp
let f() = A3 21N 
```
$22N$
## b)
```csharp
let f() = raise (E1 321N)
```
$\boxed{\text{E1}\quad \color{blue}4711N}$
## c)
```csharp
let f() = A1
```

$\boxed{\text{E2}\quad \color{red}{\text{"Harry Hacker"}}}$
## d)
```csharp
let f() = A2 "Lisa" 
```
$815N$
## e)
```csharp
let f() = raise (E2 "Harry")
```
$\boxed{\text{E}}$
## f)

```csharp
let f() = A3 (raise (E2 "Hacker"))
```
$\boxed{\text{E2}\quad \color{red}\text{"Hacker"}}$
