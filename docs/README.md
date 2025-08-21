# Kosten Analyzer (docs/, v0.4)

**Neu:** Getrennte Buttons & Parser für **Barclays** und **N26**. Je Bank: **Zuletzt gewählte Datei** + **Statusliste**.
- **Barclays‑Parser (DE):** Abschnitt „Umsatzübersicht“ bis „Umsätze Visa Karten‑Nr“, Beträge mit ±, ignoriert „Gutschrift Manuelle Lastschrift“, Unicode‑Minus / NBSP normalisiert, AIRBNB‑Codes, „DE/LU/IE Visa“‑Suffixe entfernt.
- **N26‑Parser (DE):** zeilenbasiert, erkennt Kombinationen, in denen **Datum** und **Betrag** in **derselben Zeile** vorkommen; der **Rest** der Zeile wird als **Beschreibung** verwendet. Betragszeichen vor/nach dem Wert werden berücksichtigt (`-123,45` oder `123,45-`). **Regel:** Zeilen, deren Beschreibung „Barclays“ enthält, werden **ignoriert**. Unicode‑Minus & NBSP werden normalisiert.

**Stabilität:**
- **pdf.js v3 (UMD)** mit explizitem `GlobalWorkerOptions.workerSrc` → gut für GitHub Pages & iOS/Safari.
- `.nojekyll` verhindert Eingriffe des Jekyll‑Builders.

**CSV‑Export:** `Bank;Quelle;Belegdatum;Valutadatum;Beschreibung;Betrag` mit BOM (`;` als Trennzeichen).

**Veröffentlichung:**
1) Repo → `docs/` Inhalt aus dieser ZIP hochladen/ersetzen.
2) Settings → Pages → Branch = `main`, Folder = `/docs`.
3) Optional: Deployments → `github-pages` → Redeploy (oder mini‑Commit).

**Nächste Schritte:**
- N26‑PDF‑Beispiele testen; ggf. RegEx feintunen (weitere Kopfzeilen ignorieren, zweites Datum erkennen).
- Kategorien/Zeiträume/Dashboards, Persistenz (IndexedDB).