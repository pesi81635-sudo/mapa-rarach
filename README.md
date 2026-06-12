# Mapa království Rarach
### Dobrodružná hra pro poutnice — Parkové muzeum Modřany

Dobrodružná venkovní hra zasazená do reálného prostředí Parkového muzea Modřany (Praha 12, vnitroblok Plácek). Hráčky putují po 12 stanovištích, plní úkoly a sbírají kouzelné pečetě. Hra trvá přibližně 90–120 minut. Vhodná pro děti ve věku 7–13 let.

**Autoři:** Emma a Petr Šimandlovi · **Reálie:** Parkové muzeum Staré Modřany

---

## Web (`materialy na vercel/index.html`)

Statická landing page nasazená na Vercel. Jedna stránka, žádné závislosti — pouze HTML + inline CSS + Google Fonts (Cinzel, Crimson Text).

### Sekce stránky

| Sekce | ID | Obsah |
|-------|----|-------|
| Hero | — | Název hry, tagline, scroll CTA |
| O hře | `#pribehu` | Co je hra, 4 feature cards (12 stanovišť, kvízy, pečetě, čas) |
| Trasa putování | `#stanoviste` | Grid 12 station chips (kód + fantasy název) |
| Dopis od Lorel | `#dopis` | Ukázka úvodního dopisu, vosková pečeť |
| Jak hrát | `#jak-hrat` | 4 kroky: tisk → pečetě → dopis → putování |
| CTA | `#hrat` | Výzva ke stažení |
| Ke stažení | `#stahnout` | Download cards se soubory ke stažení |
| Zpětná vazba | `#zpetna-vazba` | Odkaz na Google formulář |
| Footer | — | Název hry, autoři |

### Ke stažení (soubory odkazované v index.html)

| Soubor | Popis | Formát stránky |
|--------|-------|----------------|
| `MAPA.pdf` | Ilustrovaná mapa vnitrobloku, 12 stanovišť | A5 na šířku |
| `MAPA.pdf` | Totéž jako PDF | A5 na šířku |
| `herni_karty.pdf` | 12 herních karet v jednom PDF | 12× A5 na výšku |
| `pecete.pdf` | Arch 12 pečetí k vystřižení | čtverec ~18 cm |
| `dopis.pdf` | Úvodní dopis od Lorel | A5 na výšku |
| `Klic_k_hernim_kartam.pdf` | Přehledová tabulka a pokyny pro rodiče | A4 na výšku |

---

## Herní materiály

### 12 stanovišť

| č. | Kód | Stanoviště PM | Fantasy název | Typ úkolu |
|----|-----|--------------|---------------|-----------|
| I | C1 | Do Modřan přijel vlak | Železná brána | kvíz |
| II | C2 | Zlaté časy za první republiky | Věž světla | kreativní |
| III | C3 | Husákova zeměkoule | Šedý spánek | pozorovací |
| IV | C4 | Čechova čtvrť | Elfí čtvrť | kreativní |
| V | C5 | Když Josefína Bakerová tančila | Kouzelný kruh tance | fyzický |
| VI | C6 | Hlas Modřan | Rada starších | rituální |
| VII | C7 | Cukrovar | Sladká kovárna | kvíz |
| VIII | C8 | Modřanská múza | Jeviště iluzí | kreativní |
| IX | C9 | Vítězství nad Prusy | Tréninkový kruh válečnic | fyzický |
| X | C10 | Zahradnická kolonie Cholupice | Zahrada kouzelných bylín | pozorovací |
| XI | C11 | Hradiště na Závisti | Stará pevnost | kvíz |
| XII | C12 | Pravěké sídliště vltavských břehů | Kámen počátků | rituální |

### Kvízové odpovědi

| Stanoviště | Odpovědi |
|------------|----------|
| C1 — Železná brána | 1881 / uhlí do cukrovaru / 224 domů |
| C7 — Sladká kovárna | 1861 / uhlí / cukrová řepa |
| C11 — Stará pevnost | Závist / ~2 000 obyvatel / volná odpověď |

Pečeť vydat po alespoň 2 ze 3 správných odpovědí (C1, C7). U C11 stačí otázky 1–2 + vyslechnutí volné odpovědi.

---

## Struktura souborů

```
materialy na vercel/       ← nasazeno na Vercel
  index.html
  MAPA.jpg / MAPA.pdf
  dopis.pdf
  herni_karty.pdf
  pecete.pdf
  Klic_k_hernim_kartam.pdf
  01–12 - *.pdf            (jednotlivé karty)

uvodní foto/
  herní karty/             ← zdrojové PNG karet (1054×1492 px)
  dopis mapa pečetě klíč/  ← zdrojové PNG grafik

tisk/                      ← tiskové verze (300 DPI)
  herní karty/*.jpg
  MAPA.jpg / dopis.jpg
  Klíč k herním kartám.png
  pečetě.png / pečetě_arch.png
  pečetě/*.png             (12 jednotlivých pečetí, ~2 cm ⌀)

output/                    ← textové podklady a dokumentace
  hra.md                   ← kompletní herní scénář
  klic.md                  ← přehledová tabulka pro rodiče
  vnitroblok.md            ← dokumentace Parkového muzea
  mapa.md                  ← popis mapy a stanovišť
  znak_modran.md           ← heraldický popis znaku Prahy 12
  vizualni_styl.md         ← design system: barvy, fonty, komponenty
```

---

## Vizuální styl

Středověký rukopis / fantasy mapa. Fonty: **Cinzel** (nadpisy) + **Crimson Text** (tělo).

| Token | Hex |
|-------|-----|
| Pergamen | `#f5edd6` |
| Tmavě hnědá (inkoust) | `#2c1f07` |
| Záhlaví | `#5c3a1e` |
| Tmavé zlato | `#8b6914` |
| Světlé zlato | `#c9a84c` |
| Královská modrá (pečetě) | `#1a3a6e` |

Podrobný design system: `output/vizualni_styl.md`
