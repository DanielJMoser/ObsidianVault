-> **Erinnerung**: Unter Parallelismus versteht man allgemein die **nebenläufige** (d.i. gleichzeitige) Bearbeitung von Aufgaben. Parallelismus kann auf **mehreren Ebenen** auftreten.

# Arten von Parallelismus

Klassisch unterscheidet man zwischen **drei** Arten:

## Instruction-level Parallelism
-> gleichzeitige Bearbeitung von **mehreren Instruktionen in einem Prozessorkern**

- **Pipelining**: Überlappende Verarbeitung von Instruktionen im Prozessorkern
- **Superskalarität**: Gleichzeitige Ausführung von mehreren Instruktionen durch mehrfach vorhandene Funktionseinheiten im Prozessorkern
- **Out-of-Order Execution**: Umsortierung der Reihenfolge von Instruktionen eines Befehlsstroms, um Abhängigkeiten zu reduzieren.

Programmierer_innen müssen sich nicht explizit darum kümmern, ILP passiert automatisch durch [[CPU]] bzw. [[Compiler]].

___
## Data Parallelism
-> zu bearbeitende Daten werden auf **mehrere Knoten** verteilt, welche die ihnen zugewiesenen Datenpartitionen parallel verarbeiten.

### z.B. Matrixmultiplikationen
- Die Matrizen werden in **Partitionen** zerteilt (Zeilen- bzw. Spaltenweise) und an die einzelnen Knoten verteilt.
- Diese Berechnen ihre **Teilergebnisse**, welche in Summe das Gesamtergebnis bilden.
- [[Flynn'sche Taxonomie#2. SIMD (Single Instruction, Multiple Data)|SIMD]] ist ein Beispiel von klassischem Datenparallelismus!

Hier müssen sich Programmierer_innen in der Regel **explizit** um die Partitionierung kümmern!

___
## Task Parallelism
-> verschiedene Aufgaben werden auf mehrere Knoten verteilt, welche diese dann parallel erledigen.