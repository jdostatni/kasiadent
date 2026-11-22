# Prototyp D — zatwierdzone wymagania C1–C7

**Status:** decyzje właściciela zatwierdzone; specyfikacja wdrożenia prototypu D.  
**Baza:** lokalny prototyp C (Granat redakcyjny premium), nie A ani B.  
**Źródło:** decyzje właściciela podczas analiz C1–C7, listopad 2026.  
**Zakres:** najpierw prototyp strony głównej desktop/mobile; nie oznacza zgody na wdrożenie całego serwisu, merge ani publikację.

## Zasady nadrzędne

1. Przeczytaj `CLAUDE.md`, `DESIGN.md`, `docs/IMPLEMENTATION_GUIDE.md`, `docs/DECISIONS.md`, zatwierdzone pliki `content/` oraz niniejszą specyfikację. W razie konfliktu z wcześniejszym opisem makiety C obowiązują nowsze, wyraźne decyzje właściciela C1–C7. Inne konflikty zgłoś.
2. Właściciel zatwierdził **przygotowanie prototypu D**, nie zmianę ani nadpisanie A/B/C. Nie wdrażaj na hosting i nie scalaj do `main` bez osobnej zgody.
3. Nie zmieniaj samodzielnie zatwierdzonych treści, logo, usług, adresów, zdjęć ani technologii. Zachowaj siedem równorzędnych usług. Kafelek konsultacji jest **dodatkowym CTA**, nie ósmą usługą.
4. Pracuj na kopii C, z zachowaniem oryginalnych zasobów; przed zmianami zweryfikuj lokalne pliki i ścieżki. D ma być oddzielnym prototypem. Nie modyfikuj katalogów analiz C1–C7.

## C1 — hero

- Zastąp zdjęcie hero wariantem `foto-start-hero2.png` z lokalnego `kasiadent-prototypy/assets/img/` (retusz uśmiechu); nie modyfikuj oryginalnych zdjęć.
- Desktop: zachowaj zatwierdzoną kompozycję i kadrowanie C.

## C2 — nawigacja desktop

- Linki menu: **15 px**, uppercase, `letter-spacing: .06em`, Source Sans 3, weight 600.
- PL/EN: **14 px**. CTA w nagłówku: **15 px**.
- Sprawdź szerokości 1100–1280 px; nie zmieniaj breakpointów arbitralnie bez analizy.

## C3 — stopka

- **Układ jak w prototypie A:** cztery kolumny: logo + wprowadzenie, nawigacja, usługi, kontakt.
- **Kolory jak w C:** granatowe tło i biały tekst, nie jasnoszara stopka A.
- W stopce użyj osobnego białego wariantu istniejącego logo SVG, bez modyfikacji oryginalnego pliku/znaku.
- **Dolny pasek copyright biały**, tylko: po lewej `© 2026 dr KASIA DENT`, po prawej `Polityka prywatności`. Bez innych tekstów w pasku.
- Sprawdź układ mobilny i działanie linków.

## C4 — kadrowanie hero na telefonie

- Wariant **W3**: dla `@media (max-width: 599px)` ustaw `.hero-img { height: calc(var(--hero-img-h) * .9); object-position: 77% 0; }`.
- Użyj `foto-start-hero2.png`. Desktop bez zmian.
- **Usuń delikatną poziomą krawędź obrazu widoczną pod gradientem**, nie zmieniając zatwierdzonego efektu gradientu.
- Sprawdź 360, 390 i 430 px.

## C5 — sekcja „Nasze usługi”

- **L4**: siedem usług w siatce, z wyróżnionym szerokim kafelkiem konsultacji na końcu; na telefonie konsultacja na końcu pojedynczej listy. Układ i proporcje oprzyj na zatwierdzonym eksperymencie `kasiadent-analiza-c5`.
- Siedem usług w zatwierdzonej kolejności: Stomatologia zachowawcza; Endodoncja mikroskopowa; Protetyka; Stomatologia estetyczna; Profilaktyka; Stomatologia dziecięca; Diagnostyka RTG. Bez zmian nazw i opisów.
- **H2 hover usług**: tło `#365572`, biały tekst i odpowiednio kontrastowe pozostałe elementy; subtelne przejście ~220 ms, także `:focus-visible`; respektuj `prefers-reduced-motion`. Na urządzeniach dotykowych kafelki pozostają zrozumiałe bez hover.
- **K1 konsultacja**: spoczynkowe tło `#1F3A63`, odróżniające CTA od usług.
- **Zatwierdzona treść konsultacji:**
  - Nagłówek: `Nie wiesz, od czego zacząć?`
  - Opis: `Zacznij od konsultacji – ocenimy stan zębów i zaproponujemy dalsze kroki.`
  - Przycisk: `UMÓW KONSULTACJĘ`; prowadzi do istniejącego Kontakt (bez fikcyjnego systemu rezerwacji).
- **Oznaczenie klikalności: zatwierdzony wariant C** z wcześniejszej analizy C5. Przed implementacją odczytaj jego dokładną definicję z lokalnych wyników / ustaleń. **Nie zakładaj automatycznie**, że chodzi o usunięcie plusa albo napisu „Dowiedz się więcej”; jeśli definicja C nie jest dostępna, poproś właściciela o doprecyzowanie.
- Responsywność: przy 1280 px popraw proporcje szerokiego kafelka konsultacji i czytelność nagłówka/przycisku; przy 768 px zachowaj czytelną zwartą kartę; przy 360–390 px nie twórz nadmiernej wysokości i odstępu przed CTA.

## C6 — „Dlaczego pacjenci wybierają dr KASIA DENT?”

- **L6**: od 1024 px dwie kolumny ~38/62; nagłówek po lewej, numerowana pionowa lista 01–04 po prawej, separatory; bez kart, ikon, ciemnych teł, sticky i animacji.
- **T2**: usuń myślniki rozpoczynające oddzielne opisy, zmień pierwszą literę każdego opisu na wielką. **Nie zmieniaj innych słów, kolejności ani istniejących linków.**
- H2 szeryfowy, płynnie **32–44 px**, `text-wrap: balance`, maksymalnie 44 px.
- Na tablecie jedna kolumna z numerem obok opisu; na telefonie numer nad tytułem. Zachowaj linki, podkreślenia i widoczny fokus.
- **Aktualizacja czwartego argumentu:** nagłówek `Przejrzyste ceny`, tekst `Poznaj nasz cennik i umów się na konsultację.` Słowo **`cennik` jest linkiem** do zatwierdzonej podstrony Cennik (polska trasa `/cennik`; zweryfikuj w mapie URL).
- Zachowaj trzy pozostałe argumenty ze źródła C, poza korektą T2.

## C7 — hamburger mobilny

- Trzy **równej długości** poziome kreski w granacie `#113269`; górna i dolna grubsze (~2.8 px), środkowa cieńsza (~1.2 px). Brak ozdobnej ramki.
- Po otwarciu menu animacja w znak **×**, po zamknięciu odwrotna, około **200 ms**; parametry dostosuj do realnej wielkości w nagłówku.
- Obszar dotykowy co najmniej 44×44 px, klawiatura, Escape, kliknięcie poza menu, `aria-expanded` i dostępna etykieta; `prefers-reduced-motion` wyłącza ruch, nie działanie menu.

## Odbiór prototypu D

- Przygotuj lokalnie oddzielny, działający prototyp D desktop/mobile, bez zmian A/B/C.
- Testy przynajmniej 360, 390, 430, 768, 1024, 1100, 1280, 1440 px: brak poziomego scrolla, czytelność, interakcje klawiaturą, kontrasty, linki, hero, stopka i menu.
- Zrzuty pełnej strony desktop/mobile i osobne ujęcia zmienionych sekcji; porównanie z C, lista zmian i nierozstrzygniętych kwestii.
- Przed kodowaniem sprawdź dokładną definicję **C5 wariant C** i dostępność źródłowych plików lokalnych. W razie braku danych zatrzymaj ten fragment i zapytaj, nie zgaduj.
- W repozytorium nie umieszczaj przypadkowo prywatnych lokalnych zdjęć lub zasobów bez sprawdzenia zgód i licencji.
- Nie wykonuj merge ani deploymentu bez osobnej zgody właściciela. Kod i dokumentacja mogą trafić do PR po przedstawieniu planu zgodnego z `CLAUDE.md`.
