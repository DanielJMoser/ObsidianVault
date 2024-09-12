## Grundlagen und Definitionen

- Definition Datenbank
- CAP Theorem
- Codd’s 9 rules
- DB-Systemarchitektur mit Unterscheidung: Database System, Database Management System, Database und Data Dictionary
- Modeldefinition nach Stachowiak (Mapping, Reduction, Pragmatism)
- Unterscheidung Schema (Intension) und Data Expression (Extension)
- Definition: Daten Redundanz, Konsistenz und Integrität

## Datenbankentwurf und Modellierung

- Database Design Steps
- ER/EER Diagramme
- Relationales Model (Schema, Relationen, Attribute, Tupel)
- Primärschlüssel + künstliche Schlüssel und Fremdschlüssel
- Anomalien
- Normalformen (1. NF bis 3.NF + Boyce-Codd NF)
- Relationale Algebra

## Abfragesprachen und SQL

- Definition Query Language
- SQL
  - Bestandteile
  - DQL, DML, DCL, TCL
  - Operatoren
  - Aggregationsfunktionen / Gruppierungen
  - Geschachtelte Abfragen (Korreliert vs. Unkorreliert)
  - Indices
  - Views
- Übersicht SQL Query Processing -> Query Parsing into Relational Algebra + Optimierung + Code Generierung

## Datenintegrität und Constraints

- Ternärer Bool Datentyp
- Constraints (NOT NULL, CHECK, UNIQUE, PRIMARY KEY; FOREIGN KEY)
- Referentielle Integrität

## Generalisierung und Spezialisierung

- Strategien für Generalisierung/Spezialisierung mit Vor- und Nachteilen

## Transaktionen und Synchronisation

- Transaktionen
- Read/Write Model
- Statement Serialisierung
- Conflict Graph
- Eigenschaften von Statement Schedules
- Serialisierungsmethoden im Überblick
