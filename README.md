# Korrektur-Begleiter

Eine einzelne Webseite (`index.html`), die beim Korrigieren von Schülerarbeiten in Französisch und Spanisch hilft. Sie läuft im Browser auf iPad, iPhone, Android, Windows, macOS und Linux. Es gibt keinen Server und keine Installation.

## Funktionen

- **Mehrere Kurse parallel** mit Fortschrittsbalken (x / y, Prozent), Motivationssprüchen, Meilensteinen und Konfetti bei 100 %
- **Verbleibende Arbeiten** links neben dem Fortschrittsbalken, motivierend formuliert (z. B. „Nur noch 7 Stück! 💪🏃“), in der Sek I und der Oberstufe
- **Seiten pro Arbeit:** Am Anfang gibst du an, wie viele Seiten die Arbeit hat (1 bis 40) und bei wie vielen Seiten schon alle Arbeiten korrigiert sind. Jede Seite hat einen eigenen Fortschrittsbalken. Du kannst eine Seite als „komplett erledigt“ anklicken oder die aktive Seite wechseln. Nach einer fertigen Seite geht es mit der nächsten offenen Seite weiter (danach wieder von vorn). Eine wieder geöffnete Seite wird gleich zur aktiven. Die Zeitmessung gilt pro Seite, die Kachel zeigt „Ø pro Seite“.
- **Notentabellen** als Einblendung auf der Seite (kein neues Fenster): bei Oberstufen-Kursen die Notenpunkte 15 bis 0 mit Note und Prozent (KMK-Skala, wie auf Wikipedia unter „Abitur in Hessen“), bei Sek-I-Kursen die Noten 1 bis 6 mit Prozentbereichen. Beide Tabellen lassen sich auch auf der Startseite einblenden. Schließen mit ✕, Klick auf den Rand oder Esc. Die Tabellen passen ohne Scrollen auf iPad (quer) und Handy (hoch).
- **Rückgängig und Wiederherstellen** über zwei Buttons, auch über Seitenwechsel hinweg
- **Logo** (Yin-Yang) oben links, ein Link zum GitHub-Repository dieser Seite
- **Statusübersicht** (nur lesend): alle Kurse mit verbleibenden Korrekturen, Restzeit und Feierabend-Prognose
- **Zeitmessung** nach dem Pomodoro-Prinzip. Ein gemeinsamer Button startet (grün) und stoppt (rot) die Korrektur einer Seite. „Zeit pausieren“ hält nur die Zeit der aktuellen Korrektur an, der große Button wird dann gelb („Korrektur fortsetzen“). Ein kurzer Schutz verhindert, dass ein Doppeltippen direkt nach dem Start sofort stoppt. In der Oberstufe bleiben „Sprachlich“ und „Inhaltlich“ getrennt, dazu „Stopp: fertig“ und „Zeit pausieren“ bzw. „Korrektur fortsetzen“. Nach jeder Arbeitsphase fragt ein kleines Fenster in der Seite (kein Browser-Pop-up) „Pause jetzt einlegen?“: **Ja** startet die Pause, **Nein** startet direkt eine neue Arbeitsphase, **Später erinnern** verschiebt die Pause um frei wählbare Minuten (in 0,5-Schritten, z. B. 1,5). Solange das Fenster offen ist, steht die Zeit der Korrektur. **Toilettenpause jetzt einlegen** startet sofort eine 5-Minuten-Pause (Zeit der Korrektur angehalten); danach läuft die Arbeitsphase dort weiter, wo sie war, und „Pause überspringen“ beendet sie früher. Dazu Durchschnitt pro Seite, Pausen mit Augenpausen-Tipp. Der Durchschnitt lässt sich pro Kurs mit dem Button ↺ in der Kachel „Ø pro Seite“ nach einer Bestätigung zurücksetzen. Die gemessenen Zeiten bleiben dabei gespeichert, auch in der Excel-Tabelle (dort zählen die Durchschnitte dann erst ab dem Zurücksetzen).
- **Oberstufe** (E, Q, Q1 bis Q4): getrennte Stoppuhren für sprachliche und inhaltliche Korrektur; die Kacheln „Ø pro Seite“ und „Aktuelle Seite“ zeigen beide Werte (sprachl. und inhaltl.) und fett die Summe (Σ)
- **Uhren** (digital und analog) und Bildschirm bleibt an (wo der Browser es erlaubt). Der Hinweis zur Systemeinstellung erscheint nur, wenn du auf das ⓘ neben dem Button tippst, und verschiebt die Seite nicht.
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
4. Bei „Wie viele Seiten hat die Arbeit?“ die Seitenzahl eintragen (1 = keine Aufteilung) und angeben, bei wie vielen Seiten schon alle Arbeiten korrigiert sind.
5. **Start** drücken (der Button leuchtet grün und zeigt „Läuft …"), korrigieren, mit **Stopp** oder **Erledigt (ohne Zeit)** weiterzählen. Eine Korrektur zählt immer für die aktive Seite.

## Daten und Datenschutz

- Alles liegt im Browser (localStorage) des jeweiligen Geräts, nichts auf einem Server.
- Die Sätze, die du analysieren lässt, gehen an die Anthropic-API. Gib deshalb keine echten Schülernamen ein.
- **Zwischen Geräten** übertragen geht auf zwei Wegen:
  - **Datensicherung:** auf der Startseite „Sicherung speichern" und auf dem anderen Gerät „Sicherung einlesen". Enthalten sind alle Kurse, Fehlerlisten und Zeiten, aber nicht der API-Key.
  - **Code:** Der Kurs-Code (z. B. `9erSpa28`) bleibt immer gleich. Haben zwei Kurse denselben Code (gleiche Stufe, gleiches Fach, gleiche Anzahl), fragt die Seite, welchen du öffnen willst. In der Kursliste auf der Startseite ist immer eindeutig, welcher Kurs gemeint ist und öffnet den Kurs mit seinem aktuellen Stand auf diesem Gerät. Auf einem anderen Gerät kennt er den Fortschritt nicht. Dafür gibt es den **Code mit Stand** (z. B. `9erSpa28-12`). Zeiten und Fehlerliste überträgt nur die Datensicherung.
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
| `SCHAETZ_SEK1_MIN` | grobe Schätzung pro ganze Arbeit (Sek I), wird auf die Seiten verteilt | 20 |
| `SCHAETZ_SPR_MIN` / `SCHAETZ_INH_MIN` | grobe Schätzung pro ganze Arbeit, Oberstufe, sprachlich / inhaltlich | 25 / 20 |

Erscheint bei der Analyse die Meldung „Modell nicht gefunden", ist der Wert in `MODEL` zu prüfen.

## Bekannte Grenzen

- PONS lässt sich nicht in die Seite einbetten und öffnet deshalb immer in einem neuen Tab.
- „Bildschirm bleibt an" nutzt die Wake-Lock-Funktion des Browsers. Wo sie fehlt, zeigt die Seite einen Hinweis auf die Systemeinstellung (iOS: Einstellungen → Anzeige & Helligkeit → Automatische Sperre → Nie).
- Der Code mit Stand (z. B. `9erSpa28-12`) gilt nur für Kurse mit einer Seite pro Arbeit. Bei mehreren Seiten nutze die Datensicherung.
- Die Seite braucht Internet für die KI-Analyse und für PONS. Zeitmessung, Fortschritt und Auswertungen funktionieren auch ohne.
- Die Restzeit und die Feierabend-Prognose sind Schätzungen. Ohne eigene Messung rechnet die Seite mit Standardwerten und kennzeichnet das.

## Logo

Das Yin-Yang-Symbol oben links ist als einfaches SVG direkt im Code gezeichnet, es lädt also nichts von außen. Es verweist auf das GitHub-Repository der Seite. Wer die Seite lokal öffnet, landet auf `github.com`. Mit der Konstante `REPO_URL` lässt sich die Adresse fest eintragen.

## Lizenz

Noch keine Lizenzdatei, damit liegen alle Rechte bei dir. Wenn du den Code mit anderen teilen möchtest, ergänze beim Anlegen oder später über „Add file → Create new file → `LICENSE`" eine Lizenz, z. B. die MIT-Lizenz.
