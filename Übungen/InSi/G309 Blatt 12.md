
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

### a)

_i)_
__Isolation:__
$t_2$ darf $P_A$ nicht mit alten Daten ohne die Änderungen von $t_1$ commiten.

_ii)_

__Atomicity:__
Keine Daten von $t_1$ dürfen in den Hintergrundspeicher geschrieben werden und der Puffer muss zurückgesetzt werden auf den Zustand vor $t_1$.

_iii)_

__Atomicity:__
Keine Daten von $t_2$ dürfen in den Hintergrundspeicher geschrieben werden und der Puffer muss zurückgesetzt werden auf den Zustand vor $t_2$

_iv)_

__Isolation:__
$t_1$ muss commited haben bevor $t_2$ die Daten liest.

### b)
Es werden drei Seiten in den Puffer geladen.

### c)
Das DBMS braucht UNDO und REDO:
- Wir brauchen UNDO, da es durch steal passieren kann, das eine Seite geschrieben wird, die später nicht geschrieben werden soll.
- Wir brauchen REDO, da es durch $\neg$force passieren kann, das eine Transaktion nach einem Commit aus dem Puffer verschwindet ohne das sie auf der Festplatte geschrieben wurde.

## Aufgabe 2

### a)

![1000](G309%20Blatt%2012%202024-07-14%2016.37.06.excalidraw)

![](G309%20Blatt%2012%202024-07-14%2017.22.19.excalidraw)

Wir sehen der Konfliktgraph hat einen Zyklus, daher gibt es keine Serialisierung der Historie.

### b) 
Dieser Schedule ist durch 2PL entstanden, jedoch nicht durch 2PL, da wir reads zwischen unlocks haben.

## Aufgabe 3

### a)

|                | $H_1$ | $H_2$ | $H_3$ | $H_4$ |
| -------------- | ----- | ----- | ----- | ----- |
| RC             | ✓     | ✕     | ✓     | ✓     |
| ACA            | ✕     | ✕     | ✓     | ✓     |
| ST             | ✕     | ✕     | ✓     | ✓     |
| serialisierbar | ✓     | ✓     | ✓     | ✕     |
| seriell        | ✕     | ✕     | ✓     | ✕     |

### b)

$H_1: t_1, t_2$
$H_2: t_2,t_1$
$H_3: t_2, t_1$

### c)
Betrachten wir die Historie $H_1=r_2(b),r_1(a),w_1(a),r_2(a),c_1,r_2(c),w_2(c),c_2$. In dieser Historie liest Transaktion $t_2$ den Wert von $a$, der von Transaktion $t_1$ geschrieben wurde, bevor $t_1$ commitet. Dies bedeutet, dass $t_2$ von einem ungesicherten (uncommitted) Wert von $a$ liest. Stellen wir uns vor, dass der Wert von $a$, den $t_2$ liest, später von $t_1$ geändert wird, bevor $t_1$ tatsächlich committet. In einem solchen Fall könnte der Wert, den $t_2$ für $c_2$ berechnet, falsch sein, weil $t_2$ mit einem unsicheren Wert von $a$ arbeitet.  Dies verhindert, dass Transaktionen auf ungesicherten Werten basieren und somit möglicherweise falsche oder inkonsistente Ergebnisse produzieren.


## Aufgabe 4

```java
import java.io.BufferedReader;  
import java.io.FileNotFoundException;  
import java.io.FileReader;  
import java.io.IOException;  
import java.util.*;  
import java.util.stream.Collectors;  
  
public class G03_09 {  
  
    /**  
     * @param ops Der eingelesene Schedule  
     * @return Eine serielle Reihenfolge der Transaktionen oder null falls es keine solche gibt  
     */    private static List<Integer> schedule(List<Operation> ops) {  
        Map<Integer, Set<Integer>> graph = new HashMap<>();  
        Set<Integer> transactions = new HashSet<>();  
  
        for (int i = 0; i < ops.size(); i++) {  
            Operation op1 = ops.get(i);  
            transactions.add(op1.transactionID);  
  
            for (int j = i + 1; j < ops.size(); j++) {  
                Operation op2 = ops.get(j);  
  
                if (op1.transactionID != op2.transactionID && op1.objectID == op2.objectID) {  
                    if (op1.isRead && !op2.isRead || !op1.isRead && op2.isRead || !op1.isRead) {  
                        graph.computeIfAbsent(op1.transactionID, k -> new HashSet<>()).add(op2.transactionID);  
                    }  
                }  
            }  
        }  
  
        return topologicalSort(graph, transactions);  
    }  
  
    private static List<Integer> topologicalSort(Map<Integer, Set<Integer>> graph, Set<Integer> transactions) {  
        Map<Integer, Integer> inDegree = new HashMap<>();  
        for (int transaction : transactions) {  
            inDegree.put(transaction, 0);  
        }  
        for (Set<Integer> deps : graph.values()) {  
            for (int dep : deps) {  
                inDegree.put(dep, inDegree.get(dep) + 1);  
            }  
        }  
  
        Queue<Integer> queue = new LinkedList<>();  
        for (Map.Entry<Integer, Integer> entry : inDegree.entrySet()) {  
            if (entry.getValue() == 0) {  
                queue.add(entry.getKey());  
            }  
        }  
  
        List<Integer> result = new ArrayList<>();  
        while (!queue.isEmpty()) {  
            int current = queue.poll();  
            result.add(current);  
            if (graph.containsKey(current)) {  
                for (int neighbor : graph.get(current)) {  
                    inDegree.put(neighbor, inDegree.get(neighbor) - 1);  
                    if (inDegree.get(neighbor) == 0) {  
                        queue.add(neighbor);  
                    }  
                }  
            }  
        }  
  
        if (result.size() != transactions.size()) {  
            return null;  
        }  
        return result;  
    }  
  
  
    private static List<Operation> readOperations(String path) throws FileNotFoundException, IOException {  
        try (var reader = new BufferedReader(new FileReader(path))) {  
            var lines = reader.lines().collect(Collectors.toList());  
            var operations = new ArrayList<Operation>(lines.size());  
            for (String line : lines) {  
                line = line.trim();  
                if (line.isEmpty()) continue;  
                operations.add(Operation.parse(line));  
            }  
            return operations;  
        }  
    }  
  
    public static void main(String[] args) throws Exception {  
        if (args.length != 1) {  
            System.err.println("Must specify input path!");  
            return;  
        }  
        var operations = readOperations(args[0]);  
        var serial = schedule(operations);  
        if (serial != null) {  
            boolean first = true;  
            for (int transaction : serial) {  
                if (first) {  
                    first = false;  
                } else {  
                    System.out.print(" ");  
                }  
                System.out.print(transaction);  
            }  
            System.out.println();  
        }  
    }  
}  
  
class Operation {  
    final boolean isRead;  
    final int transactionID;  
    final int objectID;  
  
    public Operation(boolean isRead, int transactionID, int objectID) {  
        this.isRead = isRead;  
        this.transactionID = transactionID;  
        this.objectID = objectID;  
    }  
  
    public static Operation parse(String line) {  
        String[] data = line.split("\\s");  
        if (data.length != 3) throw new IllegalArgumentException("Invalid number of data items in: \"" + line + "\"");  
        boolean isRead = parseReadWrite(data[0]);  
        int transactionID = Integer.parseInt(data[1]);  
        int objectID = Integer.parseInt(data[2]);  
        return new Operation(isRead, transactionID, objectID);  
    }  
  
    private static boolean parseReadWrite(String input) {  
        switch (input) {  
            case "r":  
            case "R":  
                return true;  
            case "w":  
            case "W":  
                return false;  
            default:  
                throw new IllegalArgumentException("Invalid operation \"" + input + "\"");  
        }  
    }  
}
```