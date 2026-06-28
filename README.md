# Lotse — Besucherführung Sektor 10

Digitale Besucherführung & Areal-Navigation für die Liegenschaft
**Industriestrasse 1283, 5728 Gontenschwil**.

Live: https://besucherfuehrung-sektor10.vercel.app

## Features

**Besucheransicht**
- Mieterverzeichnis mit Suche & Kategorie-Filter
- Live-Status pro Mieter (offen/geschlossen, aus Öffnungszeiten berechnet)
- Detail-Panel: Turn-by-turn-Wegbeschreibung, Kontakt, Öffnungszeiten, Hinweise
- Interaktive Gelände-Karte mit animierter Route ab Besucherparkplatz
- Echte Stockwerk-Grundrisse (UG / EG / 1. OG) mit Hervorhebung des Mieters
- QR-Code zum Teilen der Route, Druckansicht
- Umgebungs-PDF & Fassadenansichten

**Editor**
- Marker setzen, direkt auf der Karte ziehen, löschen
- Eigenschaften je Marker: Name, Typ, Farbe, X/Y-Koordinaten
- Marker-Typen: Mieter, Eingang, Parkplatz, Rampe, Wareneingang, Briefkasten, Sammelplatz
- Wege zeichnen: Wegpunkte setzen & ziehen, Marker als Wegpunkt, Ziel verbinden
- „Nur aktiven Weg" Ansicht
- JSON Export / Import, Auto-Save (localStorage), Reset

**Responsive** — Desktop (3 Spalten), Tablet & Mobile (gestapelt).

## Tech

Single-file Static App: HTML + CSS + Vanilla JS, SVG-Karten, Tabler Icons,
QRCode.js. Deployment auf Vercel (statisch, kein Build-Step).

## Entwicklung

Lokal mit beliebigem Static-Server:

```bash
npx http-server . -p 4321
```

## Roadmap

- Migration auf Next.js + Supabase (Mieter- & Marker-Daten aus DB)
- Hochwertige isometrische 3D-Grundrisse
- Mehrsprachigkeit (DE / EN / FR)
- Multi-Areal-Verwaltung
