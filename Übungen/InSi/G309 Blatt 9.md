
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

__a)__

- $\lbrace \text{SachbearbeiterID}, \text{KundeID}, \text{Timestamp} \rbrace \to \text{Nachricht}$
- $\lbrace \text{SachbearbeiterID}, \text{KundeID}, \text{Timestamp} \rbrace \to \text{Richtung}$

Die FDs basieren auf der Annahme, dass jede Nachricht zu einem bestimmten Zeitpunkt zwischen einem spezifischen Sachbearbeiter und einem Kunden eindeutig ist und sowohl die Nachricht als auch die Richtung eindeutig bestimmt werden können.


__b)__

_i)_ Die Zerlegung ist nicht verlustlos, da bei einem Join potentiell mehrere Timestamps von verschiedenen (SachbearbeiterID, KundenID) Tupeln miteinander gejoint werden, sollten also in zwei verschiedenen Chats zwei Nachrichten zum gleichen Zeitpunkt verschickt werden, so tauchen diese Nachrichten nach einem Join in beiden Chats auf.

_ii)_ Die Zerlegung ist nicht abhängigkeitserhaltend, da nach der Zerlegung die Antecedent und die Konsequente in zwei verschieden Tabellen geteilt werden.

## Aufgabe 2

__a)__

Schritt $1$ berechnet die Kanonische überdeckung, das heißt aus allen folgenden FDs können die ursprünglichen FDs wieder hergestellt werden, es reicht dementsprechend die Verlustlosigkeit und Abhängigkeitserhaltung im Bezug zu den FDs in $F_c$ zu zeigen.

- _Verlustlosigkeit_: In Schritt $3$ wird sichergestellt das ein Kandidatenschlüssel bezüglich $F_c$ existiert, dadurch gilt bei einem Join auf diesem Schlüssel per Definition, das jeder Partner eindeutig zugeordnet werden kann.
- _Abhängigkeitserhaltung_: Im zweiten Schritt wird für jede FD sichergestellt, das das Relationsscheme $R_\alpha$ sowohl die Antecedente $\alpha$ als auch die Konsequente $\beta$ enthält, damit bleibt jede FD immer erhalten.

__b)__
Sei $R_\alpha$ das Relationschema für $\alpha\to\beta \in F_c$. Wir wählen $\alpha$ als Primärschlüssel für $R_\alpha$
Wir wählen FDs der Art $\alpha'\to\beta'\in F_c$ mit $\alpha'\cup \beta' \subseteq \alpha \cup \beta$.
für die 3NF Betrachten wir FDs der Art
Sei $B\not\in \alpha$ und $\alpha \not =B$, sonst gelten Bedingungen 1, 3. Dann gilt nach der kanonischen Überdeckung, das $\alpha' \supseteq \alpha$ und damit das $\alpha'$ ein Superschlüssel und es gilt der Zweite fall.

## Aufgabe 3

Sei das relations Schema $R = \lbrace A, B, C, D\rbrace$ und die Zerlegung
$$R_1 = \lbrace A, B, D\rbrace; R_2 = \lbrace A, B, C\rbrace$$
Gelten außerdem folgende FDs
$A\to B$
$A\to D$
$B\to C$

Es gilt offensichtlich $R_1 \cup R_2 = R$. Die Zerlegung ist außerdem Verlustfrei da bei einem Join auf $A, B$ dadurch das $A$ ein Superschlüssel ist alles bestimmt ist.

Es gilt jedoch keine der beiden Bedingungen der Vorlesung:
- $R_1 \cap R_2 = AB\to D\not\in F^+_{R}$
- $R_1 \cap R_2 = AB\to C \not\in F^+_{R}$

## Aufgabe 4

```java
import java.io.*;  
import java.util.*;  
  
public class G3_09 {  
    public static void main(String[] args) throws FileNotFoundException, IOException {  
        var fds = fromFile(args[0]);  
        var allColumns = allColumns(fds);  
        var relations = Synthesis.synthesis(fds, allColumns);  
        for (var rel : relations) {  
            System.out.println(rel.toString());  
        }  
    }  
  
    /**  
     * Parse the input file     ** @param path path to the input file  
     * @return A Collection of the Functional Dependencies from hte input file  
     * @throws FileNotFoundException  
     * @throws IOException  
     */    private static Collection<FunctionalDependency> fromFile(String path) throws FileNotFoundException, IOException {  
        var fds = new ArrayList<FunctionalDependency>();  
        try (BufferedReader br = new BufferedReader(new FileReader(path))) {  
            String line;  
            while ((line = br.readLine()) != null) {  
                fds.add(FunctionalDependency.parse(line));  
            }  
            return fds;  
        }  
    }  
  
    /**  
     * Extract the Set of all Columns from a list of Functional Dependencies     ** @param fds  
     * @return  
     */  
    private static ColumnSet allColumns(Collection<FunctionalDependency> fds) {  
        var result = new ColumnSet(new ArrayList<>());  
        for (var fd : fds) {  
            result = result.unionWith(fd.toRelation());  
        }  
        return result;  
    }  
}  
  
class Synthesis {  
  
    /**  
     * Calculate the Attribute Hull of a given set of attributes from a given set     * of functional dependencies.     *     * See Slide 531  
     ** @param fds   the collection of functional dependencies to work with  
     * @param start the set of attributes to start with  
     * @return      the attribute hull of start  
     */    public static ColumnSet attrHull(Collection<FunctionalDependency> fds, ColumnSet start) {  
        var res = start;  
        boolean changed = true;  
        while(changed){  
            changed = false;  
            for (FunctionalDependency fd : fds){  
                var beta = fd.getAntecedent();  
                 if (beta.isSubsetOrEqualOf(start)){  
                     res = res.unionWith(fd.getConsequent());  
                     changed = true;  
                 }  
            }  
        }  
  
        return res;  
    }  
  
    /**  
     * Calculate the canonical cover of a given set of functional dependencies     *     * See slide 535  
     ** @param fds the set of functional dependencies  
     * @return the canonical cover of fds  
     */    public static Collection<FunctionalDependency> canonicalCover(Collection<FunctionalDependency> fds) {  
        ArrayList<FunctionalDependency> step1 = new ArrayList<>();  
        for (var fd : fds){  
            var leftReduced = fd.leftReduce(fds);  
            step1.add(leftReduced);  
        }  
  
        ArrayList<FunctionalDependency> step2 = new ArrayList<>();  
        for(var fd : step1){  
            var rightReduced = fd.rightReduce(fds);  
            if(!rightReduced.getConsequent().isEmpty()){  
                step2.add(rightReduced);  
            }  
        }  
  
        Map<ColumnSet, ColumnSet> combined = new HashMap<>();  
  
        for (FunctionalDependency fd : step2){  
            combined.putIfAbsent(fd.getAntecedent(), fd.getConsequent());  
            combined.computeIfPresent(fd.getAntecedent(), (k, v) -> v.unionWith(fd.getConsequent()));  
        }  
  
        ArrayList<FunctionalDependency> res = new ArrayList<>();  
        for (Map.Entry<ColumnSet, ColumnSet> entry : combined.entrySet()){  
            res.add(new FunctionalDependency(entry.getKey(), entry.getValue()));  
        }  
  
        return res;  
    }  
  
    /**  
     * Find a candidate key for a given set of attributes under a given set of     * functional dependencies.     ** @param allColumns the set of attributes for which we seek a key  
     * @param fds        the collection of functional dependencies which apply  
     * @return a candidate key for allColumns.  
     */    public static ColumnSet findCandidateKey(ColumnSet allColumns, Collection<FunctionalDependency> fds) {  
        var candidateKey = allColumns;  
  
        for (var col : allColumns) {  
            var tempKey = candidateKey.without(col);  
            if (attrHull(fds, tempKey).equals(allColumns)) {  
                candidateKey = tempKey;  
            }  
        }  
  
        return candidateKey;  
    }  
  
    /**  
     * The overall synthesis algorithm     *     * see slide 562  
     ** @param fds        the functional dependencies  
     * @param allColumns the set of all columns  
     * @return a collection of relations in 3rd normal form  
     */    public static Collection<ColumnSet> synthesis(Collection<FunctionalDependency> fds, ColumnSet allColumns) {  
        Collection<FunctionalDependency> canonicalCover = canonicalCover(fds);  
  
        List<ColumnSet> relations = new ArrayList<>();  
        Map<ColumnSet, List<FunctionalDependency>> schemaToFds = new HashMap<>();  
  
        for (FunctionalDependency fd : canonicalCover) {  
            ColumnSet relation = fd.toRelation();  
            relations.add(relation);  
            schemaToFds.putIfAbsent(relation, new ArrayList<>());  
            schemaToFds.get(relation).add(fd);  
        }  
  
        ColumnSet candidateKey = findCandidateKey(allColumns, canonicalCover);  
        boolean candidateKeyInRelations = false;  
  
        for (ColumnSet relation : relations) {  
            if (findCandidateKey(relation, canonicalCover).equals(candidateKey)) {  
                candidateKeyInRelations = true;  
                break;  
            }  
        }  
  
        if (!candidateKeyInRelations) {  
            relations.add(candidateKey);  
        }  
  
        List<ColumnSet> finalRelations = new ArrayList<>(relations);  
  
        for (int i = 0; i < relations.size(); i++) {  
            for (int j = 0; j < relations.size(); j++) {  
                if (i != j && relations.get(i).isSubsetOrEqualOf(relations.get(j))) {  
                    finalRelations.remove(relations.get(i));  
                    break;  
                }  
            }  
        }  
  
        return finalRelations;  
    }  
  
}  
  
/**  
 * A Set of attributes */class ColumnSet implements Iterable<String> {  
    private final Set<String> contents;  
  
    public static final Comparator<ColumnSet> SIZE_COMPARATOR = Comparator.<ColumnSet>comparingInt(s -> s.size())  
            .reversed();  
  
    public ColumnSet(Collection<String> contents) {  
        this.contents = new TreeSet<>(contents);  
        for (var foo : contents) {  
            if (foo.equals(""))  
                throw new RuntimeException("Must not have empty column names");  
        }  
    }  
  
    /**  
     * parse a set from a string as defined in the task     ** @param input  
     * @return  
     */  
    public static ColumnSet parse(String input) {  
        return new ColumnSet(Arrays.asList(input.split("\\s+")));  
    }  
  
    /**  
     * @return the number of attributes in the set  
     */    public int size() {  
        return contents.size();  
    }  
  
    /**  
     * @return true iff this set's size is 0  
     */    public boolean isEmpty() {  
        return contents.isEmpty();  
    }  
  
    /**  
     * perform set union     ** @param other the set to union this set with  
     * @return a new set which contains the elements contained either in this  
     *         set or the other set.     */    public ColumnSet unionWith(ColumnSet other) {  
        var res = new TreeSet<>(contents);  
        res.addAll(other.contents);  
        return new ColumnSet(res);  
    }  
  
    /**  
     * Check whether all elements from this set are contained in the other set     ** @param rhs the other set  
     * @return  
     */  
    public boolean isSubsetOrEqualOf(ColumnSet rhs) {  
        return rhs.contents.containsAll(contents);  
    }  
  
    /**  
     * Check whether the attribute col is contained in this set     ** @param col the attribute to test  
     * @return true iff this set contains col  
     */    public boolean contains(String col) {  
        return contents.contains(col);  
    }  
  
    /**  
     * insert a new attribute into this set     ** @param col the attribute to add  
     * @return a new set which contains all elements from this set and the new  
     *         attribute col.     */    public ColumnSet add(String col) {  
        var res = new TreeSet<>(contents);  
        res.add(col);  
        return new ColumnSet(res);  
    }  
  
    /**  
     * remove an attribute from this set     ** @param col the sttribute to remove  
     * @return a new set which contains all elements  
     */    public ColumnSet without(String col) {  
        var res = new TreeSet<>(contents);  
        res.remove(col);  
        return new ColumnSet(res);  
    }  
  
    @Override  
    public Iterator<String> iterator() {  
        return contents.iterator();  
    }  
  
    @Override  
    public boolean equals(Object o) {  
        if (!(o instanceof ColumnSet))  
            return false;  
        var rhs = (ColumnSet) o;  
        return contents.equals(rhs.contents);  
    }  
  
    @Override  
    public String toString() {  
        return String.join(" ", contents);  
    }  
}  
  
/**  
 * A class which models a functional dependency. The attributes in the set * "antecedent" define the values of the attributes in the set "consequent". */class FunctionalDependency {  
    private final ColumnSet antecedent;  
    private final ColumnSet consequent;  
  
    public FunctionalDependency(ColumnSet ante, ColumnSet cons) {  
        antecedent = ante;  
        consequent = cons;  
    }  
  
    /**  
     * parse a functional dependency as defined in the task     ** @param input  
     * @return  
     */  
    public static FunctionalDependency parse(String input) {  
        var parts = input.split("\\s*->\\s*");  
        if (parts.length != 2)  
            throw new IllegalArgumentException("Malformed Input");  
        var ante = ColumnSet.parse(parts[0]);  
        var cons = ColumnSet.parse(parts[1]);  
        return new FunctionalDependency(ante, cons);  
    }  
  
    public ColumnSet getAntecedent() {  
        return antecedent;  
    }  
  
    public ColumnSet getConsequent() {  
        return consequent;  
    }  
  
    /**  
     * perform a reduction of the left side of a functional dependency     *     * see slide 535  
     ** @param fds the set of all valid functional dependencies  
     * @return a new, reduced functional dependency  
     */    public FunctionalDependency leftReduce(Collection<FunctionalDependency> fds) {  
        var resAnte = getAntecedent();  
        for (var A : getAntecedent()){  
            if(!getConsequent().isSubsetOrEqualOf(Synthesis.attrHull(fds, getAntecedent().without(A)))){  
                resAnte = resAnte.without(A);  
            }  
        }  
        return new FunctionalDependency(resAnte, getConsequent());  
    }  
  
    /**  
     * perform a reduction of the right side of a functional dependency     *     * see slide 535  
     ** @param fds the set of all valid functional dependencies  
     * @return a new, reduced functional dependency  
     */    public FunctionalDependency rightReduce(Collection<FunctionalDependency> fds) {  
        var resCons = getConsequent();  
        var fdsWithout = new ArrayList<>(fds);  
        fds.remove(this);  
  
        for(var B : getConsequent()){  
            var newCons = resCons.without(B);  
            FunctionalDependency modified = new FunctionalDependency(getAntecedent(), newCons);  
  
            var fdsWithModified = new ArrayList<>(fdsWithout);  
            fdsWithModified.add(modified);  
            var closure = Synthesis.attrHull(fdsWithModified, getAntecedent());  
            if (closure.contains(B)){  
                resCons = resCons.without(B);  
            }  
        }  
  
        return new FunctionalDependency(getAntecedent(), resCons);  
    }  
  
    /**  
     * @return the set of all attributes which are part of this relation as  
     *         required for the synthesis algorithm on slide 562     */    public ColumnSet toRelation() {  
        return getConsequent().unionWith(getAntecedent());  
    }  
  
    @Override  
    public String toString() {  
        return antecedent.toString() + " -> " + consequent.toString();  
    }  
}
```