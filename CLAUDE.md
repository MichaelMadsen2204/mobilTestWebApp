# CLAUDE.md — mobilTestWebApp

## Formål

Minimal test-webapp til at lære flowet: statisk side → GitHub Pages → installerbar
på mobilens hjemmeskærm. Appen er én stor knap, der tæller op og husker tallet i
`localStorage`. Hold det så simpelt som muligt.

Live: https://michaelmadsen2204.github.io/mobilTestWebApp/

## Filstruktur

| Fil | Indhold |
|---|---|
| `index.html` | Hele appen: HTML, inline CSS og inline JS |
| `manifest.json` | Web app manifest (navn, farver, `display: standalone`, ikoner) |
| `icon.svg` | Kildeikon (vektor) |
| `icon-192.png`, `icon-512.png` | PNG-ikoner til Android og `apple-touch-icon` |
| `CLAUDE.md` | Denne fil |

## Regler

- **Ingen afhængigheder, intet build.** Ingen frameworks, npm, bundlere eller
  CDN-scripts. Det, der ligger i repoet, er præcis det, der serveres.
- **Ingen service worker.** Appen virker derfor ikke offline — det er bevidst.
- Brug relative stier (`./`, `icon.svg`), fordi siden ligger under
  `/mobilTestWebApp/` og ikke i domænets rod.
- Ændres ikonet, så opdater `icon.svg` og generer PNG'erne igen i samme farver
  (`#1e293b` baggrund, `#f59e0b` cirkel).

## Deploy

GitHub Pages serverer `main` / root. Hvert push til `main` deployes automatisk
(typisk under et minut). Push derfor kun kode, der virker, til `main`.

## Arbejdsform

Dansk i samtale, kode-kommentarer og commit-beskeder. Små trin, commit efter hvert
trin, der virker.
