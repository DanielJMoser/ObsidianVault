

-> Key zur Ver- und Entschlüsselung unterschiedlich.

Im Gegensatz zu: [[_Symmetrische Verschlüsselung]]

**Zur Verschlüsselung**: _Public Key_
**Zur Entschlüsselung**: _Private Key_

## Definition

Die **asymmetrische Verschlüsselung**, auch bekannt als **Public-Key-Kryptographie**, ist ein kryptographisches Verfahren, bei dem zwei unterschiedliche, aber mathematisch miteinander verbundene Schlüssel verwendet werden: ein **öffentlicher Schlüssel** zum Verschlüsseln und ein **privater Schlüssel** zum Entschlüsseln. Dieses Verfahren ermöglicht es, sichere Kommunikation zu gewährleisten, ohne dass die Kommunikationspartner zuvor einen gemeinsamen geheimen Schlüssel austauschen müssen.

## Funktionsweise

1. **Schlüsselerzeugung:**
   - Ein Benutzer erzeugt ein **Schlüsselpaar**, bestehend aus einem **öffentlichen Schlüssel** und einem **privaten Schlüssel**.
   - Der **öffentliche Schlüssel** wird frei verteilt, während der **private Schlüssel** geheim gehalten wird.

2. **Verschlüsselung:**
   - Der Sender verwendet den **öffentlichen Schlüssel** des Empfängers, um die Nachricht zu verschlüsseln.
   - Die verschlüsselte Nachricht kann sicher über einen unsicheren Kanal gesendet werden.

3. **Entschlüsselung:**
   - Der Empfänger verwendet seinen **privaten Schlüssel**, um die Nachricht zu entschlüsseln.
   - Nur der Besitzer des privaten Schlüssels kann die Nachricht lesen, selbst wenn der öffentliche Schlüssel allgemein bekannt ist.

### Beispiel:

- **Alice** möchte eine sichere Nachricht an **Bob** senden.
- Bob generiert ein Schlüsselpaar und gibt seinen **öffentlichen Schlüssel** an Alice weiter.
- Alice verschlüsselt ihre Nachricht mit Bobs öffentlichem Schlüssel und sendet sie an Bob.
- Bob entschlüsselt die Nachricht mit seinem **privaten Schlüssel**.

## Gängige asymmetrische Verschlüsselungsalgorithmen

- **RSA (Rivest-Shamir-Adleman):**
  - Einer der bekanntesten Algorithmen, basiert auf der Schwierigkeit der Faktorisierung großer Zahlen.
  - Schlüsselgrößen typischerweise 1024 bis 4096 Bit.

- **ECC (Elliptic Curve Cryptography):**
  - Basiert auf der Algebra **elliptischer Kurven** über endlichen Feldern.
  - Bietet bei kleineren Schlüssellängen vergleichbare Sicherheit wie RSA.

- **DSA (Digital Signature Algorithm):**
  - Speziell für **digitale Signaturen** entwickelt, basiert auf diskreten Logarithmen.

- **Diffie-Hellman-Schlüsselaustausch:**
  - Ein Verfahren zum sicheren Austausch von Schlüsseln über einen unsicheren Kanal.

## Vorteile

- **Keine Verteilung des privaten Schlüssels notwendig:**
  - Der **öffentliche Schlüssel** kann frei verteilt werden, was die Schlüsselverwaltung erleichtert.

- **Unterstützung digitaler Signaturen:**
  - Ermöglicht die **Authentifizierung** und **Integrität** von Nachrichten.

- **Skalierbarkeit:**
  - In großen Netzwerken reduziert sich der Bedarf an der Anzahl der Schlüsselpaare.

## Nachteile

- **Leistungseinbußen:**
  - Asymmetrische Verschlüsselung ist **langsamer** als symmetrische Verfahren, insbesondere bei großen Datenmengen.

- **Komplexität:**
  - Mathematisch komplexere Algorithmen können anfälliger für Implementierungsfehler sein.

- **Sicherheit abhängig von Schlüsselgröße:**
  - Erfordert größere Schlüssel für vergleichbare Sicherheit gegenüber symmetrischer Verschlüsselung.

## Anwendungsgebiete

- **Sichere Schlüsselverteilung:**
  - **Übertragung symmetrischer Schlüssel** für die Verwendung in symmetrischen Verschlüsselungsverfahren.

- **Digitale Signaturen:**
  - **Authentifizierung** von Benutzern und **Integrität** von Nachrichten.

- **SSL/TLS-Protokolle:**
  - Sicherung der Kommunikation über das Internet (z. B. bei HTTPS).

- **E-Mail-Verschlüsselung:**
  - **PGP** (Pretty Good Privacy) und **S/MIME** nutzen asymmetrische Verfahren zur E-Mail-Sicherheit.

## Kombination mit symmetrischer Verschlüsselung

- **Hybride Verschlüsselungssysteme:**
  - Kombinieren die Vorteile von symmetrischer und asymmetrischer Verschlüsselung.
  - **Symmetrische Verschlüsselung** für die eigentliche Datenübertragung (schneller).
  - **Asymmetrische Verschlüsselung** für den sicheren Austausch der symmetrischen Schlüssel.

- **Beispiel:**
  - **SSL/TLS-Protokolle** verwenden asymmetrische Verfahren für den Schlüsselaustausch und symmetrische Verfahren für die Datenübertragung.

## Zusammenfassung und Bedeutung

Die **asymmetrische Verschlüsselung** ist ein grundlegendes Element der modernen *IT-Security*. Sie ermöglicht sichere Kommunikation und **Authentifizierung** ohne vorherigen Schlüsselaustausch. Trotz ihrer geringeren Effizienz gegenüber symmetrischen Verfahren ist sie unerlässlich für sichere Schlüsselverteilung und **digitale Signaturen**. In Kombination mit symmetrischen Verfahren bietet sie eine leistungsfähige und sichere Grundlage für viele Anwendungen im Internet und in der digitalen Kommunikation.

---

#ITsecurity 
#kryptografie


