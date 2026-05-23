# IRON.LOG

Eine schlanke Progressive Web App (PWA) zum Tracken von Krafttraining,
Körpergewicht und Ernährung. Läuft komplett offline, alle Daten werden
ausschließlich lokal im Browser gespeichert.

## Hosting / Installation

Die App ist eine statische Single-File-Anwendung.

1. `index.html` und `manifest.json` auf einen statischen Host legen
   (z.B. GitHub Pages, Netlify, Cloudflare Pages)
2. Die HTTPS-URL am Smartphone in Chrome öffnen
3. Menü → „Zum Startbildschirm hinzufügen"

> HTTPS ist erforderlich, damit der Kamera-Zugriff (Barcode-Scanner) funktioniert.

## Funktionen (Überblick)

- Trainings-Tracking mit Pausen-Timer und Fortschritts-Diagrammen
- Konfigurierbares Profil → automatische Kalorien-/Makro-Ziele
- Ernährungs-Tracking inkl. Barcode-Scanner
- Mehrere Trainingspläne, importier- und exportierbar
- Daten-Export/Import als JSON (Backup)

## Daten & Privatsphäre

Alle Eingaben (Training, Körpergewicht, Ernährung) bleiben lokal auf dem
Gerät (localStorage). Es gibt keinen Server und keine Accounts. Der einzige
ausgehende Aufruf ist die Barcode-Abfrage an eine offene Lebensmittel-API.

**Empfehlung:** Regelmäßig ein Backup über die Export-Funktion erstellen.

## Trainingsplan-Import

Das Format zum Importieren eigener Pläne ist in `PLAN-FORMAT.md` beschrieben.

## Aktualisierung

Hinweise zum Austausch der App-Datei stehen in `UPDATE.md`.
