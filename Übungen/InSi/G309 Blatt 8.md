
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_a)_
View $v1$:

Es können alle drei Tupel eingefügt werden, aber keiner von den Tupeln würde angezeigt werden, da sie alle die $WHERE$-Bedingung nicht erfüllen.

View $v2$:

In der View $v2$ können zwei von drei Tupeln eingefügt werden, da wir mit $CHECK OPTION$ auf die $WHERE$-Bedingung achten müssen und wir dann nur Tupel mit dem $Semester \geq 4$ hinzufügen können. Also können wir ii) nicht hinzufügen.

View $v3$:
Die ersten beiden Tupel können nicht eingefügt werden, das erste weil $D < M$ und das zweite weil die Matrnr $\le 40000$. Nur das letzte kann eingefügt werden

View $v4$:
Nur das dritte Tupel kann eingefügt werden. Tupel 1 verletzt die Bedingung von View 1 und das zweite von view $2$.

_b)_

```sql
CREATE TABLE pruefenconst (
	matrnr INTEGER REFERENCES studenten(matrnr),
	persnr INTEGER REFERENCES professoren(persnr),
	vorlnr INTEGER REFERENCES vorlesungen(vorlnr),
	note NUMERIC(2, 1) CHECK  (note IN (1.0, 1.3, 1.7, 2.0, 2.3, 2.7, 3.0, 3.3, 3.7, 4.0, 5.0))
);
```

_c)_

```sql
CREATE OR REPLACE FUNCTION neues_semester()
RETURNS VOID AS $$
BEGIN
    UPDATE studenten
    SET semester = semester + 1
    WHERE matrikelnummer IN (
	    SELECT DISTINCT studenten.matrnr 
	    FROM (studenten CROSS JOIN vorlesungen) 
	    LEFT JOIN pruefen 
	    ON studenten.matrnr = pruefen.matrnr 
		    AND pruefen.vorlnr = vorlesungen.vorlnr 
	    GROUP BY studenten.matrnr,
		    vorlesungen.vorlnr, pruefen.note 
	    HAVING pruefen.note IS NULL OR MIN(note) > 4.0
	)
END;
$$ LANGUAGE plpgsql;
```

## Aufgabe 2

_a)_

```sql
CREATE OR REPLACE FUNCTION check_Pruefer_UDF()
RETURNS TRIGGER AS $$
BEGIN 
	IF NOT 
		0 < (SELECT COUNT(*) 
			FROM vorlesungen 
			WHERE NEW.persnr = gelesen_von 
			AND NEW.vorlnr = vorlnr)
		THEN 
			RAISE NOTICE 'Warnung, falscher Prüfer';
			RETURN NULL;
	END IF;
	RETURN NEW;
END; $$
LANGUAGE plpgsql;

CREATE TRIGGER check_Pruefer_Trigger BEFORE INSERT ON pruefen FOR EACH ROW EXECUTE PROCEDURE check_Pruefer_UDF()
```

_b)_

```sql
ALTER TABLE pruefen ADD COLUMN startzeit TIME, ADD COLUMN endzeit TIME;
```

_c)_

```sql
CREATE OR REPLACE FUNCTION check_Overlap_UDF()
RETURNS TRIGGER AS $$ 
BEGIN 
	IF 0 < (SELECT COUNT(*)
		FROM pruefen
		WHERE NEW.persnr = persnr
		AND endzeit > NEW.startzeit 
		AND startzeit < NEW.endzeit)
	THEN 
		RAISE NOTICE 'Overlap Prüfer';
		RETURN NULL;
	END IF;
	IF 0 < (SELECT COUNT(*)
		FROM pruefen WHERE NEW.matrnr = matrnr 
		AND endzeit > NEW.startzeit 
		AND startzeit < NEW.endzeit)
	THEN
		RAISE NOTICE 'Overlap Student';
		RETURN NULL;
	END IF;
	RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER check_Overlap_Trigger BEFORE INSERT ON pruefen FOR EACH ROW EXECUTE PROCEDURE check_Overlap_UDF()
```

_d)_

```sql
CREATE OR REPLACE FUNCTION berechne_pruefungsdauer(ects INTEGER)
RETURNS INTERVAL AS $$
DECLARE
    dauer INTERVAL;
BEGIN
    dauer := make_interval(mins => GREATEST(4 * ects, 20));
    dauer := LEAST(dauer, '60 minutes'::INTERVAL);
    RETURN dauer;
END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION finde_naechsten_termin(matrnr INTEGER, vorlnr INTEGER, persnr INTEGER)
RETURNS TIME AS $$
DECLARE
    startzeit TIME := now();
    endzeit TIME;
    pruefungsdauer INTERVAL;
BEGIN
    SELECT berechne_pruefungsdauer(v.sws) INTO pruefungsdauer
    FROM vorlesungen v
    WHERE v.vorlnr = vorlnr;

    LOOP
        endzeit := startzeit + pruefungsdauer;
        IF NOT EXISTS (
            SELECT 1 FROM pruefen p
            WHERE (p.persnr = persnr OR p.matrnr = matrnr)
            AND (p.startzeit, p.endzeit) OVERLAPS (startzeit, endzeit)
        ) THEN
            RETURN startzeit;
        END IF;


        startzeit := startzeit + INTERVAL '10 minutes';
    END LOOP;
END;
$$ LANGUAGE plpgsql;

CREATE OR REPLACE FUNCTION pruefungs_trigger_funktion()
RETURNS TRIGGER AS $$
BEGIN
    IF NEW.startzeit IS NULL THEN
        NEW.startzeit := finde_naechsten_termin(NEW.matrnr, NEW.vorlnr, NEW.persnr);
        NEW.endzeit := NEW.startzeit + berechne_pruefungsdauer((SELECT sws FROM vorlesungen WHERE vorlnr = NEW.vorlnr));
    END IF;

    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER setze_pruefungstermin
BEFORE INSERT ON pruefen
FOR EACH ROW
EXECUTE FUNCTION pruefungs_trigger_funktion();
```

## Aufgabe 3

_a)_

1. $C \to B$ ist keine Gültige Abhängigkeit da $t_1.C = t_2.C$ aber $t_1.B \not = t_2.B$
2. $A\to C$ ist keine Gültige Abhängigkeit da $t_4.A = t_6.A$ aber $t_4.C \not = t_6.C$
3. $CB \to A$ ist eine Gültige Abhängigkeit.
4. $BCD \to A$ ist eine Gültige Abhängigkeit.

_b)_
1. $C$ kann nicht $B$ identifizieren, daher kann es nicht eine Gesamte reihe identifizieren.
2. $D$ ist kein Valider Superschluessel da $t_1.D = t_5.D$ aber $t_1.C \not = t_5.C$
3. $AD$ ist kein Valider Superschluessel da $t_6.A = t_7.A \land t_6.D = t_7.D$ aber $t_6.B \not = t_7.B$
4. $BC$ ist kein valider Superschluessel da $t_0.B = t_9.B \land t_0.C = t_0.C$ aber $t_0.D \not = t_9.D$
5. $ABCD$ ist ein valider Superschluessel, da die gesamte Relation immer ein Superschluessel ist.
6. $ACD$ ist ein valider Superschluessel, da jedes Wertetupel von $ACD$ nur einmal in der Datenbank vorkommt. Da dies der kleinste Superschluessel ist ist er auch ein Kandidatenschluessel.


## Aufgabe 4
$$\vdash \alpha \to \beta\gamma \land \beta \to \delta \implies \alpha \to \beta\delta\gamma$$
Nach dem Deduktionssatz gilt diese Aussage genau dann wenn
$$\alpha \to \beta\gamma, \beta \to \delta\vdash \alpha \to \beta\delta\gamma$$
gilt:


$$\begin{align}
&1.\quad\alpha \to \beta\gamma &&\text{(Vorraussetzung)}\\
&2.\quad \beta \to \delta &&\text{(Vorraussetzung)}\\
&3.\quad \alpha \to \beta &&(\text{Dekomposition 1.})&\\
&4.\quad \alpha \to \gamma &&(\text{Dekomposition 1.})&\\
&5.\quad \alpha \to \delta &&(\text{Transitivitaet 3, 2})&\\
&6.\quad \alpha \to \beta\delta &&(\text{Vereiningung 3, 5})&\\
&7.\quad \alpha \to\beta\delta\gamma &&(\text{Vereinigung 6, 4})&
\end{align}$$

Daher gilt $\alpha \to \beta\gamma \land \beta \to\delta \implies \alpha\to\beta\gamma\delta$
