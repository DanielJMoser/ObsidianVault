#C
**I/O (Input/Output)** in C bezieht sich auf die Ein- und Ausgabeoperationen, die es ermöglichen, Daten von externen Quellen (wie Tastatur, Dateien) einzulesen und Daten an Ausgabegeräte (wie Bildschirm, Dateien) zu senden. C bietet eine Reihe von Funktionen zur Durchführung von I/O-Operationen, die in der Standardbibliothek `<stdio.h>` definiert sind.

## Einfache Ein- und Ausgabe

### Standardausgabe (`printf`)

- **`printf`**: Wird verwendet, um formatierte Daten an die Standardausgabe (normalerweise der Bildschirm) zu senden.
  
  **Syntax**:
  ```clike
  printf("Formatstring", Argumente...);
  ```
  
  **Beispiel**:
    ```clike
 int num = 10;
 printf("Die Zahl ist: %d\n", num); // Ausgabe: Die Zahl ist: 10
  ```


### Standardeingabe (`scanf`)

- **`scanf`**: Liest formatierte Eingaben von der Standard-Eingabe (normalerweise die Tastatur).
  
  ```clike
  `scanf("Formatstring", &Variable);`
  ```

```clike
int num;
printf("Geben Sie eine Zahl ein: ");
scanf("%d", &num); // Benutzer gibt eine Zahl ein, die in num gespeichert wird
```

## Arbeiten mit Dateien (Dateideskriptoren)

### Öffnen und Schließen von Dateien

- **`fopen`**: Öffnet eine Datei und gibt einen Zeiger auf den Dateistream zurück.
  
  ```clike
  FILE *file = fopen("datei.txt", "r"); // "r" für Lesen, "w" für Schreiben, "a" für Anhängen
  fclose(file)
  ```
  
### Lesen und Schreiben in Dateien

- **`fscanf` und `fprintf`**: Entsprechende Funktionen zu `scanf` und `printf`, aber für Dateien.
  
  ```clike
	char buffer[100];
	FILE *file = fopen("daten.txt", "r");
		if (file != NULL) {
	    fgets(buffer, 100, file); // Liest eine Zeile aus der Datei
	    fclose(file);
	}
  ```

## Standard I/O Funktionen

- **`getchar` und `putchar`**: Lesen und Schreiben eines einzelnen Zeichens.
  
  ```clike
	char c;
	printf("Geben Sie ein Zeichen ein: ");
	c = getchar(); // Liest ein Zeichen
	putchar(c);    // Gibt das Zeichen aus

  ```
  