Der **Heap-Algorithmus** ist eng mit der Datenstruktur des Heaps verknüpft. Ein Heap ist eine spezielle Baumstruktur, die für effizientes Speichern und Abrufen von Daten verwendet wird, insbesondere wenn man auf Minima oder Maxima zugreifen möchte. Ich erkläre den **Heapsort-Algorithmus** sowie die Funktionsweise eines **Min-Heap** und **Max-Heap**, da diese eng mit der Nutzung von Heaps für Sortieralgorithmen und Prioritätswarteschlangen zusammenhängen.

### Heap-Datenstruktur

Ein Heap ist ein binärer Baum, der zwei Bedingungen erfüllen muss:

1. **Komplettheit**: Der Baum muss ein vollständiger Binärbaum sein. Das bedeutet, dass alle Ebenen vollständig ausgefüllt sind, mit Ausnahme der letzten, die von links nach rechts gefüllt wird.
2. **Heap-Eigenschaft**: Es gibt zwei Varianten von Heaps:
    - **Min-Heap**: In einem Min-Heap ist der Wert jedes Knotens kleiner oder gleich dem Wert seiner Kindknoten. Das Minimum befindet sich an der Wurzel des Baums.
    - **Max-Heap**: In einem Max-Heap ist der Wert jedes Knotens größer oder gleich dem Wert seiner Kindknoten. Das Maximum befindet sich an der Wurzel des Baums.

#### Beispiel für einen Min-Heap

```markdown
        1
      /   \
     3     6
    / \   /
   5   9 8

```

Hier ist 1 der kleinste Wert (die Wurzel), und jeder Elternknoten ist kleiner als seine Kindknoten.

### Heapsort-Algorithmus

**Heapsort** ist ein effizienter Sortieralgorithmus, der einen Max-Heap (oder Min-Heap) verwendet, um eine Liste von Elementen zu sortieren. Der Algorithmus hat eine Laufzeitkomplexität von **O(n log n)** und besteht aus zwei Hauptschritten:

1. **Build-Heap (Heap-Aufbau)**: Die unsortierte Liste wird in einen Max-Heap oder Min-Heap umgewandelt. Dies geschieht, indem jedes Element in der Liste in den Heap eingefügt wird. Für jeden Knoten im Baum wird die **Heapify**-Prozedur aufgerufen, um sicherzustellen, dass die Heap-Eigenschaft aufrechterhalten wird. Dies hat eine Laufzeit von **O(n)**.
    
2. **Sortieren durch Extraktion des Maximums** (für Max-Heap):
    
    - Da der größte Wert (Maximum) immer an der Wurzel eines Max-Heaps liegt, wird der Wert an der Wurzel extrahiert (d.h., er wird aus dem Heap entfernt und ans Ende der Liste gesetzt).
    - Der letzte Knoten im Heap wird zur Wurzel verschoben, und dann wird erneut **Heapify** aufgerufen, um die Heap-Eigenschaft zu reparieren.
    - Dieser Prozess wird für die restlichen Elemente wiederholt, bis der Heap leer ist. Jedes Mal wird das Maximum (oder Minimum) entfernt und an die entsprechende Stelle in der Liste gesetzt.Heapsort-Algorithmus

**Heapsort** ist ein effizienter Sortieralgorithmus, der einen Max-Heap (oder Min-Heap) verwendet, um eine Liste von Elementen zu sortieren. Der Algorithmus hat eine Laufzeitkomplexität von **O(n log n)** und besteht aus zwei Hauptschritten:

1. **Build-Heap (Heap-Aufbau)**: Die unsortierte Liste wird in einen Max-Heap oder Min-Heap umgewandelt. Dies geschieht, indem jedes Element in der Liste in den Heap eingefügt wird. Für jeden Knoten im Baum wird die **Heapify**-Prozedur aufgerufen, um sicherzustellen, dass die Heap-Eigenschaft aufrechterhalten wird. Dies hat eine Laufzeit von **O(n)**.
    
2. **Sortieren durch Extraktion des Maximums** (für Max-Heap):
    
    - Da der größte Wert (Maximum) immer an der Wurzel eines Max-Heaps liegt, wird der Wert an der Wurzel extrahiert (d.h., er wird aus dem Heap entfernt und ans Ende der Liste gesetzt).
    - Der letzte Knoten im Heap wird zur Wurzel verschoben, und dann wird erneut **Heapify** aufgerufen, um die Heap-Eigenschaft zu reparieren.
    - Dieser Prozess wird für die restlichen Elemente wiederholt, bis der Heap leer ist. Jedes Mal wird das Maximum (oder Minimum) entfernt und an die entsprechende Stelle in der Liste gesetzt.


#### Heapsort Pseudocode

```clike
Heapsort(A):
1. BuildMaxHeap(A)
2. for i = n downto 2:
     swap(A[1], A[i])
     MaxHeapify(A, 1, i - 1)

BuildMaxHeap(A):
1. for i = floor(n/2) downto 1:
     MaxHeapify(A, i, n)

MaxHeapify(A, i, n):
1. left = 2 * i
2. right = 2 * i + 1
3. largest = i
4. if left <= n and A[left] > A[largest]:
     largest = left
5. if right <= n and A[right] > A[largest]:
     largest = right
6. if largest ≠ i:
     swap(A[i], A[largest])
     MaxHeapify(A, largest, n)

```


### Erläuterung des Pseudocodes:

- **BuildMaxHeap**: Diese Funktion verwandelt das Array in einen Max-Heap, indem sie die **MaxHeapify**-Funktion für alle Knoten von der Mitte bis zur Wurzel aufruft. Dies stellt sicher, dass der Baum die Max-Heap-Eigenschaft erfüllt.
- **MaxHeapify**: Diese Funktion repariert die Heap-Eigenschaft, indem sie den größten Wert von Eltern und Kindknoten bestimmt und bei Bedarf den Elternknoten mit dem größten Kind vertauscht. Dies wird rekursiv für den betroffenen Teilbaum fortgesetzt, bis die Heap-Eigenschaft wiederhergestellt ist.
- **Heapsort**: Hier werden nach dem Aufbau des Max-Heaps die Wurzelknoten (Maximum) schrittweise extrahiert, und das Array wird sortiert, indem das Maximum ans Ende des Arrays gesetzt wird.

### Laufzeitkomplexität von Heapsort:

- **Heap-Aufbau**: O(n)
- **Sortieren durch Extraktion**: O(n log n), da für jedes der nnn Elemente das **Heapify**-Verfahren aufgerufen wird, das eine Laufzeit von O(log n) hat.
- **Gesamtzeit**: O(n log n)

### Anwendungen des Heaps

- **Prioritätswarteschlangen**: Hier wird der Heap verwendet, um die Priorität von Aufgaben zu verwalten. Aufgaben mit höchster Priorität (bzw. kleinstem/großtem Wert) können effizient aus der Warteschlange entnommen werden.
- **Heapsort**: Eine effiziente Methode, um eine unsortierte Liste zu sortieren.
- **Graphenalgorithmen**: Heaps werden in Algorithmen wie Dijkstra zur effizienten Verwaltung von Knoten in Graphen verwendet.

Heapsort ist ein beliebter Sortieralgorithmus, weil er sowohl in-place (ohne zusätzlichen Speicher) als auch effizient ist, mit einer garantierten Zeitkomplexität von $O(nlog⁡n)$