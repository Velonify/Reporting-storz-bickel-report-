# Monatsreport Storz & Bickel / Vapormed

Live: https://storz-bickel-report.velonify.de (GitHub Pages, Branch `main`, Ordner `/`)

## Inhalt
- `index.html` – aktueller Report mit Monats-, Marken- und Bereichsumschalter (alle bisherigen Monate eingebettet)
- `reports/YYYY-MM/` – PDF des jeweiligen Monats
- `CNAME` – eigene Domain; bei Strato: CNAME `storz-bickel-report` → `velonify.github.io`
- `robots.txt` + `noindex` – Seite ist über den Link erreichbar, wird aber nicht von Suchmaschinen indexiert

Rohdaten (`raw_*.md`, `data2.json`) und der Generator (`render2.py`, `make_pdf.py`, `build_site.py`) liegen bewusst **nicht** im Repo, sondern lokal unter `Reporting/` – das Repo ist öffentlich.

## Monatlicher Ablauf
1. Zahlen erheben, `Reporting/YYYY-MM/data2.json` + `raw_*.md` anlegen
2. `python render2.py YYYY-MM/data2.json report2.html <frühere Monate data2.json …>`
3. `python make_pdf.py`
4. `python build_site.py YYYY-MM <Pfad zum Repo>`
5. Commit + Push → GitHub Pages aktualisiert die Seite automatisch
