

Die Flynn'sche Taxonomie ist ein **Klassifikationsschema** für **Computersystemarchitekturen**, das 1966 von Michael J. Flynn eingeführt wurde. Es kategorisiert Computersysteme basierend auf der **Parallelität von Befehlen** (Instruktionen) und **Daten**, die innerhalb eines Systems verarbeitet werden. Die Flynn'sche Taxonomie unterscheidet vier grundlegende Architekturen:

## 1. SISD (Single Instruction, Single Data)

- **Beschreibung:** Einfache sequentielle Verarbeitung, bei der ein einzelner Prozessor jeweils einen Befehl auf einem Datenelement ausführt.
- **Merkmale:**
  - Keine Parallelität in der Befehls- oder Datenverarbeitung.
  - Traditionelle von-Neumann-Architektur.
- **Beispiele:** Einfache Mikroprozessoren, die eine serielle Verarbeitung durchführen.

![[zZDrawing_Flynn_SISD]]

## 2. SIMD (Single Instruction, Multiple Data)

- **Beschreibung:** Ein einzelner Befehl wird gleichzeitig auf mehrere Datenelemente angewendet. Diese Architektur eignet sich besonders für Anwendungen, die gleiche Operationen auf große Datensätze ausführen.
- **Merkmale:**
  - Instruktionsstrom ist einheitlich, während der Datenstrom parallel verarbeitet wird.
  - Hohe Effizienz bei Vektorverarbeitung, Multimediaanwendungen, und wissenschaftlichen Berechnungen.
- **Beispiele:** Grafikkarten (GPUs), Vektorprozessoren, Multimedia-Erweiterungen wie SSE (Streaming SIMD Extensions).

![[zZDrawing_Flynn_SIMD]]

## 3. MISD (Multiple Instruction, Single Data)

- **Beschreibung:** Mehrere Prozessoren führen unterschiedliche Befehle auf demselben Datenelement aus. Diese Architektur ist theoretisch interessant, aber in der Praxis kaum umgesetzt.
- **Merkmale:**
  - Hohe Redundanz und Fehlererkennungsmöglichkeiten.
  - Begrenzte praktische Anwendungen, da es selten sinnvoll ist, unterschiedliche Instruktionen auf die gleichen Daten anzuwenden.
- **Beispiele:** Redundante Systeme für spezielle Anwendungen, wie z. B. in der Raumfahrt für Fehlertoleranz.

![[zZDrawing_Flynn_MISD]]
## 4. MIMD (Multiple Instruction, Multiple Data)

- **Beschreibung:** Mehrere Prozessoren führen unterschiedliche Befehle auf verschiedene Datenelemente aus. Diese Architektur ermöglicht die größte Flexibilität und wird in modernen multiprozessor- und Multicore-Systemen häufig verwendet.
- **Merkmale:**
  - Jede Einheit kann unabhängig operieren, was eine hohe Parallelität ermöglicht.
  - Kann sowohl für Aufgaben mit hohem Durchsatz (Throughput) als auch für solche mit niedriger Latenz genutzt werden.
- **Beispiele:** Multiprozessorsysteme, verteilte Systeme, Cluster-Computing, moderne CPUs mit mehreren Kernen.

![[zZDrawing_Flynn_MIMD]]

## Bedeutung und Anwendung

Die Flynn'sche Taxonomie bietet eine Grundlage, um die Architektur von Computersystemen zu verstehen und zu vergleichen, insbesondere in Bezug auf ihre Fähigkeit, parallel zu arbeiten. Sie hilft, die Vor- und Nachteile verschiedener Architekturen für bestimmte Anwendungsbereiche zu bewerten, z. B. die Wahl zwischen SIMD für Datenparallelität und MIMD für Aufgabenparallelität.

Flynn's Klassifikation hat in der Informatik und insbesondere in der Entwicklung von Hochleistungscomputern, supercomputing und parallelverarbeitenden Systemen eine große Bedeutung. Sie ist nach wie vor relevant, obwohl moderne Architekturen zunehmend hybride Ansätze verfolgen, die Elemente mehrerer Flynn-Kategorien kombinieren.







---

## Quellen

- Flynn, M. J. (1966). "Very high-speed computing systems." *Proceedings of the IEEE*.
