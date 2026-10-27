# Duolingo_z_Wishe

Aplikace pro učení angličtiny (UI v češtině) inspirovaná Duolingem. Jediný soubor `index.html` (HTML + CSS + JS bez závislostí) – GitHub Pages vyžaduje právě tento název.

## Spuštění
Otevři `index.html` v prohlížeči (žádný build, žádný server).

## Architektura (`index.html`)
- `COURSE` – obsah kurzu: úroveň (`beginner|intermediate|advanced`) → jednotky → lekce → `items` (en/cs) + `sentences`.
- `state` – postup uložený do `localStorage` (klíč `duolingo_z_wishe_v1`): úroveň, XP, streak, hotové lekce, srdíčka.
- Obrazovky: `screenWelcome` (výběr pokročilosti), `screenHome` (cesta lekcí), `screenExercise`, `screenDone`, `screenFail`.
- Typy cvičení generuje `buildExercises`: `choice` (výběr), `build` (skládání věty), `type` (psaní). Chybné cvičení se zopakuje na konci lekce.
- Výslovnost přes Web Speech API (`speak`).

## Konvence
- Jeden soubor `index.html`, žádné externí knihovny.
- Texty rozhraní česky, kód a identifikátory anglicky.
- Nový obsah přidávej do `COURSE`, ne do logiky.

## Nápady na další rozvoj
- Více lekcí a jednotek, další slovní zásoba
- Poslechová cvičení, spojování dvojic
- Zkouška zařazení (placement test) místo ručního výběru úrovně
- Obnova srdíček v čase, denní cíl, žebříček
- Možnost přidat další jazyky
