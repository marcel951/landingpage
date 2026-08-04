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

## Inhalte pflegen

Die zentralen Texte, Links, Projekte und Tech-Stack-Gruppen befinden sich in [`src/pages/index.astro`](src/pages/index.astro). Das spätere Porträt kann unter `src/assets/` abgelegt und anschließend anstelle des aktuellen Platzhalters eingebunden werden.

## Deployment auf GitHub Pages

Der Workflow [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) prüft und baut die Website bei jedem Push auf `main`. Anschließend wird der erzeugte Build automatisch als GitHub Page veröffentlicht. Ein Deployment kann außerdem im Tab **Actions** manuell gestartet werden.

Einmalig im Repository einstellen:

1. **Settings → Pages → Build and deployment → Source:** `GitHub Actions`
2. Nach dem ersten erfolgreichen Workflow unter **Settings → Pages → Custom domain** die Domain `kaiser-marcel.de` speichern.
3. Beim Domainanbieter folgende DNS-Einträge setzen:

| Typ | Name | Wert |
| --- | --- | --- |
| `A` | `@` | `185.199.108.153` |
| `A` | `@` | `185.199.109.153` |
| `A` | `@` | `185.199.110.153` |
| `A` | `@` | `185.199.111.153` |
| `CNAME` | `www` | `marcel951.github.io` |

4. Sobald GitHub das Zertifikat bereitgestellt hat, **Enforce HTTPS** aktivieren. DNS-Änderungen und das Zertifikat können bis zu 24 Stunden benötigen.

`public/CNAME` und `astro.config.mjs` sind bereits für `kaiser-marcel.de` vorbereitet. Die Domain muss trotzdem in den GitHub-Pages-Einstellungen gespeichert werden. Weitere Details stehen in der [Astro-Anleitung](https://docs.astro.build/en/guides/deploy/github/) und der [GitHub-Dokumentation zu eigenen Domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

## Vor der Veröffentlichung

- optionale Kontaktadresse und Porträt ergänzen
- Inhalte und Schreibweise persönlich prüfen
- prüfen, ob Impressum oder Datenschutzerklärung erforderlich sind

## Lizenz

Sofern nicht anders angegeben, sind die Inhalte und das individuelle Design nicht zur freien Weiterverwendung lizenziert.
