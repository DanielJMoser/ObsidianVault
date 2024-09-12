#C 

In C ermöglicht die dynamische Speicherverwaltung, Speicher zur **Laufzeit** zu **reservieren** und **freizugeben**. 
Dies ist besonders nützlich, wenn die **Größe** der benötigten Datenstrukturen zur Kompilierzeit **nicht bekannt** ist. Die dynamische Speicherverwaltung wird durch eine Reihe von Funktionen bereitgestellt, die in der Standardbibliothek `<stdlib.h>` definiert sind.
Wichtige Funktionen der dynamischen Speicherverwaltung:

## `malloc()`

Beschreibung: Reserviert eine bestimmte Menge an Speicher im Heap und gibt einen Zeiger auf den Anfang des reservierten Speicherblocks zurück. Der Speicher ist nicht initialisiert.

**Syntax**:

```c
void* malloc(size_t size);
```

**Beispiel**:

```C
int *array = (int*)malloc(10 * sizeof(int)); // Reserviert Speicher für ein Array von 10 Integern
if (array == NULL) {
    // Fehlerbehandlung, falls Speicherreservierung fehlschlägt
    printf("Speicherreservierung fehlgeschlagen!\n");
}
```


## `free()`

**Beschreibung**: Gibt den zuvor mit `malloc()`, `calloc()` oder `realloc()` reservierten Speicher wieder frei. Es ist wichtig, Speicher freizugeben, um Speicherlecks zu vermeiden.

**Syntax**:

```C
void free(void* ptr);
```


**Beispiel**:

```C
free(array); // Gibt den Speicher frei, der für array reserviert wurde
array = NULL; // Zeiger auf NULL setzen, um Dangling Pointer zu vermeiden

```

### `realloc()`

**Beschreibung**: Ändert die Größe eines bereits reservierten Speicherblocks. Dies kann nützlich sein, wenn sich die benötigte Größe eines Arrays zur Laufzeit ändert.

**Syntax**:

```C
void* realloc(void* ptr, size_t new_size);
```


**Beispiel**:

```C
array = (int*)realloc(array, 20 * sizeof(int)); // Ändert die Größe des Arrays auf 20 Integer
if (array == NULL) {
    // Fehlerbehandlung, falls Speicheränderung fehlschlägt
    printf("Speichervergrößerung fehlgeschlagen!\n");
}
```


## Wichtige Hinweise zur dynamischen Speicherverwaltung

- **Speicherlecks vermeiden**: Jeder mit `malloc()`, `calloc()` oder `realloc()` reservierte Speicherblock muss mit `free()` freigegeben werden, um Speicherlecks zu vermeiden.
- **Null-Zeiger setzen**: Nach dem Freigeben des Speichers sollte der Zeiger auf `NULL` gesetzt werden, um das Risiko von Dangling Pointern (Zeiger, die auf freigegebenen Speicher zeigen) zu minimieren.
- **Fehlerüberprüfung**: Bei jeder Speicherreservierung sollte überprüft werden, ob der zurückgegebene Zeiger `NULL` ist, was darauf hinweist, dass die Speicherreservierung fehlgeschlagen ist.


## Beispiel
Im folgenden Beispiel wird Speicher für ein Array zur **Laufzeit** reserviert, Werte werden **eingelesen** und **ausgegeben**, und schließlich wird der Speicher ordnungsgemäß **freigegeben**.

``` C
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Geben Sie die Anzahl der Elemente ein: ");
    scanf("%d", &n);

    // Speicher für n Integer reservieren
    int *array = (int*)malloc(n * sizeof(int));
    if (array == NULL) {
        printf("Speicherreservierung fehlgeschlagen!\n");
        return 1; // Beendet das Programm bei Speicherfehler
    }

    // Werte in das Array einlesen
    for (int i = 0; i < n; i++) {
        printf("Element %d: ", i + 1);
        scanf("%d", &array[i]);
    }

    // Array ausgeben
    printf("Eingegebene Elemente:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", array[i]);
    }

    // Speicher freigeben
    free(array);
    array = NULL; // Dangling Pointer vermeiden

    return 0;
}

```
