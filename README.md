# Abnahme

Mobile Web-App zur Abnahme von Innentüren für **Jonas Stolzenburg Baukonzept**.
Die ganze App steckt in `index.html` (HTML, CSS und JavaScript), ohne Build-Schritt.

**Live:** https://stolzi1337.github.io/Abnahme/

## Ablauf

1. **Start:** Datum (heute), Baustelle (Vorschlagsliste und automatischer Vorschlag der nächstgelegenen gespeicherten Baustelle im Umkreis von 500 m), Wohnung, Kunde, Prüfer. Mit „+ Weiteren Prüfer hinzufügen“ lassen sich mehrere Prüfer eintragen, die App merkt sich alle.
2. **Türen:** Bezeichnung, Pflichtfotos Vorder- und Rückseite (max. 1280 px, JPEG 0.7, mit Uhrzeit und GPS inkl. Genauigkeit), Zustand „In Ordnung“, „Mangel“ oder „Fehlende Teile“. Bei Mängeln oder fehlenden Teilen ist eine Notiz Pflicht (mit Diktierfunktion), dazu ein optionales Detailfoto.
3. **Unterschrift:** Der Kunde unterschreibt mit dem Finger, oder „Später unterschreiben“ wählen.
4. **PDF-Bericht:** Logo auf jeder Seite, Kopfdaten, Zusammenfassung der offenen Punkte, alle Türen mit Fotos, Zeitstempel und GPS, dazu Unterschrift bzw. „Unterschrift ausstehend“ und Seitenzahlen.
5. **Fertig:** Bericht über das Teilen-Menü des Handys teilen (WhatsApp, Mail …) oder herunterladen. Danach „Nächste Wohnung“ oder „Ganz neue Abnahme“.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die App |
| `logo.png` | Logo für PDF und Startbildschirm. Zum Austauschen einfach ersetzen, am besten ein quadratisches PNG. |
| `icon-180.png`, `icon-512.png` | App-Symbol für den Handy-Startbildschirm |
| `manifest.webmanifest` | Damit die App installiert wie eine eigene App läuft |

## Auf dem Handy einrichten

Seite öffnen, dann **Teilen → Zum Home-Bildschirm** (iPhone) bzw. **Menü → Zum Startbildschirm hinzufügen** (Android).
Beim ersten Start fragt der Browser nach Zugriff auf Standort, Kamera und Mikrofon. Bitte erlauben.

## Hinweise

- Baustellen und Prüfernamen werden nur auf dem jeweiligen Gerät gespeichert (`localStorage`).
- Erfasste Türen liegen bis zur Berichterstellung nur im Arbeitsspeicher. Die Seite also nicht neu laden, bevor das PDF erstellt ist. Die App warnt beim Verlassen.
- Für die PDF-Erstellung wird jsPDF von cdnjs.cloudflare.com geladen, dafür ist eine Internetverbindung nötig.
- GitHub Pages veröffentlicht automatisch den Branch `main`.
