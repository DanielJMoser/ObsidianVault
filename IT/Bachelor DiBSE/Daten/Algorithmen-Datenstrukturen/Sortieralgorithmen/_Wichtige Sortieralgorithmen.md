

-> Übersicht der wichtigsten **Sortieralgorithmen** inklusive einer kurzen Beschreibung und ihrer Performance in Landau-Notation.

| **Algorithmus**                              | **Beschreibung**                                                                                                                                                                         | **Performance**                                                                     |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **[[1_Insertion Sort\|Insertion Sort]]**     | Fügt jedes Element der unsortierten Liste in die richtige Position innerhalb der sortierten Liste ein.                                                                                   | $\mathcal{O}(n^2)$                                                                  |
| **[[2_Bubble Sort\|Bubble Sort]]**           | Vergleicht benachbarte Paare und vertauscht sie, wenn sie in der falschen Reihenfolge sind. Wiederholt dies, bis die Liste sortiert ist.                                                 | $\mathcal{O}(n^2)$                                                                  |
| **[[3_Merge Sort\|Merge Sort]]**             | Teilt die Liste rekursiv in zwei Hälften, sortiert jede Hälfte und fügt sie dann zusammen. -> [[Teile-und-Herrsche-Prinzip]]                                                             | $\mathcal{O}(n \log n)$                                                             |
| **Quick Sort**                               | Wählt ein **Pivot**-Element und partitioniert die Liste in Elemente kleiner und größer als das Pivot, sortiert dann rekursiv die Partitionen.                                            | Durchschnittlich $\mathcal{O}(n \log n)$, schlimmstenfalls $\mathcal{O}(n^2)$       |
| **[[Heap#Heapsort-Algorithmus\|Heap Sort]]** | Baut einen **[[Heap]]** aus den Daten auf und entnimmt dann wiederholt das Maximum (oder Minimum) zum Sortieren.                                                                         | $\mathcal{O}(n \log n)$                                                             |
| **Selection Sort**                           | Findet wiederholt das minimale Element aus der unsortierten Liste und verschiebt es an die sortierte Position.                                                                           | $\mathcal{O}(n^2)$                                                                  |
| **Shell Sort**                               | Eine Erweiterung von [[1_Insertion Sort\|Insertion Sort]], die Elemente mit einem bestimmten Abstand vergleicht und verschiebt, der sich schrittweise verringert.                        | Zwischen $\mathcal{O}(n)$ und $\mathcal{O}(n^2)$ (abhängig von der Implementierung) |
| **Counting Sort**                            | Zählt die Vorkommen jedes Elements und berechnet die Position jedes Elements in der sortierten Liste. Geeignet für ganzzahlige Schlüssel in begrenztem Bereich.                          | $\mathcal{O}(n + k)$                                                                |
| **Radix Sort**                               | Sortiert Zahlen durch Verteilung nach ihren Ziffernstellen, von der niedrigsten zur höchsten Stelle.                                                                                     | $\mathcal{O}(n \cdot k)$                                                            |
| **Bucket Sort**                              | Verteilt die Elemente in mehrere **Buckets** (Behälter), sortiert diese individuell (oft mit Insertion Sort) und kombiniert sie dann.                                                    | $\mathcal{O}(n + k)$                                                                |
| **Tim Sort**                                 | Eine hybride Sortiermethode, die **[[3_Merge Sort\|Merge Sort]]** und **[[1_Insertion Sort\|Insertion Sort]]** kombiniert, optimiert für reale Daten. Wird in Python und Java verwendet. | $\mathcal{O}(n \log n)$                                                             |

*Hinweis:* In den Performance-Angaben steht $n$ für die Anzahl der zu sortierenden Elemente und $k$ für den Wertebereich der Elemente (bei Counting Sort und Radix Sort).

---

#Algorithmen #Sortieren
