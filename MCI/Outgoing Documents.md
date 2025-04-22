## 2. Dokumenttypen und Prozessschritte

Folgende Dokumenttypen müssen im System verwaltet werden können:

### 2.1 Grant Agreement Phase

- **Grant Agreement Vorlage**: Wird vom System zur Verfügung gestellt, Student kann herunterladen
- **Grant Agreement Unterzeichnet**: Muss vom Studenten hochgeladen werden, setzt `egBeantragtAm` auf aktuelles Datum
- **Ankunftsbestätigung Vorlage**: Wird vom System zur Verfügung gestellt, Student kann herunterladen
- **Ankunftsbestätigung Ausgefüllt**: Muss vom Studenten hochgeladen werden, setzt `egAnkunftBestaetigtAm` auf aktuelles Datum
- **Aufenthaltsbestätigung Vorlage**: Wird vom System zur Verfügung gestellt, Student kann herunterladen
- **Aufenthaltsbestätigung Ausgefüllt**: Muss vom Studenten hochgeladen werden, setzt `egAufenthaltBestaetigtAm` auf aktuelles Datum
- **Green Travel Bestätigung**: Optional, wenn Green Travel beantragt wurde

#### Vom System zur Vefuegung gestellt:
- Vorlage Grant Agreement
- Vorlage Ankunftsbestaetigung
- Vorlage Aufenthaltsbestaetigung
- Vorlage Green Travel (?; optional)

#### Vom User hochgeladen:
- Ausgefuelltes Grant Agreement, setzt `egBeantragtAm` auf aktuelles Datum
- Ausgefuellte Ankunftsbestaetigung, setzt `egAnkunftBestaetigtAm` auf aktuelles Datum
- Ausgefuellte Aufenthaltsbestaetigung
- Ausgefuellte Green Travel-Bestaetigung (?; optional)


### 2.2 During Mobility Phase

- **Learning Agreement During Mobility**: Nach Änderungen der Kurse generiert, muss heruntergeladen werden können
- **Unterzeichnetes Learning Agreement During Mobility**: Muss vom Studenten hochgeladen werden, setzt `prozessSchritt` auf 15

### 2.3 After Mobility Phase

- **Learning Agreement After Mobility Vorlage**: Wird vom System zur Verfügung gestellt
- **Unterzeichnetes Learning Agreement After Mobility**: Muss vom Studenten hochgeladen werden, setzt `prozessSchritt` auf 18
- **Transcript of Records**: Muss vom Studenten hochgeladen werden
- **Tabelle F**: Wird nach Genehmigung vom System zur Verfügung gestellt
- **National Sheet**: Wird nach Genehmigung vom System zur Verfügung gestellt

## 3. Technische Anforderungen - Backend

### 3.1 Änderungen an `MyOutgoingController.java`

- Der bestehende Endpunkt `/outgoing/update` muss erweitert werden, um Multipart-Dateien zu akzeptieren
- Implementierung der Erkennung, ob die Anfrage eine Datei enthält (Content-Type enthält "multipart/form-data")
- Extraktion der hochgeladenen Datei und des Dokumenttyps aus der Anfrage
- Validierung der hochgeladenen Datei (Größe, Typ, etc.)
- Erstellung eines neuen `Dokument`-Objekts mit richtigen Metadaten (Person, Typ, Verfügbarkeit)
- Aktualisierung des zugehörigen `Outgoing`-Objekts basierend auf dem Dokumenttyp
    - Setzen relevanter Zeitstempel (wie `egBeantragtAm`, `egAnkunftBestaetigtAm`, etc.)
    - Aktualisierung des Prozessschritts, wenn erforderlich

### 3.2 Änderungen an `DokumentService.java`

- Keine signifikanten Änderungen notwendig, da die bestehenden Methoden ausreichend sind:
    - `saveOrUpdate` für die Speicherung neuer Dokumente
    - Bestehender Endpunkt `/dokument/{id}` für den Download

### 3.3 Änderungen an `createOutgoingData` Methode

- Die bestehende Methode muss erweitert werden, um alle relevanten Dokument-IDs in das `eg_docids`-Feld aufzunehmen
- Format: `"key1=value1;key2=value2"` für die verschiedenen Dokumenttypen
- Mapping der Dokument-IDs zu spezifischen Schlüsseln, die im Frontend verwendet werden
- Inklusion von Vorlagen-Dokumenten und hochgeladenen Dokumenten

### 3.4 Datenbankänderungen

- Keine Änderungen am Datenmodell erforderlich, da die `Dokument`-Entität bereits existiert
- Die Verknüpfung zwischen `Outgoing` und `Dokument` erfolgt über das `owner`-Feld in der `Dokument`-Entität

## 4. Technische Anforderungen - Frontend

### 4.1 Erweiterung von `outgoingService.ts`

- Implementierung einer neuen Methode `uploadDocument(outgoingId: number, documentType: string, file: File): Promise<boolean>`
- Die Methode soll FormData verwenden, um die Datei und Metadaten zum Backend zu senden
- Anpassung des Content-Types auf `multipart/form-data`
- Umbenennung der Methode `getDocumentById` zu `getDocumentDownloadUrl` für bessere Klarheit

### 4.2 Änderungen an `DocumentsUpAndDownloadPage.tsx`

- Implementierung der Dateiauswahl über einen Input-Typ "file"
- Anzeige des Fortschritts beim Hochladen
- Validierung der ausgewählten Datei (Größe, Typ, etc.)
- Aufrufen der `uploadDocument`-Methode beim Hochladen
- Aktualisierung der UI-Anzeige nach erfolgreichem Upload
- Behandlung von Fehlerfällen mit benutzerfreundlichen Meldungen

### 4.3 UI-Anforderungen

- Klare Trennung der verschiedenen Dokumenttypen in der UI
- Statusanzeige für jedes Dokument (nicht verfügbar, verfügbar, hochgeladen, genehmigt, etc.)
- Buttons zum Herunterladen vorhandener Dokumente
- Upload-Funktion mit Dateiauswahldialog
- Fortschrittsanzeige während des Uploads
- Visuelles Feedback nach erfolgreichem Upload oder bei Fehlern
- Responsives Design für verschiedene Gerätetypen

## 5. Sicherheitsanforderungen

### 5.1 Berechtigungsprüfung

- Prüfung, ob der aktuelle Benutzer berechtigt ist, auf die angeforderten Dokumente zuzugreifen
- Sicherstellung, dass Studierende nur ihre eigenen Dokumente sehen und verwalten können
- Keine direkten Dokument-IDs im Frontend sichtbar machen (Verschlüsselung oder Token-Basierter Zugriff)

### 5.2 Validierung

- Validierung der hochgeladenen Dateien (Größenbeschränkung, erlaubte Dateitypen)
- Sicherstellung, dass nur erwartete Dokumente in den entsprechenden Prozessschritten hochgeladen werden können
- CSRF-Schutz für den Upload-Prozess

## 6. Integrationspunkte

### 6.1 Benachrichtigungen

- Nach dem Hochladen bestimmter Dokumente müssen E-Mail-Benachrichtigungen an relevante Personen gesendet werden:
    - Bei Grant Agreement Upload an IRO
    - Bei Learning Agreement During Mobility Upload an Studiengang und IRO
    - Bei Learning Agreement After Mobility Upload an Studiengang und IRO

### 6.2 Prozessübergänge

- Aktualisierung des `prozessSchritt` in der `Outgoing`-Entität nach dem Hochladen bestimmter Dokumente
- Automatische Fortschreitung im Prozess nach bestimmten Dokument-Uploads