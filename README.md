# Korrektur-Begleiter

Eine einzelne Webseite (`index.html`), die beim Korrigieren von Schülerarbeiten in Französisch und Spanisch hilft. Sie läuft im Browser auf iPad, iPhone, Android, Windows, macOS und Linux. Es gibt keinen Server und keine Installation.

## Funktionen

- **Mehrere Kurse parallel** mit Fortschrittsbalken (x / y, Prozent), Motivationssprüchen, Meilensteinen und Konfetti bei 100 %
- **Statusübersicht** (nur lesend): alle Kurse mit verbleibenden Korrekturen, Restzeit und Feierabend-Prognose
- **Zeitmessung** nach dem Pomodoro-Prinzip mit Start, Pause und Stopp, Durchschnitt pro Korrektur, Pausen mit Augenpausen-Tipp
- **Oberstufe** (E, Q, Q1 bis Q4): getrennte Stoppuhren für sprachliche und inhaltliche Korrektur
- **Uhren** (digital und analog) und Bildschirm bleibt an (wo der Browser es erlaubt)
- **PONS-Wörterbuch** (Französisch oder Spanisch, je nach Kurs), öffnet in einem neuen Tab
- **KI-Übersetzer und Fehleranalyse** mit Claude: Übersetzung, Fehler nach Grammatik, Lexik und Syntax, korrigierte Fassung. Mit API-Key direkt in der Seite, **ohne Key** über die Claude-App: Prompt kopieren, dort einfügen, Antwort zurück in die Seite einfügen
- **Gesammelte typische Fehler** als Word-Datei im Querformat (A4), z. B. `9er Spa typische Fehler.docx`
- **Arbeitszeiten** als Excel-Tabelle, z. B. `9er Spa Korrekturzeiten.xlsx`
- **Datensicherung** als `.json`-Datei und **Code** zum Fortsetzen (z. B. `9erSpa28-12`)

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
4. Start drücken, korrigieren, mit **Stopp** oder **Korrektur erledigt (ohne Zeit)** weiterzählen.

## Daten und Datenschutz

- Alles liegt im Browser (localStorage) des jeweiligen Geräts, nichts auf einem Server.
- Die Sätze, die du analysieren lässt, gehen an die Anthropic-API. Gib deshalb keine echten Schülernamen ein.
- **Zwischen Geräten** übertragen geht auf zwei Wegen:
  - **Datensicherung:** auf der Startseite „Sicherung speichern" und auf dem anderen Gerät „Sicherung einlesen". Enthalten sind alle Kurse, Fehlerlisten und Zeiten, aber nicht der API-Key.
  - **Code:** überträgt nur Jahrgangsstufe, Fach, Gesamtzahl und erledigte Korrekturen eines Kurses, nicht Zeiten und Fehlerliste.
- Löschst du die Browserdaten oder nutzt den privaten Modus, sind die Daten weg. Mach daher ab und zu eine Sicherung.
- Safari auf iPhone und iPad kann Daten von Seiten löschen, die etwa eine Woche nicht geöffnet wurden. Am besten die Seite über „Zum Home-Bildschirm" ablegen und regelmäßig sichern.

## Anpassen

Am Anfang des Skripts in `index.html` stehen Konstanten:

| Konstante | Bedeutung | Standard |
|---|---|---|
| `MODEL` | Claude-Modell für die Analyse | `claude-sonnet-5-5` |
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
- Die Seite braucht Internet für die KI-Analyse und für PONS. Zeitmessung, Fortschritt und Auswertungen funktionieren auch ohne.
- Die Restzeit und die Feierabend-Prognose sind Schätzungen. Ohne eigene Messung rechnet die Seite mit Standardwerten und kennzeichnet das.

## Lizenz

Noch keine Lizenzdatei, damit liegen alle Rechte bei dir. Wenn du den Code mit anderen teilen möchtest, ergänze beim Anlegen oder später über „Add file → Create new file → `LICENSE`" eine Lizenz, z. B. die MIT-Lizenz.
