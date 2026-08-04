# kaiser-marcel.de

[![Deploy to GitHub Pages](https://github.com/marcel951/landingpage/actions/workflows/deploy.yml/badge.svg)](https://github.com/marcel951/landingpage/actions/workflows/deploy.yml)

Quellcode für die persönliche Website von Marcel Kaiser. Die Seite stellt mein Profil an der Schnittstelle von Systemintegration, Infrastruktur und Softwareentwicklung vor.

## Technischer Aufbau

- [Astro](https://astro.build/) als statischer Site-Generator
- TypeScript und modernes CSS ohne Frontend-Framework
- lokal eingebettete Technologie-Logos aus [Simple Icons](https://simpleicons.org/)
- automatisches Deployment mit GitHub Actions und GitHub Pages
- eigene Domain: [kaiser-marcel.de](https://kaiser-marcel.de)

Die Seite benötigt im Browser keine externen JavaScript- oder Logo-CDNs und wird vollständig statisch erzeugt.

## Lokal entwickeln

Voraussetzung ist Node.js ab Version 22.12. Empfohlen und im Projekt festgelegt ist Node.js 24.

```bash
nvm install
nvm use
npm ci
npm run dev
```

Astro zeigt anschließend die lokale Adresse im Terminal an, üblicherweise `http://localhost:4321`.

### Befehle

| Befehl | Zweck |
| --- | --- |
| `npm run dev` | Entwicklungsserver mit Live-Reload starten |
| `npm run check` | Astro- und TypeScript-Prüfung ausführen |
| `npm run build` | statische Produktionsdateien nach `dist/` bauen |
| `npm run verify` | Typecheck und Produktions-Build nacheinander ausführen |
| `npm run preview` | den erzeugten Build lokal anzeigen |

## Projektstruktur

```text
.
├── .github/workflows/deploy.yml  # GitHub-Pages-Deployment
├── public/                       # statische Dateien, CNAME und Metadaten
├── src/components/               # wiederverwendbare Astro-Komponenten
├── src/pages/                    # Startseite und 404-Seite
├── src/styles/                   # globales Design und responsive Styles
└── astro.config.mjs              # Astro- und Domain-Konfiguration
```
