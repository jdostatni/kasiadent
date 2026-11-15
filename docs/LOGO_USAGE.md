# Zasady użycia logo — dr KASIA DENT

**Status:** zatwierdzone przez właściciela w rozmowie 15.11.2026. Zasady wiążące dla koncepcji Claude Design. Zmiany wymagają odrębnej akceptacji właściciela.

## Pliki źródłowe (SVG, napisy zamienione na ścieżki)

| Plik w `assets/logo/` | Rola |
|---|---|
| `zab_KD_logo_napis_poziomo_web.svg` | **Logo podstawowe** — nagłówek desktop; ząb po lewej i napis w jednej linii |
| `zab_KD_samo_logo_web.svg` | **Nagłówek mobilny** — sam ząb KD; **favicon** — oryginalny ząb KD |
| `zab_KD_logo_napis_poziomo_2_linie_web.svg` | **Stopka** — ząb po lewej, napis w dwóch liniach |
| `zab_KD_logo_napis_poziomo_ponizej_web.svg` | Wariant pomocniczy, nieprzypisany do stałego miejsca |
| `napis_poziomo_sam_web.svg` | Wariant pomocniczy: sam napis w jednej linii |
| `napis_poziomo_2_linie_web.svg` | Wariant pomocniczy: sam napis w dwóch liniach |

**Ważne:** dwa warianty dwuliniowe to poprawione pliki dostarczone jako `...(1).svg` 15.11.2026; w repozytorium zapisane pod kanonicznymi nazwami bez `(1)`. Wszystkie sześć plików nie zawiera obiektów `<text>`; zachowano oryginalne ścieżki wektorowe.

## Zatwierdzone zastosowania

1. Desktop: logo podstawowe poziome; w nagłówku po lewej.
2. Mobile: **tylko sam ząb KD** w nagłówku, nie pełny napis.
3. Stopka: ząb po lewej + napis `dr KASIA / DENT` w dwóch liniach. **Położenie całego logo w stopce nie jest jeszcze zatwierdzone**: Claude Design pokazuje różne propozycje w trzech koncepcjach; wybiera właściciel.
4. Favicon: **oryginalny ząb KD**, bez upraszczania, bez zastępowania samym obrysem. Rozmiary i czytelność do przetestowania; ewentualne uproszczenie wymaga nowej zgody.
5. Warianty pomocnicze nie mogą zastępować powyższych zatwierdzonych wyborów bez nowej zgody.

## Instrukcja dla Claude Design — przekazanie do etapu koncepcji

- Przygotuj **trzy rzeczywiście różne koncepcje wizualne strony głównej**, każda z widokiem **desktop i mobile**. Na tym etapie nie projektuj pozostałych podstron i nie implementuj strony.
- Użyj **rzeczywistych plików SVG** z `assets/logo/`, nie placeholderów ani przerysowanych znaków. Nie zmieniaj ścieżek, proporcji, liter, kolorów logo, nie generuj nowego logo.
- We wszystkich trzech koncepcjach zachowaj zatwierdzone zastosowania: desktop pełne logo poziome, mobile sam ząb KD, stopka ząb + napis dwuliniowy, favicon oryginalny ząb KD.
- Pokaż trzy warianty **położenia logo w stopce** w kontekście całej stopki; wyraźnie oznacz, że wybór nie został dokonany.
- Wszystkie **siedem usług** prezentuj z równą rangą wizualną (decyzja 182 B). Nie przenoś priorytetów SEO P1/P2/P3 na hierarchię kart usług.
- Przed makietami przedstaw trzy kierunki wizualne z uzasadnieniem, paletą HEX, typografią i licencjami, zgodnie z `DESIGN.md`; czekaj na zgodę właściciela. Nie przyjmuj proponowanych tokenów UI za zatwierdzone.
- Nie wymyślaj treści medycznych, danych gabinetu ani zdjęć personelu. Korzystaj z zatwierdzonych treści repozytorium; brakujące fotografie oznacz placeholderami.
- Właściciel wybiera jedną koncepcję albo elementy do połączenia. **Claude Code nie rozpoczyna implementacji bez odrębnej zgody**.
- Stosuj `CLAUDE.md`, `DESIGN.md`, `docs/DECISIONS.md`, `content/docs/URL_MAP_PL_EN.md`, `docs/SEO.md`.

## Kontrole techniczne przed użyciem w WWW

- Sprawdź poprawne renderowanie SVG, rozmiary i czytelność w rzeczywistym nagłówku mobilnym, stopce i przy 16/32/64 px favicony.
- Nie traktuj plików SVG jako gotowych do produkcyjnego użycia bez przeglądu bezpieczeństwa SVG, dostępności, wielkości zasobów i testów w przeglądarkach.
- Nie dodawaj obcych fontów, nie zmieniaj oryginalnych plików bez zgody właściciela.

## Status przekazania

Zasoby i instrukcje przygotowane w repozytorium dla Claude Design. **Nie jest to potwierdzenie, że Claude Design uruchomił się, przeczytał dokument lub wygenerował koncepcje.** Rozpoczęcie prac projektowych i zatwierdzenie kierunków wizualnych pozostają odrębnym krokiem.
