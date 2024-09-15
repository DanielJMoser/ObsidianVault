# Definition
Normalformen sind Regeln in der relationalen Datenbankmodellierung, die dabei helfen, Redundanzen zu minimieren und Datenanomalien zu vermeiden. Sie definieren die Anforderungen, die eine Datenbank erfüllen muss, um eine bestimmte Normalform zu erreichen. Die Anwendung dieser Regeln sorgt für eine effizientere Organisation der Daten und verbessert die Integrität und Konsistenz der Datenbank.

Die wichtigsten Normalformen sind die **1. Normalform (1NF)**, **2. Normalform (2NF)**, **3. Normalform (3NF)** und die **Boyce-Codd-Normalform (BCNF)**. Jede Normalform baut auf der vorhergehenden auf, sodass eine Tabelle die Anforderungen aller niedrigeren Normalformen erfüllen muss, um eine höhere Normalform zu erreichen.

# 1. Normalform (1NF)
## Definition
Eine Tabelle befindet sich in der **1. Normalform**, wenn:
- Alle Attribute atomar sind, das heißt, jedes Attribut enthält nur unteilbare Werte (keine wiederholten Gruppen oder Arrays).
- Alle Einträge in einer Spalte den gleichen Datentyp haben.
- Jedes Attribut einen eindeutigen Namen hat, und die Reihenfolge der Speicherung keine Bedeutung hat.

### Beispiel
**Vor der 1NF:**

| KundeID | Name         | Telefonnummer          |
| ------- | ------------ | ---------------------- |
| 1       | Max Müller   | 01234-5678, 09876-5432 |
| 2       | Anna Schmidt | 01234-1111             |

**Nach der 1NF:**

| KundeID | Name         | Telefonnummer |
|---------|--------------|---------------|
| 1       | Max Müller   | 01234-5678    |
| 1       | Max Müller   | 09876-5432    |
| 2       | Anna Schmidt | 01234-1111    |

Hier wurden die mehrfachen Telefonnummern in separate Zeilen aufgeteilt.

# 2. Normalform (2NF)
## Definition
Eine Tabelle ist in der **2. Normalform**, wenn sie:
- In der 1. Normalform ist.
- Jedes Nicht-Schlüssel-Attribut vollständig vom gesamten Primärschlüssel abhängt (d.h., es gibt keine Teilabhängigkeiten von zusammengesetzten Schlüsseln).

### Beispiel
**Vor der 2NF:**

| BestellID | ProduktID | Produktname | Preis |
|-----------|-----------|-------------|-------|
| 1         | 101       | Stuhl       | 50    |
| 2         | 102       | Tisch       | 150   |

Hier hängt `Produktname` und `Preis` nur von `ProduktID` ab, nicht von `BestellID`.

**Nach der 2NF:**
**Tabelle: Bestellungen**

| BestellID | ProduktID |
|-----------|-----------|
| 1         | 101       |
| 2         | 102       |

**Tabelle: Produkte**

| ProduktID | Produktname | Preis |
|-----------|-------------|-------|
| 101       | Stuhl       | 50    |
| 102       | Tisch       | 150   |

Die Tabelle `Produkte` stellt sicher, dass `Produktname` und `Preis` vollständig von `ProduktID` abhängen.

# 3. Normalform (3NF)
## Definition
Eine Tabelle ist in der **3. Normalform**, wenn sie:
- In der 2. Normalform ist.
- Kein Nicht-Schlüssel-Attribut transitiv von einem Schlüssel abhängt, d.h., jedes Nicht-Schlüssel-Attribut ist nur vom Primärschlüssel abhängig und nicht von anderen Nicht-Schlüssel-Attributen.

### Beispiel
**Vor der 3NF:**

| ProduktID | Produktname | KategorieID | Kategoriename |
|-----------|-------------|-------------|---------------|
| 101       | Stuhl       | 1           | Möbel         |
| 102       | Tisch       | 1           | Möbel         |

`Kategoriename` hängt transitiv von `ProduktID` über `KategorieID` ab.

**Nach der 3NF:**
**Tabelle: Produkte**

| ProduktID | Produktname | KategorieID |
|-----------|-------------|-------------|
| 101       | Stuhl       | 1           |
| 102       | Tisch       | 1           |

**Tabelle: Kategorien**

| KategorieID | Kategoriename |
|-------------|---------------|
| 1           | Möbel         |

Die Tabellen wurden so aufgeteilt, dass `Kategoriename` nur von `KategorieID` abhängt.

# Boyce-Codd-Normalform (BCNF)
## Definition
Die **Boyce-Codd-Normalform** (BCNF) ist eine strengere Version der 3NF. Eine Tabelle befindet sich in der BCNF, wenn sie:
- In der 3. Normalform ist.
- Für jede funktionale Abhängigkeit X → Y gilt, dass X ein Superschlüssel der Tabelle ist.

### Beispiel
**Vor der BCNF:**

| ProfessorID | KursID | Raum     |
|-------------|--------|----------|
| 1           | 101    | A101     |
| 2           | 102    | B202     |

Angenommen, ein Professor kann nur in einem bestimmten Raum unterrichten. Dies führt zu einer Abhängigkeit `Raum → ProfessorID`.

**Nach der BCNF:**
**Tabelle: Professoren**

| ProfessorID | Raum |
|-------------|------|
| 1           | A101 |
| 2           | B202 |

**Tabelle: Kurse**

| KursID | ProfessorID |
|--------|-------------|
| 101    | 1           |
| 102    | 2           |

Die Trennung stellt sicher, dass jede Tabelle in der BCNF ist, da `Raum` nun ausschließlich von `ProfessorID` abhängt.

# Bedeutung
-> essenziell für den Entwurf **effizienter** und **konsistenter** Datenbanken. 
Sie helfen, [[Datenredundanz|Redundanzen]] zu minimieren, [[Integrität]] zu gewährleisten und [[Anomalien]] zu vermeiden. 
Während die 1. Normalform auf atomare Werte fokussiert, sorgen die 2. und 3. Normalform sowie die BCNF für eine **strukturierte** und **eindeutige** Beziehung zwischen Schlüsseln und Attributen. 
Das Verständnis und die Anwendung dieser Normalformen sind entscheidend für die Erstellung robuster Datenbankdesigns.

___
#Datenbanken 