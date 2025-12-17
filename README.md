# Vorlage für Wissenschaftliche Arbeiten der DHBW Ravensburg an der Fakultät Wirtschaft

Diese LaTeX Vorlage dient als Grundlage für wissenschaftliche Arbeiten an der DHBW Ravensburg in der Fakultät für Wirtschaft.

Die Vorlage orientiert sich an den **Richtlinien zur Gestaltung wissenschaftlicher Arbeiten Version 2.0**.

Dabei enthält diese Vorlage **keine** "Dokumentation der Verwendung generativer KI-Systeme". Ob und in welcher Form eine Dokumentation der Verwendung generativer KI-Systeme nötig ist, klären Sie direkt mit Ihrem Studiengang und ergänzen dementsprechend diese Vorlage.

## Enthaltene Titelblätter

- Projektarbeit
- Bachelorarbeit
- Seminararbeit / Projektdokumentation

## Benutzung

Es gibt zwei Möglichkeiten, diese Vorlage zu benutzen:

### Mit git

Um die Versionierung der Vorlage zu nutzen, empfiehlt es sich, das [Repository](https://github.com/felixkxlr/LatexVorlage_DHBW_RV_FakultaetWirtschaft) auf Github auszuchecken. Alle Einstellungen (Parameter, Gliederung) kannst du im Ordner `/config` vornehmen. Dieser wird vom Repository nicht beeinflusst.
Dateien, die du zum Ordner `/chapter` hinzufügst, werden ebenfalls ignoriert, Änderungen an den Beispieldateien werden jedoch von der Versionsverwaltung verfolgt.

### Ohne git

Um die Vorlage zu benutzen, kannst du einfach die [vorlage.zip](vorlage.zip) downloaden. Das .zip entpacken und den Inhalt in dein gewünschtes Arbeitsverzeichnis kopieren.

## Installation

Es empfiehlt sich Wissenschaftliche Arbeiten mit **TeXStudio**, **VS Code** (mit LaTeX Workshop) oder **Overleaf** zu bearbeiten.

### Wichtig: Umstellung auf Biber (APA 7)

Diese Vorlage nutzt den modernen **Biber**-Prozessor für das Literaturverzeichnis, um den geforderten APA-7-Stil korrekt abzubilden.
Stelle sicher, dass dein Editor so konfiguriert ist, dass er `biber` statt `bibtex` ausführt!

### Installation MacOS

- download and install [MacTex](https://tug.org/mactex/)
- download and install [TexStudio](http://www.texstudio.org/) oder VS Code

### Installation Linux

#### Debian Based (bspw. Ubuntu)

```bash
sudo apt-get install texlive-full biber
Installation Windows
download and install MikTex

download and install TexStudio
```

## Konfiguration von TexStudio

Unter: `Einstellungen` -> `Erzeugen` -> `Standard Bibliographieprogramm` auf **Biber** stellen.

Falls du einen manuellen "Benutzerbefehl" (User Command) definieren möchtest, nutze folgenden Ablauf für Biber und Glossare:

```bash
txs:///pdflatex | txs:///biber | txs:///makeindex "%.nlo" -s nomencl.ist -o "%.nls" | txs:///pdflatex | txs:///pdflatex
```

## Allgemeine Informationen zum Gebrauch

Keine Änderungen an den Dateien im Verzeichnis ./pages/ vornehmen. Für die Arbeit beziehen sich alle Änderungen auf die Datei config/config.tex und die Dateien im Verzeichnis ./chapter/.

## Verzeichnisstruktur

Die Verzeichnisstruktur sieht folgendermaßen aus:
```
.  
├── appendix                    # In diesem Ordner können die Anhänge verwaltet werden.
│   ├── artefact.pdf            # Beispiel-Pdf die in den Anhang eingefügt wurde
│   └── index.tex               # Beispielhafter Anhang
├── chapter                     # Dein Arbeitsverzeichnis (Inhalt deiner Arbeit)
│   ├── 10_einleitung.tex       # Beispiel Einleitung
│   ├── 20_kapitel.tex          # Beispiel Kapitel
│   ├── 80_fazit.tex            # Beispiel Fazit
│   ├── abkuerzungsverzeichnis.tex # Definition deiner Abkürzungen
│   ├── formelverzeichnis.tex   # Definition deiner Formeln (falls genutzt)
│   ├── kiVerzeichnis.tex       # Einträge für das KI-Verzeichnis (Pflicht bei KI-Nutzung)
│   └── symbolverzeichnis.tex   # Definition deiner Symbole
├── config                      # Verzeichnis für die Konfigurationen deines Projektes.
│   ├── config.tex              # ZENTRALE KONFIGURATION (Titel, Autor, Sprache, Typ...)
│   ├── lang_de.tex             # Sprachdatei Deutsch (automatisch geladen)
│   ├── lang_en.tex             # Sprachdatei Englisch (automatisch geladen)
│   ├── gliederung.tex          # Hier fügst du deine Kapitel aus /chapter ein
│   └── metaseiten.tex          # Logik für Verzeichnisse (nicht ändern)
├── HOWTO                       # Verzeichnis mit Anleitungen zur Benutzung
│   ├── CHEAT_SHEET.tex         # Cheat sheet
│   └── INITIAL_CONFIG.md       # Anleitung zur Konfiguration
├── images
│   └── Seeigel_wuhuu.jpg       # Beispiel Bild
├── pages                       # Vorlagen Verzeichnis! Nichts Ändern!
│   ├── 10_titel_bachelor.tex
│   ├── 10_titel_projekt.tex
│   ├── 11_sperrvermerk.tex
│   ├── 13_abkuerzungsverzeichnis.tex
│   ├── 14_Formelverzeichnis.tex
│   ├── 17_listingsverzeichnis.tex
│   ├── 18_literaturverzeichnis.tex
│   ├── 19_symbolverzeichnis.tex
│   └── 20_erklaerung.tex
├── literatur.bib               # Deine Literatursammlung (BibTeX Format)
├── main.tex                    # Hauptdatei <- Öffnen zum Kompilieren
└── README.md                   # Die Datei die du gerade liest
```

## Initiale Konfiguration

siehe [INITIAL_CONFIG](HOWTO/INITIAL_CONFIG.md)

## Sprache wechseln

Die Vorlage unterstützt Deutsch und Englisch. Die Sprache wird zentral in config/config.tex über die Variable \myLanguage (ngerman oder english) gesteuert. Alle rechtlichen Texte und Verzeichnisnamen passen sich automatisch an.

## Strukturierung der Arbeit

Es empfiehlt sich pro Kapitel eine neue Datei im Ordner chapter anzulegen und diese in config/gliederung.tex einzubinden.

## Literaturarbeit (APA 7)

Die Vorlage nutzt biblatex mit biber im APA-Stil. Für die Verwaltung der Literatur empfiehlt sich:

Zotero (<https://www.zotero.org/>) (Export als BibLaTeX).

Die Datei ist unter ```./literatur/literatur.bib``` zu speichern.

### Zitieren im Text

\vgl{key} -> (vgl. Autor, Jahr)

\parencite{key} -> (Autor, Jahr)

\textcite{key} -> Autor (Jahr)

## Versionierung und Backup

Es empfiehlt sich für das Schreiben von wissenschaftlichen Arbeiten eine Versionierung wie git zu verwenden. Falls dies nicht möglich ist, nutze Cloud-Dienste für Backups:

Dropbox / Google Drive / OneDrive

## Versionierung

Version 1.0: Markus Schutz - (WI06)

Version 2.0: Julian Amelung - 2016

Version 3.0: Felix Keller (unterstützt von Sebastian Geimer) - 2024

Version 4.0: Simon Fischer - 2025 (Zitierstil-Vergleich -> Grundlage für Zitierstilentscheidung)

Version 5.0: Felix Keller - 2025 (Anpassung an Richtlinie V 2.0, APA 7, Biber, Mehrsprachigkeit (Deutsch, Englisch))

## [License](LICENSE)

Copyright (c) 2025 felixkxlr

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
