
> Marcel Wirdel, Kilian Lichtner

## Aufgabe 1

_a)_

```sql
SELECT DISTINCT name, semester, AVG(note) 
OVER (PARTITION BY semester) 
FROM studenten NATURAL JOIN pruefen WHERE note < 5;;
```

_b)_

```sql
SELECT DISTINCT name,
SUM(note) OVER (PARTITION BY professoren.name) as s 
FROM professoren NATURAL JOIN pruefen 
WHERE pruefen.note = 1 ORDER BY s;;
```

## Aufgabe 2

_a)_
```sql
SELECT s.name, s.semester, sa.avg_note 
FROM studenten s JOIN (
	SELECT s.semester, AVG(p.note) AS avg_note 
	FROM pruefen p JOIN studenten s ON s.matrnr = p.matrnr
	WHERE p.note < 5 
	GROUP BY s.semester) AS sa ON s.semester = sa.semester ORDER BY s.semester, s.name
```

_b)_

```sql
SELECT pro.name, COUNT(p.note) AS anzahl 
FROM professoren pro JOIN pruefen p ON p.persnr=pro.persnr WHERE p.note = 1 
GROUP BY pro.name 
ORDER BY anzahl ASC
```

## Aufgabe 3

_a)_

```sql
WITH RECURSIVE kameradinnen AS (
    SELECT s.matrnr, s.name, s.semester, 
	    p.persnr, p.vorlnr, p.note
    FROM studenten s
    NATURAL JOIN pruefen p
    WHERE s.matrnr = 94823 AND p.note = 5
    
    UNION
    
    SELECT s.matrnr, s.name, s.semester, p.persnr, p.vorlnr, p.note
    FROM studenten s
    NATURAL JOIN pruefen p
    JOIN kameradinnen k
    ON p.persnr = k.persnr AND p.vorlnr = k.vorlnr AND k.semester = s.semester
    WHERE p.note = 5
)
SELECT DISTINCT name FROM kameradinnen;
```

_b)_
```sql
WITH RECURSIVE kameradinnen AS (
    SELECT s.matrnr, s.name, s.semester, 
	    p.persnr, p.vorlnr, p.note
    FROM studenten s
    NATURAL JOIN pruefen p
    WHERE s.matrnr = 94823 AND p.note = 5
    
    UNION
    
    SELECT s.matrnr, s.name, s.semester, p.persnr, p.vorlnr, p.note
    FROM studenten s
    NATURAL JOIN pruefen p
    JOIN kameradinnen k
    ON p.persnr = k.persnr AND p.vorlnr = k.vorlnr AND k.semester = s.semester
    WHERE p.note = 5
)
SELECT COUNT(DISTINCT name) FROM kameradinnen;
```

## Aufgabe 4

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;
import java.util.Locale;
import java.sql.*;

public class G03_09 {
    public static void main(String args[]) {
        Configuration conf;
        try {
            conf = Configuration.parse(args);
        } catch (Exception e) {
            System.out.println("Usage:\n  java G03_09 path/to/file.txt");
            return;
        }
        var results = new ArrayList<Person>();

        Connection connection = null;
        try {
            Class.forName("org.postgresql.Driver");

            String dbUrl = "jdbc:postgresql://" + conf.DB_HOST + ":" + conf.DB_PORT + "/" + conf.DB_NAME;
            connection = DriverManager.getConnection(dbUrl, conf.DB_USER, conf.DB_PASSWORD);

            String viewName = "Gehalt" + conf.JAHR;

            // Check if the view already exists
            DatabaseMetaData meta = connection.getMetaData();
            ResultSet resultSet = meta.getTables(null, null, viewName, null);
            if (!resultSet.next()) {
                // Create the view if it does not exist
                String createViewSQL = "CREATE OR REPLACE VIEW " + viewName + " AS " +
                        "SELECT p.PNR, p.Gehalt + COALESCE(SUM(b.Betrag) OVER (PARTITION BY p.PNR), 0) AS Gehalt " +
                        "FROM Personal p " +
                        "LEFT JOIN Bonus b ON p.ANR = b.ANR AND b.Jahr = " + conf.JAHR + " " +
                        "GROUP BY p.PNR, p.Gehalt, b.Betrag;";
                try (Statement stmt = connection.createStatement()) {
                    stmt.executeUpdate(createViewSQL);
                }
            }            String querySQL1 = "SELECT anr FROM abteilung p WHERE p.name = " + "'" + conf.ABTEILUNG + "'";
            PreparedStatement stmt1 = connection.prepareStatement(querySQL1);
            ResultSet rs1 = stmt1.executeQuery();
            rs1.next();
            var ANR = rs1.getInt("anr");

            // Query the view for the given department
            String querySQL = "SELECT p.PNR, p.Name, g.Gehalt " +
                    "FROM Personal p " +
                    "JOIN " + viewName + " g ON p.PNR = g.PNR " +
                    "WHERE p.ANR = " + ANR +
                    " ORDER BY p.PNR";
            System.out.println(querySQL);
            try (PreparedStatement stmt = connection.prepareStatement(querySQL)) {
                ResultSet rs = stmt.executeQuery();
                while (rs.next()) {
                    int pnr = rs.getInt("PNR");
                    String name = rs.getString("Name");
                    double gehalt = rs.getDouble("Gehalt");
                    results.add(new Person(pnr, name, gehalt));
                }
            }
        } catch (ClassNotFoundException e) {
            System.out.println("PostgreSQL JDBC Driver not found.");
            e.printStackTrace();
        } catch (SQLException e) {
            e.printStackTrace();
        } finally {
            if (connection != null) {
                try {
                    connection.close();
                } catch (SQLException e) {
                    e.printStackTrace();
                }
            }
        }

        for (var result : results) {
            System.out.println(result);
        }
    }
}

class Configuration {
    public final String DB_NAME;
    public final String DB_HOST;
    public final String DB_PORT;
    public final String DB_USER;
    public final String DB_PASSWORD;
    public final String JAHR;
    public final String ABTEILUNG;

    private Configuration(String name, String host, String port, String user, String pw, String year, String dept) {
        this.DB_NAME = name;
        this.DB_HOST = host;
        this.DB_PORT = port;
        this.DB_USER = user;
        this.DB_PASSWORD = pw;
        this.JAHR = year;
        this.ABTEILUNG = dept;
    }

    @Override
    public String toString() {
        // Needed for debugging only
        var builder = new StringBuilder();
        builder.append(DB_USER);
        builder.append(':');
        builder.append(DB_PASSWORD);
        builder.append('@');
        builder.append(DB_HOST);
        builder.append(':');
        builder.append(DB_PORT);
        builder.append('/');
        builder.append(DB_NAME);
        builder.append("?year=");
        builder.append(JAHR);
        builder.append("&abteilung=");
        builder.append(ABTEILUNG);
        return builder.toString();
    }

    public static Configuration parse(String args[]) throws IOException {
        if (args.length != 1) {
            throw new IllegalArgumentException();
        }
        var reader = new BufferedReader(new FileReader(args[0]));
        String name = reader.readLine().trim();
        String host = reader.readLine().trim();
        String port = reader.readLine().trim();
        String user = reader.readLine().trim();
        String pw = reader.readLine().trim();
        String year = reader.readLine().trim();
        String dept = reader.readLine().trim();
        return new Configuration(name, host, port, user, pw, year, dept);
    }
}

class Person {
    private final int pnr;
    private final String name;
    private final double gehalt;

    public Person(int pnr, String name, double gehalt) {
        this.pnr = pnr;
        this.name = name;
        this.gehalt = gehalt;
    }

    @Override
    public String toString() {
        var builder = new StringBuilder();
        builder.append(pnr);
        builder.append(", ");
        builder.append(name);
        builder.append(": ");
        builder.append(String.format(Locale.ENGLISH, "%.2f", gehalt));
        return builder.toString();
    }
}

```
