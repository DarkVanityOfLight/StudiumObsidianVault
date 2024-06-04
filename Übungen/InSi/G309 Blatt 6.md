
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_a)_
```sql
DROP TABLE Assistenten
```

_b)_
```sql
ALTER TABLE Professoren
ADD COLUMN gebaeude INTEGER,
ADD COLUMN raumnr INTEGER;
```

`psql -d -f buero.sql`

_c)_

```sql
ALTER TABLE pruefen ADD COLUMN ects INTEGER;
```

_d)_

```sql
UPDATE pruefen                                      
SET ects = (SELECT sws FROM vorlesungen WHERE pruefen.vorlnr = vorlesungen.vorlnr);
```


## Aufgabe 2

_a)_

```sql
SELECT gebaeude, COUNT(*) AS anzahl
FROM pruefen
JOIN professoren ON pruefen.persnr = professoren.persnr
GROUP BY gebaeude
ORDER BY anzahl DESC
LIMIT 1;
```

_b)_

```sql
SELECT DISTINCT studenten.name
FROM studenten 
JOIN pruefen ON studenten.matrnr = pruefen.matrnr 
JOIN voraussetzen ON pruefen.vorlnr = voraussetzen.nachfolger
WHERE NOT EXISTS (
	SELECT * FROM voraussetzen 
	LEFT JOIN hoeren ON voraussetzen.vorgaenger = hoeren.vorlnr AND hoeren.matrnr = studenten.matrnr 
	WHERE voraussetzen.nachfolger = pruefen.vorlnr AND hoeren.vorlnr IS NULL);
```

_c)_

```sql
SELECT DISTINCT name
FROM studenten NATURAL JOIN pruefen 
WHERE 
        pruefen.note < (SELECT AVG(note) as A 
                FROM pruefen as p2  
                WHERE p2.vorlnr = pruefen.vorlnr ) 
        AND pruefen.note < 5.0 
        AND 1 = (SELECT COUNT(*) FROM pruefen as p3  
                WHERE p3.note = 5.0 AND p3.matrnr = pruefen.matrnr AND p3.vorlnr = pruefen.vorlnr);
```

_d)_

```sql
WITH bestanden AS (
	SELECT matrnr FROM pruefen GROUP BY matrnr
	HAVING COUNT(CASE WHEN note <= 4.0 THEN 1 ELSE NULL END) = (SELECT COUNT(*) FROM vorlesungen)
)
SELECT name, 'Dozierend' as reason FROM professoren
UNION ALL
SELECT name, 'Absolvent*Innen' as reason FROM studenten  
	WHERE studenten.matrnr IN (SELECT matrnr FROM bestanden)
UNION ALL
SELECT name, 'Studierende' as reason FROM studenten
	WHERE studenten.matrnr NOT IN (SELECT matrnr FROM bestanden);
```


## Aufgabe 3

_a)_

```sql
CREATE TABLE three_valued_logic (
    A BOOLEAN,
    B BOOLEAN
);

INSERT INTO three_valued_logic (A, B) VALUES
    (TRUE, TRUE),
    (TRUE, FALSE),
    (TRUE, NULL),
    (FALSE, TRUE),
    (FALSE, FALSE),
    (FALSE, NULL),
    (NULL, TRUE),
    (NULL, FALSE),
    (NULL, NULL);

SELECT 
    A, 
    B, 
    (A AND B) AS AND_result
FROM 
    three_valued_logic;

```

_b)_

```sql
SELECT mytable.id, 
COALESCE(mytable_other.col1, mytable_default.col1) AS col1, COALESCE(mytable_other.col2, mytable_default.col2) AS col2 
FROM  mytable LEFT JOIN mytable_other ON mytable.id = mytable_other.id 
CROSS JOIN mytable_default
```

## Aufgabe 4

_Standard 92_

__myview1__

> Funktioniert

```sql
INSERT INTO myview1(id, title, submission_date) VALUES(4,'test2','30-04-2000');
```

__myview2__

> Funktioniert nicht

Wir haben keine Spalte `Titel` in der View, aber `Titel` darf in der ursprünglichen Tabelle nicht `null` sein

__myview3__

> Funktioniert nicht

Unsere View besteht aus mehreren Tabellen.

__myview4__

> Funktioniert nicht

Wir haben eine Aggregationsfunktion und eine Gruppierung.

---

_Standard 99_

__myview1__

> Funktioniert

```sql
INSERT INTO myview1(id, title, submission_date) VALUES(4,'test2','30-04-2000');
```

__myview2__

> Funktioniert nicht

Wir haben keine Spalte `Titel` in der View, aber `Titel` darf in der ursprünglichen Tabelle nicht `null` sein

__myview3__

> Funktioniert

```sql
INSERT INTO myview3(id, title, submission_date,posting_id,no,content) 
VALUES(9,'test10','01-01-1999',9,2,'test content');
```

__myview4__

> Funktioniert nicht

Wir haben eine Aggregationsfunktion und eine Gruppierung.
