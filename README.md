# Kosten Analyzer (docs/, v0.2)

**Fixes & Ergänzungen**:
- pdf.js **v3 UMD** + `GlobalWorkerOptions.workerSrc` → stabiler Worker‑Ladevorgang (kein ESM‑Import nötig).
- Barclays‑Parser: Abschnitt **„Umsatzübersicht“** bis **„Umsätze Visa Karten‑Nr“**, robust gegen Leerzeichen/Unicode‑Minus.
- **„Zuletzt ausgewählte Datei“** wird angezeigt.
- **Status‑Liste** je Datei: OK/Fehler + Nachricht (z. B. „0 Transaktionen erkannt“ oder konkrete Fehlermeldung).
- Fehlerpaneel oben, Debug‑Text sichtbar.
- Mehrfach‑Auswahl unterstützt; Import aggregiert alle Treffer.

**Veröffentlichen (GitHub Pages)**:
1) Repo anlegen ⇒ nur den `docs/`‑Ordner hochladen (hier: Inhalt aus diesem Paket).
2) Settings → Pages → Source = `/docs`.
3) Seite öffnen (HTTPS).

**Hinweis zu vorheriger v0.1**:
- v0.1 nutzte pdf.js **v4 (ES Modules)**. In einigen Browsern/Setups lädt der Worker dabei **nicht automatisch** von einem CDN (CORS/Module‑Worker). Der Wechsel auf v3 UMD + expliziten Worker‑Pfad beseitigt das Problem.

**Nächste Schritte**:
- N26‑Parser (DE, Tabellen‑PDF).
- Kategorien/Zeiträume/Dashboards, Persistenz (IndexedDB), Mehrfachauswahl/Hotkeys.
