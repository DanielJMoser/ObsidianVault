## Definition

Die **Relationale Algebra** ist ein **formales System** zur Manipulation und Abfrage von Relationen (Tabellen) in [[_Relationale Datenbanken|relationalen Datenbanken]]. 
Sie bietet eine Menge von **Operationen**, die auf **Relationen** angewendet werden können, um neue Relationen zu erzeugen. Diese Operationen ermöglichen es, **komplexe Datenabfragen** auszudrücken und zu verarbeiten. 
Die relationale Algebra bildet die **theoretische Grundlage** für relationale Datenbanksysteme und ist essenziell für das Verständnis von [[_SQL|_SQL]] und anderen Abfragesprachen.

## Grundlegende Operationen

Die relationale Algebra besteht aus einer Reihe von grundlegenden Operationen, die in zwei Kategorien unterteilt werden können: **Mengenoperationen** und **relationale Operationen**.

### Mengenoperationen

1. **Vereinigung (Union) (∪):**

   - Kombiniert die Tupel zweier Relationen und entfernt Duplikate.
   - **Bedingung:** Beide Relationen müssen union-kompatibel sein (gleiche Anzahl und Datentypen der Attribute).

2. **Durchschnitt (Intersection) (∩):**

   - Liefert die Tupel, die in beiden Relationen vorkommen.
   - **Bedingung:** Beide Relationen müssen union-kompatibel sein.

3. **Differenz (Difference) (-):**

   - Gibt die Tupel zurück, die in der ersten Relation, aber nicht in der zweiten vorhanden sind.
   - **Bedingung:** Beide Relationen müssen union-kompatibel sein.

### Relationale Operationen

1. **Selektion (Selection) (σ):**

   - Filtert Tupel basierend auf einer bestimmten Bedingung.
   - **Notation:** σ<sub>Bedingung</sub>(Relation)
   - **Beispiel:** σ<sub>Alter > 30</sub>(Mitarbeiter)

2. **Projektion (Projection) (π):**

   - Wählt bestimmte Attribute (Spalten) einer Relation aus.
   - **Notation:** π<sub>Attribute</sub>(Relation)
   - **Beispiel:** π<sub>Name, Gehalt</sub>(Mitarbeiter)

3. **Kartesisches Produkt (Cartesian Product) (×):**

   - Kombiniert jede Zeile der ersten Relation mit jeder Zeile der zweiten Relation.
   - **Notation:** Relation1 × Relation2

4. **Theta-Verbund (Theta Join) (⋈<sub>θ</sub>):**

   - Verbindet Tupel zweier Relationen basierend auf einer allgemeinen Bedingung θ.
   - **Notation:** Relation1 ⋈<sub>θ</sub> Relation2

5. **Natürlicher Verbund (Natural Join) (⋈):**

   - Ein Spezialfall des Theta-Verbunds, bei dem automatisch auf gleichnamige Attribute verknüpft wird.
   - **Notation:** Relation1 ⋈ Relation2

6. **Umbenennung (Rename) (ρ):**

   - Ändert den Namen einer Relation oder ihrer Attribute.
   - **Notation:** ρ<sub>NeuerName</sub>(Relation)

## Abgeleitete Operationen

Zusätzlich zu den grundlegenden Operationen gibt es abgeleitete Operationen, die aus den Grundoperationen zusammengesetzt werden können:

1. **Halbverbund (Semijoin):**

   - Kombiniert Tupel einer Relation mit denen einer anderen, jedoch werden nur die Attribute der ersten Relation zurückgegeben.

2. **Antiverbund (Antijoin):**

   - Gibt die Tupel der ersten Relation zurück, die keine übereinstimmenden Tupel in der zweiten Relation haben.

3. **Division:**

   - Wird verwendet, um Anfragen vom Typ "Finde alle X, die alle Y haben" zu beantworten.

## Beispiele

### Beispiel 1: Selektion und Projektion

**Gegeben:**

Relation **Mitarbeiter**

| MitarbeiterID | Name     | Abteilung | Gehalt |
|---------------|----------|-----------|--------|
| 1             | Müller   | Verkauf   | 5000   |
| 2             | Schmidt  | IT        | 6000   |
| 3             | Weber    | Verkauf   | 5500   |
| 4             | Lehmann  | HR        | 4800   |

**Anfrage:**

Finde die Namen aller Mitarbeiter in der Abteilung "Verkauf".

**Lösung:**

1. Selektion: σ<sub>Abteilung = 'Verkauf'</sub>(Mitarbeiter)

   Ergebnis:

   | MitarbeiterID | Name   | Abteilung | Gehalt |
   |---------------|--------|-----------|--------|
   | 1             | Müller | Verkauf   | 5000   |
   | 3             | Weber  | Verkauf   | 5500   |

2. Projektion: π<sub>Name</sub>(Ergebnis)

   Endergebnis:

   | Name   |
   |--------|
   | Müller |
   | Weber  |

### Beispiel 2: Natürlicher Verbund

**Gegeben:**

Relation **Kunden**

| KundenID | Name       | Stadt    |
|----------|------------|----------|
| 1        | Meier      | Berlin   |
| 2        | Schulz     | Hamburg  |
| 3        | Becker     | München  |

Relation **Bestellungen**

| BestellID | KundenID | Betrag |
|-----------|----------|--------|
| 1001      | 1        | 250    |
| 1002      | 2        | 450    |
| 1003      | 1        | 150    |

**Anfrage:**

Finde alle Bestellungen mit Kundennamen und Stadt.

**Lösung:**

Natürlicher Verbund: Kunden ⋈ Bestellungen

Ergebnis:

| KundenID | Name   | Stadt    | BestellID | Betrag |
|----------|--------|----------|-----------|--------|
| 1        | Meier  | Berlin   | 1001      | 250    |
| 1        | Meier  | Berlin   | 1003      | 150    |
| 2        | Schulz | Hamburg  | 1002      | 450    |

## Bedeutung und Anwendung

Die relationale Algebra ist fundamental für das Verständnis relationaler Datenbanksysteme und der Abfragesprache SQL. Sie bietet:

- **Formale Grundlage:** Ein mathematisches Fundament, um Datenbankabfragen zu formulieren und zu optimieren.
- **Abfrageoptimierung:** Datenbanksysteme nutzen die Prinzipien der relationalen Algebra, um Abfragen effizient zu verarbeiten.
- **Theoretische Analyse:** Ermöglicht die formale Überprüfung von Abfragen und deren Eigenschaften.

## Zusammenfassung

Die relationale Algebra ist ein wesentliches Konzept in der Datenbanktheorie, das eine Reihe von Operationen bereitstellt, um Relationen zu manipulieren und komplexe Datenabfragen zu formulieren. Durch das Verständnis dieser Operationen können Datenbankdesigner und -entwickler effizientere und effektivere Abfragen erstellen und die Leistung von Datenbanksystemen optimieren.

---

#Datenbanken