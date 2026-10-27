# Duolingo_z_Wishe

Aplikace pro učení japonštiny (UI v češtině; původně angličtina) inspirovaná Duolingem. Jediný soubor `index.html` (HTML + CSS + JS bez závislostí) – GitHub Pages vyžaduje právě tento název.

## Spuštění
Otevři `index.html` v prohlížeči (žádný build, žádný server).

## Architektura (`index.html`)
- `COURSE` – obsah kurzu: úroveň (`beginner|intermediate|advanced`) → jednotky → lekce → `items` (`it(jp, ro, cs)`: japonsky, romaji, česky) + `sentences` (`sn("tokeny oddělené mezerou", romaji, česky)`).
- `state` – postup uložený do `localStorage` (klíč `duolingo_z_wishe_ja_v1`): úroveň, XP, streak, hotové lekce, srdíčka.
- Obrazovky: `screenWelcome` (výběr pokročilosti), `screenHome` (cesta lekcí), `screenExercise`, `screenDone`, `screenFail`.
- Typy cvičení generuje `buildExercises`: `choice` (výběr), `build` (skládání věty), `type` (psaní romaji nebo japonsky, mezery a pomlčky se ignorují). Chybné cvičení se zopakuje na konci lekce.
- Výslovnost přes Web Speech API (`speak`, `ja-JP`).
- Úroveň beginner používá hiragana/katakana, advanced už kandži (vždy s romaji).

## Konvence
- Jeden soubor `index.html`, žádné externí knihovny.
- Texty rozhraní česky, kód a identifikátory anglicky.
- Nový obsah přidávej do `COURSE`, ne do logiky.

## Nápady na další rozvoj
- Více lekcí a jednotek, další slovní zásoba
- Samostatné lekce na učení hiragany a katakany, furigana u kandži
- Poslechová cvičení, spojování dvojic
- Zkouška zařazení (placement test) místo ručního výběru úrovně
- Obnova srdíček v čase, denní cíl, žebříček
- Možnost přidat další jazyky
