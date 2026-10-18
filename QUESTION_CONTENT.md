# Překlady otázek a české vysvětlivky

Nový mobilní build používá `question-content-v1.json` jako manifest. Ten odkazuje na neměnný `question-content-v1-<revision>.json` s českými vysvětlivkami a schválenými překlady otázek, odpovědí a vysvětlivek EN/RU/UK. První vydání obsahuje 1 136 otázek v každém jazyce a 1 136 českých vysvětlivek.

Původní české soubory `questions_etesty_prod.json`, `pre_generated_exams.json` a `difficult_questions.json` ani jejich URL se nemění. Starší aplikace nový manifest nečtou.

## Další aktualizace

1. Aktualizovat český zdroj a schválené vysvětlivky v projektu `autoskola`, přegenerovat SQLite seed a dotčené překlady nezávisle zkontrolovat. Zdrojový otisk zahrnuje znění, odpovědi, správnost, body a média. Překlad pro jiné znění se nepoužije.
2. V mobilním repozitáři spustit `node scripts/localization/export-remote-content.cjs <cesta-k-tomuto-repozitari>`. Export kontroluje každý překlad proti SQLite seedu, přesným redakčním podkladům a schváleným otiskům. Při neúplnosti skončí chybou. UI katalogy, značky ani audio do tohoto kanálu nepatří.
3. Publikovat nový neměnný soubor společně s manifestem (nebo soubor nejdřív, manifest až potom). Starší vydání ponechat. Původní české datasety měnit jen při skutečné aktualizaci českého zdroje.
4. Ověřit GitHub Pages URL manifestu a souboru, délku v bajtech a MD5. MD5 slouží ke kontrole poškození přenosu, ne jako podpis. Důvěryhodným distribučním kanálem je HTTPS tohoto repozitáře.

Aplikace kontroluje manifest při stávající aktualizaci datasetů, velký soubor stáhne jen při změně revize. Validovaný obsah, české vysvětlivky a vyhledávací index uloží v jedné SQLite transakci. Neúspěšné stažení/import zachová předchozí obsah. Offline spuštění obnoví uloženou verzi. Historické snapshoty a uživatelský pokrok se nemění.

## Návrat na předchozí obsah

Nastavit manifest na dřívější neměnný soubor, jeho revision/MD5/bytes, ale s novým `publishedAt`. Nový čas je potřebný, protože klient odmítá starší manifesty z cache a vydání starší než jeho bundlovaný základ. Překlady nekompatibilní s aktuálními českými otázkami se zobrazí česky.

Pro budoucí build s novějšími bundlovanými překlady použít export s `--update-baseline`, a odpovídající manifest také publikovat. Tím stará serverová verze nepřepíše novější obsah buildu.
