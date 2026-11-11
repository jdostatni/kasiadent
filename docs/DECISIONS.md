# Rejestr decyzji właściciela projektu

Rejestr zawiera wyłącznie decyzje właściciela projektu dr KASIA DENT.
Propozycje i rekomendacje AI **nie są** tu wpisywane jako zatwierdzone. Są w `docs/REVIEW.md`.

## Zasada niezmienności
- Zatwierdzonych decyzji **nie wolno merytorycznie nadpisywać ani usuwać**.
- Nowa decyzja zastępująca poprzednią jest zapisywana jako **kolejny wpis**. Poprzedni wpis zmienia wyłącznie status na „Zastąpiona przez D-xxx" lub „Uchylona" (z datą), a jego treść pozostaje bez zmian.
- **Poprawki techniczne** (np. literówka, błędny odnośnik, formatowanie) są dopuszczalne wyłącznie po zgodzie właściciela projektu i nie mogą zmieniać treści decyzji.

## Statusy
- **Zatwierdzona**: obowiązuje i można ją wdrażać.
- **Zastąpiona**: zastąpiona nowszą decyzją (podaj identyfikator).
- **Uchylona**: przestała obowiązywać bez następcy.

## Format wpisu
| Pole | Opis |
|---|---|
| Identyfikator | `D-001`, `D-002`, … (kolejne numery, bez ponownego użycia) |
| Data | RRRR-MM-DD, data decyzji właściciela |
| Obszar | architektura / technologia / wygląd / funkcjonalność / treść / proces |
| Opis | Co zostało postanowione |
| Uzasadnienie | Dlaczego |
| Źródło | Odwołanie do przeglądu (`R-xxx`), jeśli dotyczy, albo „własna decyzja właściciela" |
| Status | Zatwierdzona / Zastąpiona przez D-xxx / Uchylona |

## Decyzje

### D-001 – Model współpracy: zgoda na całe zadanie
- **Data:** 2026-11-11
- **Obszar:** proces
- **Opis:** Po zatwierdzeniu przez właściciela konkretnego zadania (zakres, pliki, operacje) Claude Code wykonuje wszystkie wymienione w nim rutynowe czynności bez ponownych pytań: utworzenie i przełączenie gałęzi zadania, zmiany wskazanych plików, uzgodnione testy, poprawki w zakresie, `git add`, `git commit`, `git push` gałęzi zadania oraz utworzenie Pull Requesta, o ile plan je wymienia. Zgoda obowiązuje tylko w ramach danego zadania i wygasa po jego zakończeniu. Zmiany architektury, technologii, zatwierdzonych treści i wyglądu wymagają wyraźnej akceptacji właściciela; jeżeli zostały szczegółowo opisane i zaakceptowane w planie zadania, nie wymagają ponownej zgody podczas jego realizacji, a każde odstępstwo od planu wymaga nowej zgody. Zawsze wymagają osobnej zgody: merge do `main`, publikacja na hostingu (deployment), instalacja skilli, bibliotek i narzędzi, zmiana zasad bezpieczeństwa, usuwanie gałęzi, przepisywanie historii Git i inne operacje destrukcyjne. Po zadaniu Claude Code przedstawia jeden zbiorczy raport. Rekomendacje recenzji ChatGPT są wprowadzane dopiero po akceptacji właściciela.
- **Uzasadnienie:** Ograniczenie liczby pytań o drobne operacje techniczne przy zachowaniu pełnej kontroli właściciela nad decyzjami projektowymi.
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

<!-- Wzór wpisu:

### D-001 – Krótki tytuł
- **Data:** RRRR-MM-DD
- **Obszar:** …
- **Opis:** …
- **Uzasadnienie:** …
- **Źródło:** R-xxx lub „własna decyzja właściciela"
- **Status:** Zatwierdzona
-->
