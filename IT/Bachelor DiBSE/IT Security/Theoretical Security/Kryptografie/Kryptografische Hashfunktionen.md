1. **Determinismus:**
   - Die Hashfunktion muss für dieselbe Eingabe immer den gleichen Hash-Wert (Ausgabe) erzeugen. Das bedeutet, wenn du dieselben Daten mehrmals in die Funktion eingibst, erhältst du immer das gleiche Ergebnis.

2. **Effizienz:**
   - Die Berechnung des Hash-Werts für eine beliebige Eingabe sollte schnell und effizient durchführbar sein, unabhängig von der Größe der Eingabe. Dies ist besonders wichtig bei großen Datenmengen.

3. **Vorwärts-Sicherheit (Preimage-Resistenz):**
   - Es muss praktisch unmöglich sein, aus einem gegebenen Hash-Wert die ursprüngliche Eingabe (den Preimage) zu berechnen. Wenn ein Hash-Wert $h = H(x)$ bekannt ist, sollte es extrem schwierig sein, $x$ zu finden, das diese Bedingung erfüllt.

4. **Schwache Kollisionsresistenz (Second Preimage-Resistenz):**
   - Es sollte extrem schwer sein, für eine gegebene Eingabe $x_1$ eine zweite Eingabe $x_2$ zu finden, sodass $H(x_1) = H(x_2)$. Das bedeutet, dass zwei unterschiedliche Eingaben nicht denselben Hash-Wert erzeugen sollten.

5. **Starke Kollisionsresistenz (Collision-Resistenz):**
   - Es muss extrem schwierig sein, **zwei verschiedene** Eingaben $x_1$ und $x_2$ zu finden, sodass $H(x_1) = H(x_2)$. Das bedeutet, es sollte keine zwei unterschiedlichen Nachrichten geben, die denselben Hash-Wert haben.

6. **Avalanche-Effekt:**
   - Eine kleine Änderung in der Eingabe (z. B. Ändern eines Bits) sollte zu einer erheblichen und scheinbar zufälligen Änderung des Hash-Werts führen. Selbst minimale Änderungen der Eingabe sollten den Hash vollständig verändern.

7. **Pseudorandomness:**
   - Der Hash-Wert sollte wie eine zufällige Zeichenkette aussehen. Es sollte keine erkennbaren Muster oder Struktur im Hash-Wert geben, die auf die Eingabedaten schließen lassen.

8. **Länge der Ausgabe (Fixed Output Length):**
   - Unabhängig von der Größe der Eingabe sollte der Hash-Wert eine feste Länge haben. In der Regel beträgt diese Länge 256 oder 512 Bits, abhängig von der verwendeten Hashfunktion (z. B. SHA-256 oder SHA-512).

## Beispiele für kryptografische Hashfunktionen:

- **SHA-256 (Secure Hash Algorithm 256-bit)**
- **SHA-3 (neuere Version von SHA, basiert auf Keccak)**
- **RIPEMD-160**
- **BLAKE2**

Diese Funktionen erfüllen die oben genannten Anforderungen und werden häufig in sicherheitskritischen Anwendungen verwendet.
