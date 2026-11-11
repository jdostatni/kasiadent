# Rejestr przeglądów i rekomendacji (ChatGPT)

Rejestr zawiera przeglądy i rekomendacje ChatGPT w roli analityka i recenzenta.

> **Rekomendacje nie są decyzjami.** Wpisy w tym pliku to opinie recenzenta, a nie ustalenia projektu.
> Wdrożenie wymaga akceptacji właściciela projektu. Zaakceptowaną rekomendację właściciel zapisuje
> jako decyzję w `docs/DECISIONS.md`, a we wpisie przeglądu pojawia się jej identyfikator `D-xxx`.
> Obowiązują wyłącznie decyzje ze statusem „Zatwierdzona" w `docs/DECISIONS.md`.

Każda rekomendacja ma **dwa niezależne statusy**: status decyzji (co postanowił właściciel) i status realizacji (co z tym zrobiono).
Realizację można rozpocząć dopiero po decyzji „Zaakceptowana".

## Status decyzji (decyduje wyłącznie właściciel projektu)
- **Oczekuje na decyzję**: właściciel jeszcze nie zdecydował.
- **Zaakceptowana**: właściciel przyjął rekomendację (podaj identyfikator `D-xxx`).
- **Odrzucona**: właściciel nie przyjął rekomendacji (krótko podaj powód).
- **Odłożona**: decyzja przesunięta w czasie.

## Status realizacji
- **Nie dotyczy**: rekomendacja nie została zaakceptowana (oczekuje, odrzucona lub odłożona).
- **Do wykonania**: zaakceptowana, prace jeszcze się nie rozpoczęły.
- **W realizacji**: prace trwają.
- **Wdrożona**: zmiana wykonana i sprawdzona (podaj commit lub PR).
- **Wstrzymana**: realizacja przerwana (podaj powód).

## Format wpisu
| Pole | Opis |
|---|---|
| Identyfikator | `R-001`, `R-002`, … (kolejne numery, bez ponownego użycia) |
| Data | RRRR-MM-DD |
| Zakres | Co zostało przejrzane (pliki, podstrony, elementy) |
| Ustalenia | Co stwierdzono (opinia recenzenta) |
| Rekomendacje | Co proponuje się zmienić (propozycja, nie decyzja) |
| Status decyzji | Oczekuje na decyzję / Zaakceptowana (D-xxx) / Odrzucona / Odłożona |
| Status realizacji | Nie dotyczy / Do wykonania / W realizacji / Wdrożona / Wstrzymana |

Zasada niezmienności jak w `docs/DECISIONS.md`: treści ustaleń i rekomendacji nie nadpisujemy ani nie usuwamy.
Zmiany statusów zapisujemy dopiskiem z datą pod wpisem. Poprawki techniczne tylko po zgodzie właściciela.

## Przeglądy

_Brak wpisów._

<!-- Wzór wpisu:

### R-001 – Krótki tytuł
- **Data:** RRRR-MM-DD
- **Autor:** ChatGPT (recenzent)
- **Zakres:** …
- **Ustalenia:** …
- **Rekomendacje:** …
- **Status decyzji:** Oczekuje na decyzję
- **Status realizacji:** Nie dotyczy
-->
