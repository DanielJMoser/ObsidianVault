## Definition

Eine **digitale Signatur** ist ein kryptographisches Verfahren, das die **Authentizität**, **Integrität** und **Nicht-Abstreitbarkeit** einer digitalen Nachricht oder eines Dokuments gewährleistet. Sie ermöglicht es dem Empfänger, die Identität des Absenders zu verifizieren und sicherzustellen, dass die Nachricht während der Übertragung nicht manipuliert wurde.

## Funktionsweise

Digitale Signaturen basieren auf **[[Asymmetrische Verschlüsselung|asymmetrischer Verschlüsselung]]** und verwenden ein Schlüsselpaar aus **privatem** und **öffentlichem Schlüssel**:

1. **Erstellung der Signatur:**
   - Der Sender erstellt einen **Hashwert** (eine Prüfsumme) der Nachricht mittels einer **Hash-Funktion**.
   - Dieser Hashwert wird mit dem **privaten Schlüssel** des Senders verschlüsselt und bildet die digitale Signatur.

2. **Versand:**
   - Die ursprüngliche Nachricht wird zusammen mit der digitalen Signatur an den Empfänger gesendet.

3. **Verifikation:**
   - Der Empfänger entschlüsselt die digitale Signatur mit dem **öffentlichen Schlüssel** des Senders, um den ursprünglichen Hashwert zu erhalten.
   - Der Empfänger erstellt selbst einen Hashwert der erhaltenen Nachricht.
   - Beide Hashwerte werden verglichen. Stimmen sie überein, ist die **Integrität** der Nachricht gewährleistet, und die **Authentizität** des Senders wird bestätigt.

## Eigenschaften

- **Authentizität:** Bestätigung der Identität des Senders.
- **Integrität:** Gewährleistung, dass die Nachricht nicht verändert wurde.
- **Nicht-Abstreitbarkeit:** Der Sender kann die Urheberschaft der Nachricht nicht leugnen.

## Vorteile

- **Sicherheit:** Schutz vor Manipulation und Identitätsdiebstahl.
- **Vertrauen:** Stärkt das Vertrauen zwischen Kommunikationspartnern.
- **Rechtliche Gültigkeit:** In vielen Ländern sind digitale Signaturen rechtlich anerkannt und haben die gleiche Verbindlichkeit wie handschriftliche Unterschriften.

## Nachteile

- **Komplexität:** Implementierung und Verwaltung können technisch anspruchsvoll sein.
- **Schlüsselverwaltung:** Sichere Speicherung und Handhabung der privaten Schlüssel ist kritisch.
- **Abhängigkeit von Zertifizierungsstellen:** Vertrautheit auf externe **Zertifizierungsstellen** (Certificate Authorities) für die Validierung öffentlicher Schlüssel.

## Anwendungsgebiete

- **E-Mail-Sicherheit:** Sicherung und Signierung von E-Mails (z. B. mit **S/MIME** oder **PGP**).
- **Software-Verteilung:** Signierung von Softwarepaketen zur Verifizierung der Quelle (z. B. bei Updates).
- **Elektronische Verträge:** Rechtlich bindende digitale Unterzeichnungen von Dokumenten.
- **Blockchain-Technologie:** Verifikation von Transaktionen in Kryptowährungen.

## Zusammenfassung und Bedeutung

**Digitale Signaturen** sind ein unverzichtbares Werkzeug in der modernen *IT-Security*, um die Sicherheit und Vertrauenswürdigkeit digitaler Kommunikation und Transaktionen zu gewährleisten. Sie bieten einen hohen Grad an Sicherheit, indem sie die **Authentizität** des Absenders bestätigen und die **Integrität** der übermittelten Daten sicherstellen. Trotz einiger Herausforderungen bei der Implementierung sind digitale Signaturen weit verbreitet und bilden die Grundlage für viele sichere Online-Anwendungen.

---

#ITsecurity
#kryptografie
