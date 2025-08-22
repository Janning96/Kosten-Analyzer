# Kosten Analyzer (v0.9)

**Tabs & Features**
- **Import (stabil, wie v0.7):** PDF → Excel → *Auto-Download* → Import in die lokale Master-Excel. Neue Transaktionen bekommen Kategorie **Default**.
- **Transaktionen:** Zeitraum-Filter (Von/Bis), Mehrfachauswahl (Checkboxen), **Kategorie zuweisen (Bulk)**, Einzelbearbeitung (Datum, Name, Beschreibung, Betrag), **Speichern** schreibt in Master-Excel (localStorage).
- **Analyse:** Benutzerdefinierte Zeiträume, Mehrfachauswahl von Monaten/Kategorien, **Balken** (Summe je Kategorie), **Kuchen** (Anteile), **Linie** (Trend je Monat).
- **Kategorien verwalten:** Hinzufügen/Löschen. Beim **Löschen** werden alle Transaktionen dieser Kategorie auf **Default** gesetzt.
- **Master-Excel:** Export-Button im Header, Schema: `ID | Bank | Datum | Name | Beschreibung | Betrag | Kategorie`.

**Ordnerstruktur**
```
docs/
  index.html
  README.md
  .nojekyll
  vercel.json
```

**Deployment (Vercel + GitHub)**
1. ZIP entpacken und **Inhalt** in dein Repo unter **`docs/`** hochladen.
2. Vercel → Project → Settings →
   - **Root Directory:** `docs`
   - **Build Command:** *(leer)*
   - **Output Directory:** `.`
3. Nach dem Deploy Seite öffnen.

**Nutzung**
- **Import-Tab:** PDF wählen → „PDF → Excel → Import“. Einzel-Excel wird automatisch heruntergeladen **und** Daten in die Master-Excel aufgenommen.
- **Transaktionen-Tab:** Zeitraum setzen → Checkboxen markieren → Dropdown „Kategorie“ → **Kategorie zuweisen**. Felder direkt editieren → **Änderungen speichern**.
- **Analyse-Tab:** Von/Bis, Monate & Kategorien wählen → **Analysieren**.

**Datenhaltung**
- Daten werden **lokal im Browser** gespeichert (localStorage). Exportiere die Master-Excel regelmäßig als Backup.
- „Reset (lokal)“ löscht DB & Kategorien (nur lokal) und setzt Standardkategorien zurück.

**Hinweise**
- Die Import-Heuristiken sind für die bereitgestellten Barclays-/N26-PDFs optimiert.
- Wenn ein PDF nicht erkannt wird: Debug aufklappen (Import-Tab) und den Textblock prüfen.
