# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Was hier ist

Klausur-Lernguide für **„Einführung in die sozialwissenschaftliche Statistik"** (Vorlesung von Prof. Dr. Constantin Ruhe, Wintersemester 2025/26). Adressat ist ein Politikstudent, der die Klausur im ersten Anlauf nicht bestanden hat und im zweiten Versuch bestehen muss.

Das ist **kein Code-Projekt**, sondern Lernmaterial mit einer kleinen Build-Pipeline.

## Verzeichnisstruktur

| Pfad | Rolle | Editieren? |
|------|-------|------------|
| `Vorlesung/Formelsammlung.pdf`, `Vorlesung/0_Wintersemester…pdf` | **Quellen** vom Dozenten | nie verändern |
| `Lernen/Markdown/*.md` | **Lernguide** (selbst geschrieben, didaktisch aufbereitet) | hier wird gearbeitet |
| `Lernen/*.pdf` | **Generierte Artefakte** aus den Lernguide-.md-Dateien | nicht direkt editieren |
| `Üben/Markdown/*_Übung.md` | **Übungsaufgaben mit Lösungen** (Aufgaben oben, Lösungen unten getrennt) | hier wird gearbeitet |
| `Üben/Markdown/Probeklausur_*.md` | **Statische Probeklausuren** (als Markdown) | hier wird gearbeitet |
| `Üben/*.pdf` | **Generierte Übungs-PDFs** | nicht direkt editieren |
| `Üben/Probeklausur_*_interaktiv.html` | **Interaktive Probeklausuren** (HTML/JS/MathJax) | direkt editieren |
| `build_pdfs.py` | **Build-Skript** (.md → PDF) | nur bei Layout-Änderungen |

Die Vorlesung hat 495 Folien — der Lernguide kondensiert sie auf ~120 Seiten Markdown / ~60 Seiten PDF.

## PDF-Build

Nach jeder Änderung an einer `.md` müssen die PDFs neu gebaut werden:

```bash
/Users/klauslueber/claudecode/Assistent/.venv/bin/python build_pdfs.py
```

Das Skript baut **zwei aktive Verzeichnisse**:
- `Lernen/Markdown/*.md` → `Lernen/*.pdf`
- `Üben/Markdown/*.md` → `Üben/*.pdf`

Neue `.md`-Dateien an diesen Orten werden automatisch mitgebaut.

Das Skript:
1. Liest alle `*.md` aus dem jeweiligen Verzeichnis (`CLAUDE.md` selbst wird übersprungen — Meta-Doku, kein Lernstoff).
2. **Schützt Mathe-Blöcke** (`$$...$$` und `$...$`) durch Tokens, bevor Markdown läuft, und setzt sie nach dem HTML-Schritt zurück. Ohne diesen Schutz frisst der Markdown-Parser `\\` (LaTeX-Zeilenumbruch in `\begin{cases}`) und Underscores in `_{...}`-Subscripts — Formeln werden dann als Roh-LaTeX statt SVG gerendert. **Diesen Schritt nicht entfernen.**
3. Konvertiert via Python-`markdown` (Extensions: `tables`, `fenced_code`, `attr_list`, `toc`, `sane_lists`) zu HTML.
4. Bettet CSS + MathJax (TeX-SVG, von CDN) ein.
5. Rendert mit Chrome Headless (`--headless=new --print-to-pdf`) zu PDF.

**Abhängigkeiten:**
- Python 3.12 venv unter `/Users/klauslueber/claudecode/Assistent/.venv/` mit `markdown` und `pypdf`.
- Google Chrome unter `/Applications/Google Chrome.app/Contents/MacOS/Google Chrome`.
- Internet (für MathJax-CDN beim Rendern).

**Kein Pandoc, kein wkhtmltopdf, kein brew/poppler verfügbar** — Developer Tools sind auf dieser Maschine nicht installiert. Daher der Chrome-Headless-Weg.

## Interaktive Probeklausuren

HTML-Dateien in `Üben/` folgen dem Muster von `Probeklausur_4_interaktiv.html`:

- Sticky Header mit Timer und Fortschrittsbalken; Timer-Konstante `SECS` und Fragenanzahl `N` oben im `<script>`-Block setzen.
- Pro Frage ein `.card`-Div mit `.q-num`, `.q-type`, `.q-text`, `.options` (Radio-Buttons), `.hint` (nur bei Falschantwort sichtbar).
- `.hint`-Div zeigt nach falscher Antwort Erklärung + korrekte Antwort — **keine Formeln in `.q-text` oder `.q-note`**, da die Formelsammlung in der Klausur selbst konsultiert werden muss.
- `.stata`-CSS-Klasse für Stata-Output (dunkler Monospace-Block).
- `ANSWERS`-Objekt im JS enthält die Lösungen (`{1:'c', 2:'a', …}`).
- **Kreuztabellen:** UV immer in Spalten, AV in Zeilen.
- MathJax (tex-svg) wird inline geladen — kein CDN-Fallback nötig, solange Internet vorhanden.

**Deployment:** GitHub Pages ist aktiv für das Repo `klauslueber/Statistik`.
Basis-URL: `https://klauslueber.github.io/Statistik/`
Üben-Verzeichnis: `%C3%9Cben/` (URL-kodiertes Ü).

## Didaktisches Schema der Lerndateien

Jede `.md`-Datei folgt demselben Aufbau pro behandelter Operation/Kennzahl. Wenn neue Inhalte ergänzt werden, dieses Muster beibehalten:

1. **Idee / Was misst es?** (intuitive Erklärung in einem Satz)
2. **Voraussetzungen** (Skalenniveau!)
3. **Formel** (LaTeX, sowohl `$inline$` als auch `$$display$$`)
4. **Schritt-für-Schritt-Beispiel** mit konkreten Zahlen — komplett durchgerechnet
5. **Interpretation** im Sachzusammenhang
6. **Klausurfallen** (typische Fehler explizit benannt)

Beispiele kommen aus politik-/sozialwissenschaftlichen Kontexten (ESS, SOEP, Parteipräferenzen CDU/SPD/Grüne/AfD, Bildung × Lohn, Einkommensungleichheit) — passend zum Vorlesungsstil.

## Übungsdateien

Zu jedem Lernkapitel `01`–`11` gibt es eine Übungsdatei in `Üben/Markdown/`. Aufbau:

1. Kurzes Lead-Blockzitat (was kommt).
2. **3–4 Aufgaben** mit Politik-/Sozialwissenschafts-Beispielen, je mit mehreren Teilaufgaben (a, b, c, …).
3. Trennlinie `---` und Überschrift `# Lösungen`.
4. Pro Aufgabe eine Lösung mit kompletter Schritt-für-Schritt-Rechnung, Zwischenwerten in Tabellen wo sinnvoll, Plausibilitätskontrolle und mindestens einer Klausurfalle als Blockquote.

Die Übungsdateien tragen das Suffix `_Übung.md` und greifen auf Daten und Notation der zugehörigen Lerndatei zurück.

## Reihenfolge der Kapitel (zwingend so beibehalten)

`00` Übersicht & Skalenniveaus → `01` Häufigkeiten → `02` Lagemaße → `03` Streuungsmaße → `04` Konzentrationsmaße → `05` Kreuztabellen → `06` Zusammenhang nominal → `07` Zusammenhang metrisch → `08` Zufallsvariablen → `09` Schätzen → `10` Testen → `11` Regression → `12` Klausurfahrplan.

Die Themen bauen aufeinander auf (Inferenz braucht Zufallsvariablen, Regression braucht Korrelation usw.). Querverweise zwischen den Dateien (`siehe 06_Zusammenhang_nominal.md`) sind beabsichtigt.

## Stil-Konventionen

- **Sprache:** Deutsch.
- **Anrede:** Du-Form (direkter Lerner-Bezug).
- **Mathe:** LaTeX in `$…$` / `$$…$$`. MathJax rendert SVG. Komplexe Konstrukte (`\begin{cases}`, mehrere `_{...}` pro Zeile, `\left…\right`) sind unproblematisch — der Build-Pre-Processor schirmt sie vor dem Markdown-Parser ab.
- **Euro-Zeichen niemals direkt in `$…$` setzen.** MathJax 3 stürzt bei `€` innerhalb von Math-Ausdrücken mit *„Cannot read properties of null (reading '4')"* ab und rendert die Formel als „Math input error". Stattdessen `€` außerhalb des Math-Blocks schreiben (`$\mu = 3000$ €` statt `$\mu = 3000 €$`) oder bei Display-Math `\text{€}` verwenden (`$$\bar{x} = 2355\ \text{€}$$`). Andere Währungs-/Einheitenzeichen bei Verdacht entsprechend behandeln.
- **Hervorhebungen:** `> Klausurfalle:` als Blockquote (rendert als orange Hinweisbox).
- **Tabellen:** GFM-Tabellen, Spalten ausgerichtet wo sinnvoll.
- **Keine Emojis.**

## Quelltext der Vorlesung extrahieren

Falls Inhalte/Beispiele aus dem 495-seitigen Vorlesungs-PDF benötigt werden:

```bash
/Users/klauslueber/claudecode/Assistent/.venv/bin/python -c "
from pypdf import PdfReader
r = PdfReader('Vorlesung/0_Wintersemester2025-26_Folien_1-13_prelecture.pdf')
for i in range(START, END):  # Seitenbereich
    print(f'\n--- p.{i+1} ---')
    print(r.pages[i].extract_text())
"
```

Die Kapitelgrenzen der Vorlesung (#1–#13):
| # | Folie | Thema |
|---|-------|-------|
| 1 | 1 | Einführung |
| 2 | 29 | Grundbegriffe & Skalenniveaus |
| 3 | 69 | Häufigkeitsverteilungen |
| 4 | 99 | Kreuztabellen & Zusammenhangsmaße |
| 5 | 144 | Lagemaße |
| 6 | 184 | Streuungsmaße |
| 7 | 217 | Metrische Zusammenhangsmaße |
| 8 | 257 | Konzentrationsmaße |
| 9 | 285 | Zufallsvariablen |
| 10 | 341 | Schätzen |
| 11 | 366 | Testen |
| 12 | 423 | OLS-Regression |
| 13 | 460 | Interaktionseffekte |

## Übergeordneter Workspace

Dieses Projekt liegt im persönlichen Workspace `/Users/klauslueber/claudecode/`. Übergeordnete Konventionen aus `../CLAUDE.md` und `../soul.md` gelten weiterhin (Ton, Grenzen, Zusammenarbeitsstil).
