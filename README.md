# Abnahme

Mobile Web-App zur Abnahme von Innentüren – eine einzige `index.html` ohne Build-Schritt.

## Funktionen

- Startbildschirm mit Datum, Baustelle (Vorschlagsliste + automatischer Vorschlag der nächstgelegenen gespeicherten Baustelle im Umkreis von 500 m), Wohnung, Kunde und Prüfer (wird gemerkt)
- Pro Tür: Bezeichnung, Pflichtfotos Vorder- und Rückseite (auf max. 1280 px verkleinert, JPEG 0.7, mit Uhrzeit und GPS-Koordinaten inkl. Genauigkeit), Zustand „In Ordnung“ / „Mangel“ / „Fehlende Teile“, Notiz mit Diktierfunktion (de-DE) und optionales Detailfoto
- Unterschrift des Kunden per Finger oder „Später unterschreiben“
- PDF-Bericht (jsPDF) mit Zusammenfassung der offenen Punkte, Fotos mit Zeitstempel/GPS, Unterschrift bzw. leerer Unterschriftszeile und Seitenzahlen
- Teilen über das Teilen-Menü des Handys (WhatsApp, Mail …), sonst Download

## Veröffentlichen mit GitHub Pages

Repository → *Settings* → *Pages* → *Deploy from a branch* → Branch und Ordner `/ (root)` wählen.
Kamera, GPS und Mikrofon funktionieren nur über HTTPS, was GitHub Pages bereitstellt.

## Hinweise

- Gespeicherte Baustellen und der Prüfername liegen im `localStorage` des jeweiligen Geräts bzw. Browsers.
- Für die PDF-Erstellung wird jsPDF von cdnjs.cloudflare.com geladen, dafür ist eine Internetverbindung nötig.
- Die Diktierfunktion hängt vom Browser ab (Chrome unter Android sowie Safari unter iOS). Wo sie fehlt, wird der Mikrofon-Button ausgeblendet.
