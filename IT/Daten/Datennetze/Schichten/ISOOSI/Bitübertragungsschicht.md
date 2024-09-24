#Datennetze 

Die Bitübertragungsschicht (1. Schicht im OSI-Modell) ist die unterste Schicht und verantwortlich für die physikalische Übertragung von Rohdatenbits über ein physisches Übertragungsmedium. Sie definiert die Methoden und Verfahren zur Übertragung der binären Daten in Form von elektrischen, optischen oder elektromagnetischen Signalen.

---

## Hauptaufgaben der Bitübertragungsschicht

### Physikalische Übertragung von Signalen

- Die Bitübertragungsschicht wandelt die Daten in physikalische Signale um, die über ein Übertragungsmedium wie Kupferkabel, Glasfaser oder drahtlose Verbindungen (Funk, Infrarot, etc.) übertragen werden.
- Die Signale können in verschiedenen Formen auftreten, wie z.B. elektrische Spannungen, Lichtimpulse oder Funkwellen.

### Übertragungsmedium

- Verschiedene physikalische Medien haben unterschiedliche Eigenschaften und beeinflussen die Geschwindigkeit, Zuverlässigkeit und Reichweite der Datenübertragung.
- Typische Medien sind:
  - **Kupferkabel** (z.B. Twisted Pair, Koaxialkabel)
  - **Glasfaserkabel**
  - **Drahtlose Übertragungen** (z.B. WLAN, Bluetooth)

### Modulation und Codierung

- Um die Daten effizient zu übertragen, werden sie durch **Modulation** und **Codierung** in Signale umgewandelt. Modulationsarten wie **Amplitude Shift Keying (ASK)**, **Frequency Shift Keying (FSK)** oder **Phase Shift Keying (PSK)** werden verwendet, um digitale Informationen auf ein Trägersignal aufzubringen.

### Taktung und Synchronisation

- Die Bitübertragungsschicht sorgt für die Synchronisation des Senders und Empfängers, sodass die Daten in einer konsistenten Reihenfolge interpretiert werden können.
- Es gibt zwei Arten der Taktung:
  - **Synchron**: Die Übertragung erfolgt mit einem gemeinsamen Takt zwischen Sender und Empfänger.
  - **Asynchron**: Die Übertragung erfolgt ohne gemeinsamen Takt, stattdessen werden Start- und Stop-Bits verwendet.

---

## Signalstörungen und Fehler

- Während der Übertragung können **Rauschen**, **Dämpfung** und **Interferenzen** die Signale beeinflussen. Die Bitübertragungsschicht versucht, diese Störungen so weit wie möglich zu minimieren.
- Typische Maßnahmen zur Fehlererkennung und -korrektur auf höheren Schichten (wie die **Prüfsummenprüfung**) bauen auf den Fähigkeiten der Bitübertragungsschicht auf.

---

## Bandbreite und Datenrate

- **Bandbreite** bezeichnet die maximale Datenmenge, die über ein Übertragungsmedium in einer bestimmten Zeitspanne übertragen werden kann, während die **Datenrate** die tatsächlich erzielte Übertragungsrate darstellt.
- Die physikalischen Eigenschaften des Mediums und die eingesetzten Technologien bestimmen die Bandbreite.

---

## Wichtige Technologien der Bitübertragungsschicht

### Ethernet (IEEE 802.3)

- Ethernet ist eine weitverbreitete Technologie für kabelgebundene Netzwerke, die auf der Bitübertragungsschicht und der Sicherungsschicht arbeitet. Die Bitübertragungsschicht sorgt hier für die physikalische Übertragung der Ethernet-Frames über Kupfer- oder Glasfaserkabel.

### WLAN (IEEE 802.11)

- WLAN arbeitet sowohl auf der Bitübertragungsschicht als auch auf der Sicherungsschicht. Die Bitübertragungsschicht sorgt hier für die drahtlose Übertragung der Daten mittels Funkwellen.

---

## Multiplexing

- **Multiplexing** ist eine Methode, um mehrere Signale über eine gemeinsame Leitung zu übertragen. Dies geschieht durch das Aufteilen des Übertragungskanals in mehrere Subkanäle:
  - **Frequenzmultiplex (FDM)**: Verschiedene Signale werden auf unterschiedlichen Frequenzen übertragen.
  - **Zeitmultiplex (TDM)**: Verschiedene Signale werden nacheinander in bestimmten Zeitfenstern übertragen.

---

## Standardisierungen

- Standards für die Bitübertragungsschicht werden von Organisationen wie der **IEEE** (z.B. Ethernet-Standards) oder der **ITU** (z.B. DSL-Standards) entwickelt, um die Kompatibilität zwischen verschiedenen Geräten sicherzustellen.

siehe: [[Vermittlungsschicht]] für die darüberliegende Schicht im OSI-Modell.
