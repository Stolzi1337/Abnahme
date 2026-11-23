# Abnahme

Mobile Web-Apps zur Abnahme von Innentüren, Fenstern und allgemeinen Arbeiten für **Jonas Stolzenburg Baukonzept**.
Jede App steckt in einer einzigen HTML-Datei (HTML, CSS und JavaScript), ohne Build-Schritt.

| App | Datei | Live |
|---|---|---|
| Türen | `index.html` | https://stolzi1337.github.io/Abnahme/ |
| Fenster | `fenster.html` | https://stolzi1337.github.io/Abnahme/fenster.html |
| Allgemeine Arbeiten | `arbeiten.html` | https://stolzi1337.github.io/Abnahme/arbeiten.html |

Oben auf dem Startbildschirm wechselt man zwischen **🚪 Türen**, **🪟 Fenster** und **🔨 Arbeiten**. Gespeicherte Baustellen und Prüfer gelten für alle Apps.

## Fenster-App: Unterschiede

- Fotos **Innenansicht** und **Außenansicht** (Pflicht)
- **Prüfliste** pro Fenster, jeder Punkt i.O. / n.i.O.: Funktion (Öffnen/Kippen/Schließen), Beschläge & Griff, Dichtungen, Anschlussfuge innen, Anschlussfuge außen, Glas & Rahmen unbeschädigt. „Alle i.O.“ füllt alles mit einem Tipp aus.
- Wird ein Punkt als n.i.O. markiert, schlägt die App „Mangel“ vor. „In Ordnung“ ist dann nicht mehr möglich.
- Das PDF zeigt die Prüfliste je Fenster. Die n.i.O.-Punkte erscheinen zusätzlich in der Zusammenfassung.
- Dateiname: `Abnahme_Fenster_<Baustelle>_<Wohnung>_<Datum>.pdf`

## Arbeiten-App: Unterschiede

- Für alle sonstigen Gewerke, zum Beispiel Malerarbeiten, Fliesen oder Trockenbau. Jede Position hat eine Bezeichnung.
- Feld **Wohnung / Bereich**, damit auch Treppenhaus, Keller usw. passen
- **Übersichtsfoto** ist Pflicht, ein zweites Foto („Weitere Ansicht“) optional
- Beim Gewerk „Allgemein“ zusätzlich ein optionales **Vorher-Foto**. Im PDF stehen dann Vorher und Nachher nebeneinander.
- Zustand, Notiz mit Diktat und Detailfoto wie bei den Türen
- **Gewerk** pro Position: „Allgemein“ (ohne Prüfliste) oder „Fliesen“. Das gewählte Gewerk bleibt für die nächste Position eingestellt.
- **Prüfliste Fliesen:** Fugenbild gleichmäßig, Fugen gefüllt ohne Risse, Ebenheit/kein Kantenversatz, kein Hohlklang, keine beschädigten Fliesen, Silikonfugen sauber und dicht, Gefälle zum Ablauf (auch „entfällt“ möglich), gereinigt. Weitere Gewerke werden in `arbeiten.html` unter `GEWERKE` ergänzt.
- Dateiname: `Abnahme_Arbeiten_<Baustelle>_<Bereich>_<Datum>.pdf`

## Ablauf (Türen)

1. **Start:** Datum (heute), Baustelle (Vorschlagsliste und automatischer Vorschlag der nächstgelegenen gespeicherten Baustelle im Umkreis von 500 m), Wohnung, Kunde, Prüfer. Mit „+ Weiteren Prüfer hinzufügen“ lassen sich mehrere Prüfer eintragen, die App merkt sich alle.
2. **Türen:** Bezeichnung, Pflichtfotos Vorder- und Rückseite (max. 1280 px, JPEG 0.7, mit Uhrzeit und GPS inkl. Genauigkeit), Zustand „In Ordnung“, „Mangel“ oder „Fehlende Teile“. Bei Mängeln oder fehlenden Teilen ist eine Notiz Pflicht (mit Diktierfunktion), dazu ein optionales Detailfoto.
3. **Unterschrift:** Der Kunde unterschreibt mit dem Finger, oder „Später unterschreiben“ wählen.
4. **PDF-Bericht:** Logo auf jeder Seite, Kopfdaten, Zusammenfassung der offenen Punkte, alle Türen mit Fotos, Zeitstempel und GPS, dazu Unterschrift bzw. „Unterschrift ausstehend“ und Seitenzahlen.
5. **Fertig:** Bericht über das Teilen-Menü des Handys teilen (WhatsApp, Mail …) oder herunterladen. Danach „Nächste Wohnung“ oder „Ganz neue Abnahme“.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Türen-App |
| `fenster.html` | Fenster-App |
| `arbeiten.html` | App für allgemeine Arbeiten |
| `logo.png` | Logo für PDF und Startbildschirm. Zum Austauschen einfach ersetzen, am besten ein quadratisches PNG. |
| `icon-180.png`, `icon-512.png` | App-Symbol für den Handy-Startbildschirm |
| `manifest*.webmanifest` | Damit die Apps installiert wie eigene Apps laufen |

## Auf dem Handy einrichten

Seite öffnen, dann **Teilen → Zum Home-Bildschirm** (iPhone) bzw. **Menü → Zum Startbildschirm hinzufügen** (Android).
Beim ersten Start fragt der Browser nach Zugriff auf Standort, Kamera und Mikrofon. Bitte erlauben.

## Hinweise

- Baustellen und Prüfernamen werden nur auf dem jeweiligen Gerät gespeichert (`localStorage`).
- Erfasste Türen liegen bis zur Berichterstellung nur im Arbeitsspeicher. Die Seite also nicht neu laden, bevor das PDF erstellt ist. Die App warnt beim Verlassen.
- Für die PDF-Erstellung wird jsPDF von cdnjs.cloudflare.com geladen, dafür ist eine Internetverbindung nötig.
- GitHub Pages veröffentlicht automatisch den Branch `main`.
