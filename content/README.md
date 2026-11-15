# dr KASIA DENT — paczka treści Markdown PL/EN

**Wersja audytowana: 2026-11-15.** To paczka treści do integracji, **nie gotowy projekt strony**.

## Co zawiera paczka

- 12 par stron PL/EN (`*_pl.md`, `*_en.md`): strona główna, O mnie, siedem usług, cennik, pierwsza wizyta, kontakt.
- 3 pary artykułów blogowych PL/EN. Polskie teksty są zatwierdzone z zastrzeżeniem weryfikacji medycznej; **tłumaczenia EN zatwierdzone przez właściciela; weryfikacja medyczna pozostaje wymagana**.
- `docs/DECISIONS_1-55.md` — ustalenia właściciela z rozmów.
- `docs/CONTENT_AUDIT.md` — zakres audytu, wykryte luki, rozbieżności i zadania przed publikacją.
- `WYMAGANIA_DLA_CLAUDE.md` — historyczne wymagania; w razie rozbieżności pierwszeństwo mają nowsze decyzje i `CLAUDE.md` z GitHub.

## Zasady pracy

1. Nie zmieniać zatwierdzonych polskich treści, cen i metadanych bez zgody właściciela.
2. Wersja początkowa strony to HTML/CSS/JS (decyzja 3), nie Astro; migracja do Astro może nastąpić później.
3. Wersje PL i EN uruchamiamy razem, po akceptacji tłumaczeń i testach.
4. **Wersje EN są zaakceptowane językowo**, a mapa URL EN zatwierdzona; przed publikacją nadal potrzebne są wdrożenie tras, testy i weryfikacja medyczna.
5. Dat artykułów **nie wyświetlać** (decyzja 81 B); metadane techniczne dat, jeśli potrzebne, nie powinny zmieniać prezentacji. Treści medyczne podlegają kontroli lekarza.
6. Parser frontmatter musi obsługiwać istniejące konwencje pól, m.in. `metaTitle`/`metaDescription` i `meta_title`.
7. Informacje o logo i zdjęciach to placeholdery, nie zasoby graficzne.

## Decyzje kontaktowe

Poniedziałek: 9:00–18:00. Czwartek: 13:00–19:00. E-mail: `drkasiadent@gmail.com`. Informacja o parkingu zachowana z zatwierdzonego Markdown.

Przed integracją przeczytaj **`../docs/IMPLEMENTATION_GUIDE.md`**, **`../docs/DECISIONS.md`**, **`docs/CONTENT_AUDIT.md`**, **`docs/DECISIONS_1-55.md`** oraz **`docs/URL_MAP_PL_EN.md`**.