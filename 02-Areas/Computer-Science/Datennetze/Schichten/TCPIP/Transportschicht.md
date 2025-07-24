Die Transportschicht (4. Schicht im OSI-Modell) ist verantwortlich für die Ende-zu-Ende-Kommunikation zwischen zwei Geräten und sorgt für eine zuverlässige oder unzuverlässige Datenübertragung, je nach verwendetem Protokoll.

---

## Funktionen der Transportschicht

### Verbindungsaufbau und -abbau

- Sorgt für den Aufbau, die Aufrechterhaltung und den ordnungsgemäßen Abbau von Verbindungen zwischen Sender und Empfänger.

### Zuverlässigkeit der Übertragung

- Die Transportschicht stellt sicher, dass Datenpakete vollständig und in der richtigen Reihenfolge ankommen (bei verbindungsorientierten Protokollen wie TCP).

### Flusskontrolle

- Verhindert, dass der Sender den Empfänger mit mehr Daten überlastet, als dieser verarbeiten kann.

### Fehlerkontrolle

- Durch Prüfungen wie Checksummen wird sichergestellt, dass übertragene Daten fehlerfrei empfangen wurden.

---

## Wichtige Protokolle der Transportschicht

### Transmission Control Protocol (TCP)

- Verbindungsorientiertes Protokoll
- Sorgt für eine zuverlässige Datenübertragung, indem es eine **Verbindung** zwischen Sender und Empfänger aufbaut, Datenpakete nummeriert, bestätigte Pakete erneut sendet und die Reihenfolge beim Empfang überprüft.
- **Verwendung**: Web-Anwendungen (HTTP/HTTPS), E-Mail (SMTP), Dateiübertragungen (FTP)

### User Datagram Protocol (UDP)

- Verbindungsloses Protokoll
- Bietet eine **unzuverlässige** Übertragung ohne Garantie für die Reihenfolge oder den erfolgreichen Empfang der Datenpakete.
- **Verwendung**: Echtzeitanwendungen wie Video- und Sprachübertragung (VoIP), Online-Gaming, DNS-Abfragen

---

## Segmentierung

- Die Transportschicht teilt Daten in kleinere Einheiten, sogenannte **Segmente**, auf. Jedes Segment wird in einen **IP-Paket** eingebettet und durch die unteren Schichten weitergeleitet.
- Das **Sequence Number**-Feld in TCP-Segmenten wird verwendet, um die Reihenfolge der Segmente sicherzustellen.

---

## Portnummern

- **Portnummern** dienen zur Identifikation von Anwendungen auf einem Gerät. Dadurch kann die Transportschicht bestimmen, welche Anwendung ein bestimmtes Datenpaket erhalten soll.
- **Well-known Ports**: Standardisierte Ports für häufig genutzte Protokolle (z.B. Port 80 für HTTP, Port 443 für HTTPS).

---

## Flusskontrolle (TCP)

- Das **Window Size**-Feld im TCP-Header gibt die maximale Anzahl von Bytes an, die der Empfänger in einem bestimmten Zeitraum verarbeiten kann.
- **Sliding Window**-Mechanismus: Sorgt für eine dynamische Anpassung der Datenübertragungsgeschwindigkeit zwischen Sender und Empfänger.

siehe: [[ISO-OSI-Referenzmodell]] für eine Übersicht über alle Schichten des OSI-Modells.
