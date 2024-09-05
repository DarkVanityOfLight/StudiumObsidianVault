
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1
_a)_
Nehmen wir an es gibt keine Mengenwertigen Attribute, dann ist das Relationsschema in 1NF. Wegen der Relation $AC \to BDE$, ist $AC$ ein Kandidatenschlüssel. Damit ist das Relationsschema in 2NF, da $AC \to BDE$ mithilfe der Dekomposition alle nicht prim Attribute bestimmt.

Wir betrachten Relationen der Art $\alpha \to B$

- $ABE \to C$, $ABE$ ist ein Superschlüssel der Relation
- $BD \to A$, $A$ ist ein Primärattribut.

Also ist unser Schema in 3NF.

Das Schema ist nicht in BCNF, weil
$BD \to A$ weder eine triviale Abhängigkeit ist, noch $BD$ ein Superschlüssel ist.

_b)_
Wir zerlegen unser Schema $R$ nach dem Dekompositionsalgorithmus in
$$
R_1 = \lbrace A, B, D\rbrace\quad R_2 =\lbrace B, C, D, E\rbrace
$$
Da $BD \to A$ gilt ist $BD$ ein Superschlüssel von $R_1$ und damit ist die Zerlegung in BCNF.

_c)_
Die Zerlegung ist nicht Abhängigkeitserhalten, da nur die Relation $BD \to A$ in $R_1$ überprüft werden kann, aber alle anderen Abhängigkeiten nicht lokal in ihrem Schema getestet werden können. 

## Aufgabe 2

Sei $a$ die Positionierungs Zeit, $s$ die Leserate, $p$ die Seitengroesse und $d$ die Anzahl an fortlaufend abgelegten Bytes. Dann ist der Break Even Point gegeben durch

$$\begin{align}
n &= \frac{as+d}{as + p}\\
n &= \frac{0.016s \cdot 153600\frac{KiB}{s} + 1228800 KiB}{0.016s \cdot 153600\frac{KiB}{s} + 16KiB} = 498
\end{align}$$

_b)_


__FIFO:__
1. $A: [A, -, -]$
2. $A: [A, -, -]$
3. $B: [A, B, -]$
4. $C: [A, B, C]$
5. $A: [A, B, C]$
6. $D: [D, B, C]$
7. $A: [D, A, C]$
8. $C: [D, A, C]$
9. $B: [D, A, B]$
10. $C: [C, A, B]$

__LRU:__
1. $A: [A, -, -]$
2. $A: [A, -, -]$
3. $B: [A, B, -]$
4. $C: [A, B, C]$
5. $A: [A, B, C]$
6. $D: [A, D, C]$
7. $A: [A, D, C]$
8. $C: [A, D, C]$
9. $B: [B, D, C]$
10. $C: [B, D, C]$

__Optimal:__
Da $D$ nur einmal Verwendet wird, schreiben wir $D$ nicht in den Puffer:
1. $A: [A, -, -]$
2. $A: [A, -, -]$
3. $B: [A, B, -]$
4. $C: [A, B, C]$
5. $A: [A, B, C]$
6. $D: [A, B, C]$
7. $A: [A, B, C]$
8. $C: [A, B, C]$
9. $B: [B, D, C]$
10. $C: [A, B, C]$

## Aufgabe 3
_a)_
![](Pasted%20image%2020240630214811.png)
![](Pasted%20image%2020240630214830.png)![](Pasted%20image%2020240630214841.png)
![](Pasted%20image%2020240630214858.png)
![](Pasted%20image%2020240630214914.png)
![](Pasted%20image%2020240630214939.png)

_b)_
![](Pasted%20image%2020240630215022.png)
![](Pasted%20image%2020240630215037.png)
![](Pasted%20image%2020240630215044.png)


## Aufgabe 4

```java
import java.io.*;  
import java.nio.file.Paths;  
import java.util.ArrayList;  
import java.util.List;  
  
public class G03_09 {  
    static final int INNER_NODE_TYPE = 0;  
    static final int LEAF_NODE_TYPE = 1;  
  
    public static class Record {  
       int id;  
       String name;  
       int alter;  
  
       Record(int id, String name, int alter) {  
          this.id = id;  
          this.name = name;  
          this.alter = alter;  
       }  
    }  
  
    static Record search(int key, String filePath) throws IOException, RuntimeException {  
       System.out.print(filePath);  
       System.out.print(" ");  
       DataInputStream in = new DataInputStream(new FileInputStream(filePath));  
  
       Record r = null;  
       int typeinfo = in.readInt();  
  
       if (typeinfo == INNER_NODE_TYPE) {  
          List<Integer> keys = new ArrayList<>();  
          List<Integer> references = new ArrayList<>();  
  
          for (int i = 0; i < 4; i++) {  
             references.add(in.readInt());  
             keys.add(in.readInt());  
          }  
  
          references.add(in.readInt());  
  
          int i;  
          for (i = 0; i < keys.size(); i++) {  
             if (key < keys.get(i)) {  
                break;  
             }  
             // Abort at the first entry that doesn't have a key  
             if (keys.get(i) < 0) {  
                break;  
             }  
          }  
  
          int nextPage = references.get(i);  
          String nextPageFilePath = Paths.get(filePath).getParent().resolve(String.valueOf(nextPage)).toString();  
  
          in.close();  
          r = search(key, nextPageFilePath);  
  
       } else if (typeinfo == LEAF_NODE_TYPE) {  
  
  
          for (int i = 0; i < 4; i++) {  
  
             // Pretty stupid but works, in the specification every leaf node has 4 children don't know  
             // why not in the implementation, why not just set key to -1 or smth if there is nothing left?             try {  
                int _ = in.readInt(); // I don't even know what this key is used for  
             } catch (java.io.EOFException _) {  
                return null;  
             }  
  
             int recordKey = in.readInt();  
             String name = in.readUTF();  
             int alter = in.readInt();  
  
             if (recordKey == key) {  
                r = new Record(recordKey, name, alter);  
                break;  
             }  
          }  
  
       } else {  
          in.close();  
          throw new RuntimeException("unbekannter Knotentyp " + typeinfo);  
       }  
  
       in.close();  
       return r;  
    }  
  
    public static void main(String... args) {  
       try {  
          if (args.length != 1) {  
             System.err.println("Bitte Dateiname der Eingabedefinition angeben");  
             return;  
          }  
  
          BufferedReader reader = new BufferedReader(new FileReader(args[0]));  
          String rootFilePath = reader.readLine();  
  
          List<Integer> searchKeys = new ArrayList<>();  
          String line;  
          while ((line = reader.readLine()) != null) {  
             searchKeys.add(Integer.parseInt(line));  
          }  
          reader.close();  
  
          for (int key : searchKeys) {  
             Record result = search(key, rootFilePath);  
             if (result != null) {  
                System.out.println("Gefunden: id=" + result.id + " name=" + result.name + " alter=" + result.alter);  
             } else {  
                System.out.println("Nicht gefunden");  
             }  
          }  
  
       } catch (IOException e) {  
          e.printStackTrace();  
       }  
    }  
}
```

