# Audyt paczki treści — 2026-11-15

## Zawartość i status

- 12 podstawowych stron w parach `_pl.md` i `_en.md` (w tym strona główna, kontakt, cennik, pierwsza wizyta, o mnie, 7 usług).
- 3 artykuły blogowe w parach `_pl.md` i `_en.md` — tłumaczenia EN są **nowymi propozycjami**, wymagają zatwierdzenia i kontroli medycznej przed publikacją.
- `README.md`, `WYMAGANIA_DLA_CLAUDE.md`, `docs/DECISIONS_1-55.md`.
- Nie ma osobnego pliku treści `/uslugi` (lista usług) ani `/blog` (lista artykułów), ponieważ są to strony indeksowe do zbudowania z istniejących materiałów; **nie wymyślać dodatkowych opisów bez zgody**.
- Nie ma jeszcze gotowych tekstów polityki prywatności/cookies ani 404; wymagają opracowania i akceptacji.

## Zmiany względem oryginalnego ZIP

- W `kontakt_pl.md` i `kontakt_en.md`: e-mail zmieniony na `drkasiadent@gmail.com`, godziny na poniedziałek 9:00–18:00 i czwartek 13:00–19:00 (decyzje 53–54).
- Uzupełniono wcześniej puste pole e-mail w `pierwsza-wizyta_pl.md` i `pierwsza-wizyta_en.md` zgodnie z decyzją 54.
- Dodano tłumaczenia EN trzech artykułów (decyzja 51).
- Dodano rejestr decyzji 1–55 i ten audyt.
- Pozostałe zatwierdzone treści PL nie są redagowane.

## Ważne rozbieżności do rozstrzygnięcia przed wdrożeniem

1. `WYMAGANIA_DLA_CLAUDE.md` wskazuje Astro, lecz nowsza decyzja 3 przewiduje HTML/CSS/JS na start. Stosować nowszą decyzję; zachować stary plik jako materiał historyczny.
2. W istniejących plikach EN część odnośników nadal prowadzi do polskich adresów URL (np. `/kontakt` i `/uslugi/...`). Nie publikować ich jako finalnych linków EN bez ustalenia mapy tłumaczonych slugów (decyzja 10).
3. Angielskie slugi nowych artykułów są propozycjami roboczymi, a nie zatwierdzoną mapą URL.
4. W komentarzu HTML `strona-glowna_pl.md` występuje pierwotny pomysł zdjęcia kobiety w Hero; decyzja 50 dopuszcza inne rozwiązania. Nie zmieniać zatwierdzonego tekstu, tylko zastosować decyzję przy projektowaniu.
5. W `strona-glowna_pl.md` jest sekcja galerii; decyzja 39 nakazuje ją ukryć do czasu prawdziwych zdjęć. Sekcji nie usuwać z pliku.
6. Decyzje 32 i 36 dotyczące sekcji „O mnie” na homepage zostały odłożone decyzją 43; nie dodawać jej na start.
7. `README.md` oryginalnej paczki opisuje stan sprzed tłumaczenia bloga; niniejszy audyt i rejestr decyzji są aktualniejsze.

## Wskazówki integracyjne

- Treści `_pl.md` są źródłem prawdy dla zatwierdzonych tekstów polskich.
- Frontmatter zawiera różne zestawy pól (`metaTitle`, `metaDescription` lub `meta_title`, `title`, `slug`, `status`). Parser powinien obsłużyć obie konwencje lub je jawnie mapować, bez automatycznego nadpisywania zatwierdzonych danych.
- Linki i routingi należy walidować przed publikacją, zwłaszcza wersję EN.
- Wszystkie obrazy, logo, formularz i dane prawne to osobne zasoby lub zadania; sama paczka Markdown nie stanowi gotowej strony.

## Aktualizacja po zatwierdzeniu mapy URL (2026-11-15)

- Właściciel zatwierdził wszystkie tłumaczenia EN, w tym trzy artykuły blogowe. Nie jest to równoznaczne z odrębną weryfikacją medyczną.
- Właściciel zatwierdził mapę URL: `content/docs/URL_MAP_PL_EN.md`.
- Linki w istniejących treściach EN ujednolicono z zatwierdzoną mapą, w tym odnośniki do usług w artykułach.
- Wcześniejsze uwagi o **braku zatwierdzenia** tłumaczeń i **braku mapy URL** są historyczne i już nieaktualne.
- Nadal wymagane przed publikacją: weryfikacja medyczna, strony indeksowe i prawne, konfiguracja faktycznych tras HTML, sprawdzenie canonical/hreflang, formularza i RODO.
