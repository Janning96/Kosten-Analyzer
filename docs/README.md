# Kosten Analyzer (docs/)

Minimaler Start für die App (v0.1):
- **docs/**-Ordner ist direkt für GitHub Pages nutzbar.
- Import von **Barclays**-PDFs (DE).
- Zeigt erkannte Transaktionen in einer Tabelle, bewegt Einträge via Minus/Plus zwischen zwei Tabellen.
- Exportiert verbleibende Einträge als CSV.

## Veröffentlichen
1. Neues GitHub-Repository anlegen.
2. Den gesamten `docs/` Ordner hochladen.
3. In den Repository-Settings **Pages** aktivieren und Source auf **/docs** stellen.

## Nutzung
- PDF wählen → **Import**
- Minus **−** verschiebt Eintrag in *Ausgeschlossen*.
- Plus **+** holt ihn zurück.
- **CSV exportieren** speichert nur die *Importliste*.

## Parser-Details
- Erkannt werden Zeilen mit **Belegdatum** + **Valutadatum** + **Beschreibung** + **Betrag** (z. B. `13.07.2025 14.07.2025 … 23,00-`).
- **Ignoriert**: `Gutschrift Manuelle Lastschrift` (Geschäftsregel).
- Normalisiert: Dezimaltrennzeichen, Unicode-Minus, AIRBNB-Codes (`AIRBNB * ABC…` → `AIRBNB`), Anhänge wie `DE Visa`.
- Segmentiert ausschließlich den Bereich **Umsatzübersicht** bis **Umsätze Visa Karten-Nr**, damit Hinweise/„Ratenkauf“-Listen nicht fälschlich geparst werden.

## Nächste Schritte
- N26-Parser (deutsche PDF, Tabellenstrukturen).
- Kategorien, Zeitfilter, Dashboards/Trends.
- Persistenz (LocalStorage/IndexedDB), Mehrfachauswahl.
