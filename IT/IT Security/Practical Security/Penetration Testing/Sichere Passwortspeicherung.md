## Definition

Die **sichere Passwortspeicherung** bezieht sich auf Methoden und Praktiken, die sicherstellen, dass Passwörter in Systemen und Anwendungen so gespeichert werden, dass sie vor unautorisiertem Zugriff und Missbrauch geschützt sind. 
Da Passwörter oft das primäre Mittel zur **Authentifizierung** von Benutzern sind, ist ihre sichere Handhabung essenziell für die *IT-Security*.

## Best Practices für die sichere Passwortspeicherung

1. **Verwendung kryptographischer Hash-Funktionen:**

   - [[Funktionsweise Hashing|Hashing]] ist ein Prozess, bei dem ein Passwort durch eine Hash-Funktion in eine feste Länge von Zeichen umgewandelt wird.
   - Es ist wichtig, **kryptographisch sichere [[Hashfunktion|Hashfunktionen]]** zu verwenden, wie z. B. **bcrypt**, **scrypt** oder **Argon2**.
   - Veraltete Funktionen wie **MD5** oder **SHA-1** gelten als unsicher und sollten vermieden werden.

2. **Salting:**

   - Ein **Salt** ist ein zufälliger Wert, der zu jedem Passwort hinzugefügt wird, bevor es gehasht wird.
   - **Salts** verhindern, dass zwei gleiche Passwörter zu identischen Hashes führen.
   - Dies schützt gegen **Rainbow-Table-Angriffe**, bei denen vorgefertigte Tabellen verwendet werden, um Hashes zurück in Passwörter umzuwandeln.

3. **Peppering:**

   - Ein **Pepper** ist ein geheimer Wert, der zusätzlich zum Salt verwendet wird, aber nicht in der Datenbank gespeichert wird.
   - Der Pepper erhöht die Sicherheit weiter, sollte jedoch sicher aufbewahrt werden, z. B. in einer separaten Konfigurationsdatei.

4. **Verwendung von Schlüsselableitungsfunktionen:**

   - Funktionen wie **PBKDF2**, **bcrypt**, **scrypt** oder **Argon2** sind speziell für die sichere Passwortspeicherung entwickelt.
   - Sie sind ressourcenintensiv und erhöhen den Aufwand für **Brute-Force-Angriffe** erheblich.

5. **Mehrfache Iterationen:**

   - Durch wiederholtes Anwenden der Hash-Funktion (mehrere Iterationen) wird die Berechnungszeit erhöht.
   - Dies erschwert es Angreifern, viele Passwörter in kurzer Zeit zu testen.

6. **Keine Speicherung von Klartextpasswörtern:**

   - **Passwörter niemals im Klartext speichern**.
   - Auch reversible Verschlüsselung sollte vermieden werden, da der Schlüssel kompromittiert werden könnte.

7. **Regelmäßige Aktualisierung der Sicherheitsverfahren:**

   - Sicherheitsstandards entwickeln sich weiter; daher sollten Verfahren regelmäßig überprüft und aktualisiert werden.
   - Sicherheitsupdates für verwendete Bibliotheken und Tools sollten zeitnah eingespielt werden.

8. **Eingabevalidierung und Passwortregeln:**

   - Implementierung von **Passwortrichtlinien**, die Mindestlänge und Komplexität vorschreiben.
   - Verhindern von **SQL-Injection** oder anderen Angriffen durch sichere Eingabevalidierung.

## Risiken bei unsicherer Passwortspeicherung

- **Datenbankkompromittierung:**

  - Wenn Passwörter unsicher gespeichert werden, können Angreifer bei einem Datenbankleck die Passwörter leicht entschlüsseln.

- **Brute-Force- und Wörterbuchangriffe:**

  - Ohne ausreichende Schutzmaßnahmen können Angreifer systematisch Passwörter ausprobieren und erraten.

- **Identitätsdiebstahl und Betrug:**

  - Kompromittierte Passwörter können zu unautorisiertem Zugriff auf Benutzerkonten führen, was schwerwiegende Folgen haben kann.

## Bedeutung

Die sichere Passwortspeicherung ist ein kritischer Aspekt der **IT-Security**. Sie schützt nicht nur die Benutzer, sondern auch die Reputation und Integrität des Unternehmens oder der Organisation. Durch die Implementierung bewährter Sicherheitspraktiken kann das Risiko von Sicherheitsverletzungen erheblich reduziert werden.

## Zusammenfassung

Die Umsetzung von **Best Practices** bei der Passwortspeicherung ist unerlässlich, um die Sicherheit von Benutzerdaten zu gewährleisten. Durch den Einsatz von starken Hash-Funktionen, Salting, Peppering und regelmäßigen Sicherheitsüberprüfungen können Organisationen ihre Systeme gegen eine Vielzahl von Angriffen schützen.

---

#ITsecurity
