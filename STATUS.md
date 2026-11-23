# STATUS — mobilTestWebApp

Senest opdateret: 2026-11-23

## Tilstand

**Afsluttet.** Målet er nået: statisk side → GitHub Pages → installeret på
mobilens hjemmeskærm → opdatering bekræftet.

## Bekræftet på telefon

- Appen kan installeres fra https://michaelmadsen2204.github.io/mobilTestWebApp/
  og kører fra hjemmeskærmen.
- **Opdateringer slår igennem af sig selv.** Versionsmærket blev ændret til `v2`
  og pushet (`6027a90`). Efter cirka et minut, og efter at appen var lukket og
  åbnet igen, viste den `v2`.
- **`localStorage` overlever kodeopdateringer.** Tælleren beholdt sit tal.

## Lært

- Uden en service worker er den installerede app reelt et bogmærke uden
  adresselinje. Ny kode hentes ved næste kolde start. Den eneste mulige
  forsinkelse er GitHub Pages' HTTP-cache (`max-age=600`, cirka 10 minutter).
- Data i `localStorage` hører til domænet og stien, ikke til koden. Flyttes
  appen til en anden URL, starter tælleren forfra.
- Versionsmærket (`#version` i `index.html`) tælles op ved hver ændring, så det
  er let at se, hvilken version telefonen kører.

## Ikke afprøvet

- Offline-adfærd: hvad appen viser, når der ikke er netværk.
- Service worker og en egen opdateringsstrategi. Det er bevidst fravalgt, se
  `CLAUDE.md`.
