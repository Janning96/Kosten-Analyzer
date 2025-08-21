# Kosten Analyzer (docs/, v0.3)

**Änderungen für zuverlässige Dateiauswahl & Debugging:**

- **iOS/Safari-sicher:** Sichtbarer `<label for="pdfInput">` plus echtes `<input type="file">` (nicht `display:none`). Programmatic `click()`-Workarounds sind auf iOS unzuverlässig – dieser Weg ist robust.
- **Button-Diagnose:** Anzeige, ob der **Import-Button-Listener** korrekt verdrahtet ist und ob das **Dateiwechsel-Event** ausgelöst wurde.
- **Per-Datei-Statusliste** (OK/Fehler) + **„Zuletzt ausgewählte Datei“**.
- Weiterhin: pdf.js **v3 UMD** + `GlobalWorkerOptions.workerSrc`, Barclays-Parser mit Abschnitts-Segmentierung und Business-Regel.

**Anleitung:**  
- Klicke auf **„📎 PDF(s) auswählen“** oder direkt ins Dateifeld → wähle deine Barclays-PDF.  
- Prüfe unten **Diag**: „Import-Button: OK | Dateiwechsel-Event: OK“.  
- Klicke **Import**. Treffer erscheinen in der Tabelle; Fehler stehen in der Statusliste.

