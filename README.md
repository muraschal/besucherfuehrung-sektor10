# Lotse — Besucherführung Sektor 10

Digitale Besucherführung & Areal-Navigation für die Liegenschaft
**Industriestrasse 1283, 5728 Gontenschwil**.

Live: https://besucherfuehrung-sektor10.vercel.app

## Features

**Besucheransicht**
- Mieterverzeichnis mit Suche & Kategorie-Filter
- Live-Status pro Mieter (offen/geschlossen, aus Öffnungszeiten berechnet)
- Detail-Panel: Turn-by-turn-Wegbeschreibung, Kontakt, Öffnungszeiten, Hinweise
- **3D-Kartenansicht (Exploded Isometric)** — gestapelte Etagen (UG/EG/1.OG), aktive Etage hervorgehoben, glühende Route vom Parkplatz zum Ziel, Kamera-Fly-to bei Mieterwahl, Etagen-Explode-Toggle (Three.js + Bloom)
- 2D/3D-Umschalter mit automatischem 2D-Fallback ohne WebGL
- Interaktive Gelände-Karte (2D) mit animierter Route ab Besucherparkplatz
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

Single-file Static App: HTML + CSS + Vanilla JS, Tabler Icons, QRCode.js.
3D-Ansicht mit Three.js r0.169 (vanilla, via ESM-Import-Map von jsDelivr —
kein Build-Step), OrbitControls, CSS2DRenderer, UnrealBloomPass. Lazy-Load
nur für die 3D-Ansicht, 2D-SVG als Fallback. Deployment auf Vercel (statisch).

## Entwicklung

Lokal mit beliebigem Static-Server:

```bash
npx http-server . -p 4321
```

## Roadmap

- 3D-Ausbau: Etagen-Wände/Räume, Routen-Modus mit Richtungspfeilen, Treppe/Lift als vertikale Connectoren, Info-Hierarchie (Schritt 2–8 der Roadmap)
- Editor 3D-fähig (Marker/Wege direkt in der Szene setzen, `floor`-Feld pro Marker)
- Mobile-Tuning: On-demand-Rendering, Touch-Gesten, Safari-iOS-Test
- Migration auf Next.js + Supabase (Mieter- & Marker-Daten aus DB) / optional React Three Fiber
- Mehrsprachigkeit (DE / EN / FR)
- Multi-Areal-Verwaltung
