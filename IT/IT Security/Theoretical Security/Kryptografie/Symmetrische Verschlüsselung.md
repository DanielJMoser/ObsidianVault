
-> Verschlüsselnder Key entschlüsselt auch.

Im Gegensatz zu: [[Asymmetrische Verschlüsselung]]

## Definition

Die **symmetrische Verschlüsselung** ist eine Methode der [[_Kryptografie|Kryptografie]], bei der für die Ver- und Entschlüsselung **derselbe** Schlüssel verwendet wird.
Dies bedeutet, dass sowohl der **Sender** als auch der **Empfänger** den **gleichen** geheimen Schlüssel besitzen müssen, um Nachrichten sicher auszutauschen.
Symmetrische Verschlüsselungsverfahren sind bekannt für ihre **Effizienz** und **Schnelligkeit**, was sie besonders für die Verschlüsselung großer Datenmengen geeignet macht.

## Funktionsweise

1. **Schlüsselerzeugung:**
   - Ein geheimer **Schlüssel** wird generiert, der von beiden Kommunikationspartnern geteilt wird.
   - Der Schlüssel muss sicher übertragen oder geteilt werden, um zu verhindern, dass unbefugte Dritte Zugriff erhalten.

2. **Verschlüsselung:**
   - Der Sender verschlüsselt die Klartextnachricht mithilfe des geheimen Schlüssels und eines symmetrischen Verschlüsselungsalgorithmus.
   - Das Ergebnis ist der **Ciphertext** (verschlüsselte Nachricht), der ohne den Schlüssel nicht lesbar ist.

3. **Übertragung:**
   - Der Ciphertext wird über einen unsicheren Kanal an den Empfänger gesendet.

4. **Entschlüsselung:**
   - Der Empfänger verwendet denselben geheimen Schlüssel und den entsprechenden Algorithmus, um den Ciphertext wieder in den Klartext umzuwandeln.

## Gängige symmetrische Verschlüsselungsalgorithmen

- **AES (Advanced Encryption Standard):**
  - Weit verbreiteter Standard, bekannt für seine Sicherheit und Effizienz.
  - Verwendet Schlüsselgrößen von 128, 192 oder 256 Bit.

- **DES (Data Encryption Standard):**
  - Älterer Standard mit einer Schlüsselgröße von 56 Bit.
  - Aufgrund seiner kurzen Schlüsselgröße gilt DES heute als unsicher.

- **3DES (Triple DES):**
  - Erweiterung von DES, bei der der Verschlüsselungsprozess dreimal mit unterschiedlichen Schlüsseln durchgeführt wird.
  - Erhöht die Sicherheit gegenüber einfachem DES.

- **RC4:**
  - Stream Cipher, der in bestimmten Anwendungen eingesetzt wurde, aber aufgrund von Schwächen in der Sicherheit heute weniger verwendet wird.

## Vorteile

- **Effizienz und Geschwindigkeit:**
  - Symmetrische Verschlüsselung ist schneller als asymmetrische Verfahren, was sie ideal für die Verschlüsselung großer Datenmengen macht.

- **Einfachheit:**
  - Die Verwendung eines einzigen Schlüssels vereinfacht den Verschlüsselungsprozess.

## Nachteile

- **Schlüsselverteilung:**
  - Das sichere Austauschen des geheimen Schlüssels zwischen Sender und Empfänger ist herausfordernd.
  - Wenn der Schlüssel während der Übertragung abgefangen wird, kann ein Angreifer die Kommunikation entschlüsseln.

- **Skalierbarkeit:**
  - In Netzwerken mit vielen Teilnehmern steigt die Anzahl der benötigten Schlüssel exponentiell an, was die Verwaltung erschwert.

## Anwendungsgebiete

- **Datenspeicherung:**
  - Verschlüsselung von Festplatten, Dateien oder Datenbanken zum Schutz vor unbefugtem Zugriff.

- **VPNs (Virtual Private Networks):**
  - Sicherung von Datenübertragungen über öffentliche Netzwerke.

- **Sichere Kommunikation:**
  - Verschlüsselung von Nachrichten in Kommunikationsprotokollen wie SSL/TLS (in Kombination mit asymmetrischer Verschlüsselung für den Schlüsselaustausch).

## Kombination mit asymmetrischer Verschlüsselung

Um die Probleme der Schlüsselverteilung zu lösen, wird symmetrische Verschlüsselung oft mit **asymmetrischer Verschlüsselung** kombiniert:

- **Schlüsselaustausch:**
  - Asymmetrische Verschlüsselung wird verwendet, um den symmetrischen Schlüssel sicher zu übertragen.
  - Nach dem Austausch wird die symmetrische Verschlüsselung für die eigentliche Datenübertragung verwendet.

- **Beispiel:**
  - **TLS/SSL-Protokolle** verwenden asymmetrische Verschlüsselung für die Aushandlung eines Sitzungsschlüssels und symmetrische Verschlüsselung für die eigentliche Datenübertragung.

## Zusammenfassung und Bedeutung

Die symmetrische Verschlüsselung ist ein grundlegendes Element der modernen IT-Security. Trotz ihrer Herausforderungen bei der Schlüsselverteilung bietet sie eine effiziente und sichere Methode zur Verschlüsselung großer Datenmengen. Durch die Kombination mit asymmetrischen Verfahren können ihre Schwächen kompensiert werden, was zu sicheren und performanten Kommunikationssystemen führt.

---

#ITsecurity
#kryptografie

