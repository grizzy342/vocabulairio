# Korrektur-Begleiter

Eine einzelne Webseite (`index.html`), die beim Korrigieren von Schülerarbeiten in Französisch und Spanisch hilft. Sie läuft im Browser auf iPad, iPhone, Android, Windows, macOS und Linux. Es gibt keinen Server und keine Installation.

## Funktionen

- **Mehrere Kurse parallel** mit Fortschrittsbalken (x / y, Prozent), Motivationssprüchen, Meilensteinen und Konfetti bei 100 %
- **Aufgaben pro Klausur:** Für jede Aufgabe gibt es einen eigenen Fortschrittsbalken. Du kannst eine Aufgabe als „komplett erledigt" anklicken, die aktive Aufgabe wechseln, und die Seite springt nach einer fertigen Aufgabe automatisch zur nächsten offenen.
- **Notentabellen** als Einblendung auf der Seite (kein neues Fenster): bei Oberstufen-Kursen die Notenpunkte 15 bis 0 mit Note und Prozent (KMK-Skala, wie auf Wikipedia unter „Abitur in Hessen“), bei Sek-I-Kursen die Noten 1 bis 6 mit Prozentbereichen. Beide Tabellen lassen sich auch auf der Startseite einblenden. Schließen mit ✕, Klick auf den Rand oder Esc. Die Tabellen passen ohne Scrollen auf iPad (quer) und Handy (hoch).
- **Rückgängig und Wiederherstellen** über zwei Buttons, auch über Aufgabenwechsel hinweg
- **Logo** (Yin-Yang) oben links, ein Link zum GitHub-Repository dieser Seite
- **Statusübersicht** (nur lesend): alle Kurse mit verbleibenden Korrekturen, Restzeit und Feierabend-Prognose
- **Zeitmessung** nach dem Pomodoro-Prinzip mit Start, Pause und Stopp, Durchschnitt pro Korrektur, Pausen mit Augenpausen-Tipp
- **Oberstufe** (E, Q, Q1 bis Q4): getrennte Stoppuhren für sprachliche und inhaltliche Korrektur
- **Uhren** (digital und analog) und Bildschirm bleibt an (wo der Browser es erlaubt)
- **PONS-Wörterbuch** (Französisch oder Spanisch, je nach Kurs), öffnet in einem neuen Tab
- **KI-Übersetzer und Fehleranalyse** mit Claude: Übersetzung, Fehler nach Grammatik, Lexik und Syntax, korrigierte Fassung. Mit API-Key direkt in der Seite, **ohne Key** über die Claude-App: Prompt kopieren, dort einfügen, Antwort zurück in die Seite einfügen
- **Gesammelte typische Fehler** als Word-Datei im Querformat (A4), z. B. `9er Spa typische Fehler.docx`
- **Arbeitszeiten** als Excel-Tabelle, z. B. `9er Spa Korrekturzeiten.xlsx`
- **Datensicherung** als `.json`-Datei und **Kurs-Code** (z. B. `9erSpa28`) zum Wiederfinden eines Kurses

## Auf GitHub Pages veröffentlichen

1. Neues Repository anlegen (unauffälliger Name, README optional).
2. `index.html` hochladen (Add file → Upload files → Commit changes). Der Dateiname muss genau `index.html` lauten.
3. Settings → Pages → Branch `main`, Ordner `/(root)` → Save.
4. Nach ein bis zwei Minuten erscheint die Adresse `https://BENUTZERNAME.github.io/REPOSITORY/`.
5. Auf jedem Gerät die Adresse öffnen und als Lesezeichen oder über „Zum Home-Bildschirm" speichern.

**Hinweis:** Mit dem kostenlosen GitHub-Plan funktioniert Pages nur aus einem öffentlichen Repository. Bei einem privaten Repository (Pro/Team) ist die veröffentlichte Seite trotzdem für jeden mit der Adresse erreichbar. Die Datei enthält keinen Key und keine persönlichen Daten.

**Aktualisieren:** `index.html` im Repository öffnen → Stift-Symbol → neuen Code einfügen → Commit changes. Nach etwa einer Minute ist die neue Version online. Die Daten im Browser bleiben dabei erhalten.

## Erste Schritte

1. Startseite → **Neue Arbeit korrigieren**.
2. **Schritt 1 (optional):** Anthropic-API-Key eingeben (erstellbar in der Claude Console, die API wird nach Verbrauch abgerechnet). Er wird nur im Browser des jeweiligen Geräts gespeichert und nur an Anthropic gesendet. Ohne Key geht „Ohne API-Key fortfahren".
3. **Schritt 2:** Fach, Jahrgangsstufe (z. B. `9er`, `E`, `Q1`), optional einen Kursnamen und die Anzahl der Korrekturen eingeben.
4. Bei „Wie viele Aufgaben hat eine Klausur?" die Aufgabenzahl eintragen (1 = keine Aufgaben-Aufteilung) und angeben, wie viele Aufgaben schon komplett korrigiert sind.
5. **Start** drücken (der Button leuchtet grün und zeigt „Läuft …"), korrigieren, mit **Stopp** oder **Erledigt (ohne Zeit)** weiterzählen. Eine Korrektur zählt immer für die aktive Aufgabe.

## Daten und Datenschutz

- Alles liegt im Browser (localStorage) des jeweiligen Geräts, nichts auf einem Server.
- Die Sätze, die du analysieren lässt, gehen an die Anthropic-API. Gib deshalb keine echten Schülernamen ein.
- **Zwischen Geräten** übertragen geht auf zwei Wegen:
  - **Datensicherung:** auf der Startseite „Sicherung speichern" und auf dem anderen Gerät „Sicherung einlesen". Enthalten sind alle Kurse, Fehlerlisten und Zeiten, aber nicht der API-Key.
  - **Code:** Der Kurs-Code (z. B. `9erSpa28`) bleibt immer gleich und öffnet den Kurs mit seinem aktuellen Stand auf diesem Gerät. Auf einem anderen Gerät kennt er den Fortschritt nicht. Dafür gibt es den **Code mit Stand** (z. B. `9erSpa28-12`). Zeiten und Fehlerliste überträgt nur die Datensicherung.
- Löschst du die Browserdaten oder nutzt den privaten Modus, sind die Daten weg. Mach daher ab und zu eine Sicherung.
- Safari auf iPhone und iPad kann Daten von Seiten löschen, die etwa eine Woche nicht geöffnet wurden. Am besten die Seite über „Zum Home-Bildschirm" ablegen und regelmäßig sichern.

## Anpassen

Am Anfang des Skripts in `index.html` stehen Konstanten:

| Konstante | Bedeutung | Standard |
|---|---|---|
| `MODEL` | Claude-Modell für die Analyse | `claude-sonnet-5-5` |
| `REPO_URL` | Ziel des Logo-Links; leer = wird aus der Pages-Adresse abgeleitet (`https://github.com/BENUTZER/REPOSITORY`) | leer |
| `ARBEIT_MIN` | Arbeitsphase bis zur Pause | 25 |
| `PAUSE_KURZ_MIN` | kurze Pause | 5 |
| `PAUSE_LANG_MIN` | lange Pause | 15 |
| `RUNDEN_BIS_LANGE_PAUSE` | lange Pause nach so vielen Runden | 4 |
| `SCHAETZ_SEK1_MIN` | grobe Schätzung pro Korrektur (Sek I) | 20 |
| `SCHAETZ_SPR_MIN` / `SCHAETZ_INH_MIN` | grobe Schätzung Oberstufe, sprachlich / inhaltlich | 25 / 20 |

Erscheint bei der Analyse die Meldung „Modell nicht gefunden", ist der Wert in `MODEL` zu prüfen.

## Bekannte Grenzen

- PONS lässt sich nicht in die Seite einbetten und öffnet deshalb immer in einem neuen Tab.
- „Bildschirm bleibt an" nutzt die Wake-Lock-Funktion des Browsers. Wo sie fehlt, zeigt die Seite einen Hinweis auf die Systemeinstellung (iOS: Einstellungen → Anzeige & Helligkeit → Automatische Sperre → Nie).
- Der Code mit Stand (z. B. `9erSpa28-12`) gilt nur für Kurse mit einer Aufgabe pro Klausur. Bei mehreren Aufgaben nutze die Datensicherung.
- Die Seite braucht Internet für die KI-Analyse und für PONS. Zeitmessung, Fortschritt und Auswertungen funktionieren auch ohne.
- Die Restzeit und die Feierabend-Prognose sind Schätzungen. Ohne eigene Messung rechnet die Seite mit Standardwerten und kennzeichnet das.

## Logo

Das Yin-Yang-Symbol oben links ist als einfaches SVG direkt im Code gezeichnet, es lädt also nichts von außen. Es verweist auf das GitHub-Repository der Seite. Wer die Seite lokal öffnet, landet auf `github.com`. Mit der Konstante `REPO_URL` lässt sich die Adresse fest eintragen.

## Lizenz

Noch keine Lizenzdatei, damit liegen alle Rechte bei dir. Wenn du den Code mit anderen teilen möchtest, ergänze beim Anlegen oder später über „Add file → Create new file → `LICENSE`" eine Lizenz, z. B. die MIT-Lizenz.
