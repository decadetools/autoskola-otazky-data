# Data otázek do autoškoly

Veřejné datové soubory pro výuku a procvičování. Dostupné také přes [GitHub Pages](https://decadetools.github.io/autoskola-otazky-data/).

| Soubor | Obsah |
| --- | --- |
| `questions_etesty_prod.json` | České otázky a odpovědi |
| `pre_generated_exams.json` | Předgenerované testy |
| `testy-nanecisto.json` | Testy nanečisto |
| `difficult_questions.json` | Index obtížných otázek |
| `text_image_video_sort.json` | Rozdělení otázek podle typu média |
| `traffic_signs.json` | Legacy data značek, zachovaná pro kompatibilitu starších aplikací |
| `question-content.json` | Překlady otázek EN/RU/UK a české vysvětlivky |
| `question-content-v1.json` | Verze a kontrolní údaje k překladům a vysvětlivkám |

`traffic_signs.json` je starší datový zdroj. Nové řešení značek má data přímo v aplikaci a tento soubor nepotřebuje. Soubor ani jeho URL zatím neodstraňovat a nepřejmenovávat; zachování chrání starší instalace.

## Aktualizace

- Aktualizovat obsah stávajících souborů; zachovat názvy, URL, strukturu a identity otázek i odpovědí.
- `question-content.json` a `question-content-v1.json` jsou generovaná dvojice. Publikovat je společně a kontrolní údaje neupravovat ručně. `v1` označuje formát, nikoli pořadí aktualizace.
- Před zveřejněním ověřit správnost dat, reference testů a shodu překladů s českým zdrojem. Po zveřejnění ověřit skutečné soubory na GitHub Pages.
- Starší obsah uchovává historie Gitu. Při návratu ke starším překladům znovu vygenerovat odpovídající manifest s novým datem vydání.

Do tohoto repozitáře patří distribuovaná data a jejich stručný popis. Pracovní podklady, interní postupy a přístupové údaje sem nepatří.
