#Zeiger #Pointer

**Zeiger** (englisch: _Pointer_) sind Variablen, die **die Adresse eines anderen Speicherorts speichern**.

Anstatt einen direkten Wert zu halten, referenziert ein Zeiger eine Speicheradresse, an der Daten gespeichert sind. Zeiger sind ein zentrales Konzept in vielen Programmiersprachen, insbesondere in solchen, die direkten Zugriff auf Speicher erlauben, wie z.B. C und C++.

## Eigenschaften von Zeigern

- **Speichern von Adressen**: Ein Zeiger speichert die Adresse einer Variablen, eines Arrays oder eines anderen Speicherorts.
- **Dereferenzierung**: Durch Dereferenzierung eines Zeigers kann auf den Wert zugegriffen werden, der an der referenzierten Adresse gespeichert ist.
- **Typisierung**: Zeiger haben einen Typ, der angibt, auf welche Art von Daten sie zeigen (z.B. `int*` für einen Zeiger auf einen Integer).

## Verwendung von Zeigern

- **Arbeit mit Arrays und Strings**: Zeiger können genutzt werden, um durch Arrays oder Strings zu iterieren.
- **Dynamische Speicherverwaltung**: Zeiger sind essenziell für die dynamische Speicherverwaltung (z.B. `malloc` in C).
- **Funktionen**: Zeiger können genutzt werden, um Parameter an Funktionen als Referenz zu übergeben, was Änderungen am Originalwert ermöglicht.
- **Datenstrukturen**: Viele Datenstrukturen wie Listen, Bäume und Graphen basieren auf Zeigern.

## Beispiel in C

```clike
int x = 10;   // Eine Variable x mit dem Wert 10
int *p = &x;  // Ein Zeiger p, der die Adresse von x speichert

printf("%d", *p);  // Ausgabe: 10 (Wert von x über Dereferenzierung des Zeigers p)

```

## Wichtige Begriffe

- **Nullzeiger (`NULL`)**: Ein spezieller Zeiger, der auf keinen gültigen Speicherort zeigt.
- **Zeigerarithmetik**: Operationen, die auf Zeigern durchgeführt werden können, um Speicheradressen zu manipulieren.
- **Dereferenzierung**: Zugriff auf den Wert, auf den ein Zeiger zeigt, mittels des Dereferenzierungsoperators (`*`).

## Vorteile von Zeigern

- Direkter Zugriff auf Speicher, was effizient und flexibel ist.
- Ermöglicht die Implementierung von Datenstrukturen wie verketteten Listen, Bäumen und Graphen.

## Gefahren und Herausforderungen

- **Speicherlecks**: Wenn Speicher zugewiesen, aber nicht freigegeben wird.
- **Dereferenzierung eines Nullzeigers**: Führt zu Laufzeitfehlern und Abstürzen.
- **Ungültige Zeiger**: Zeiger, die auf freigegebenen oder ungültigen Speicher zeigen, können unvorhersehbares Verhalten verursachen.