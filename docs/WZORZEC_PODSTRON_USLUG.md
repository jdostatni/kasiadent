# Wzorzec podstron usług dr KASIA DENT

Obowiązujący wzorzec dla etapu P2 i implementacji podstron usług. Zatwierdzony przez właściciela po zakończeniu etapu P1 (2026-11-26).
Źródła: decyzje D-138 i D-143–D-147 w `docs/DECISIONS.md`. Przy rozbieżności obowiązuje rejestr decyzji.

Szablon referencyjny (lokalny prototyp poza repozytorium, nieprzenoszony do repozytorium bez osobnej zgody):
`kasiadent-prototypy/podstrony/szkice/endodoncja-a2-4.html` + `szkic-a2-4.css`, korzystające z `kasiadent-prototypy/d/style.css`, `podstrony/assets/css/podstrony.css` i `shared/proto.js`.

## 1. Zasada ogólna

- Wszystkie siedem podstron usług korzysta z **jednego systemu projektowego** opartego na szablonie **A2.4** (podstrona „Endodoncja mikroskopowa”).
- Wspólne są: hero, okruszki, blok wprowadzenia, typografia, kolorystyka, siatka, odstępy, separatory, nawigacja i stopka. **Liczba i rodzaj sekcji wynikają z zatwierdzonej treści danej usługi** – nie muszą powtarzać struktury endodoncji.
- Kolorystyka i typografia wyłącznie z tokenów prototypu D: granat `#113269`, ciemny granat `#0B2147`, akcent na granacie `#6EA8FF`, tekst `#1A2230`, linie `#C9D3E0`; Source Serif 4 (nagłówki) i Source Sans 3 (tekst, 18 px, interlinia 1,65).
- **Bez dodatkowego bloku CTA na końcu podstrony** (D-145) – dostęp do kontaktu zapewniają nawigacja, przycisk „Umów wizytę”, dolny pasek mobilny i stopka.

## 2. Hero

- **Indywidualna fotografia dla każdej usługi**; wszystkie fotografie tworzą spójną wizualnie serię przy wspólnym szablonie hero (D-143). Każde zdjęcie wymaga akceptacji właściciela; oryginały pozostają bez zmian, na stronie kopie WebP (`srcset`, `sizes`, `fetchpriority="high"`, `width`/`height`).
- **Od 1024 px:** wysokość 320 px; tytuł po lewej z krótką kreską w kolorze akcentu; zdjęcie dosunięte do prawej, z zachowaniem proporcji; lewa krawędź zdjęcia wygaszona w granat; granatowy gradient od lewej liczony względem zdjęcia. Kadr i intensywność gradientu dobierane do każdego zdjęcia (wzór: A2.3/A2.4). Tytuł 48 px od 1440 px, płynnie 38–48 px przy 1024–1439 px; położenie tytułu liczone od góry jak przy wyśrodkowaniu (stabilność podczas ładowania fontów).
- **Do 1023 px:** zdjęcie nad tytułem (wysokość `max(min(75vw, 330px), 44vw)`), dół zdjęcia wygaszony w granat, tytuł na granacie pod zdjęciem; tytuł 32 px (telefon) – 38 px (tablet).
- Tytuł łamany wyłącznie między frazami (frazy jako `inline-block`): bez myślnika na początku wiersza i krótkich wyrazów na końcu wiersza.
- Wymagania: kontrast tytułu na zdjęciu co najmniej 4,5:1 (mierzony na pikselach pod tekstem), kluczowy element zdjęcia w pełni widoczny i nienachodzący na tytuł przy wszystkich szerokościach.

## 3. Okruszki i nawigacja

- Okruszki pod hero: Start › Usługi › nazwa usługi; `aria-label="Ścieżka nawigacyjna"` (PL) i `aria-label="Breadcrumb"` (EN); bieżąca strona bez linku, z `aria-current="page"` (D-145). Na ekranach dotykowych pole linku ok. 45 px wysokości.
- Nawigacja, menu mobilne, dolny pasek „Umów wizytę” i stopka – jak w prototypie D; pozycja **„Usługi” wyróżniona** na wszystkich podstronach usług (D-144).
- Zatwierdzone poprawki dostępności wspólnej nawigacji: `scroll-padding-bottom` nad dolnym paskiem (WCAG 2.4.11, D-144); modalne menu mobilne z pułapką fokusu, atrybutem `inert` tła, Escape i powrotem fokusu (D-145); pole kliknięcia przycisku podmenu 26 × 44 px bez zmiany wyglądu (WCAG 2.5.8, D-145); nagłówek EN przy 1100–1159 px z mniejszymi odstępami (D-146).

## 4. Treść

- **Blok wprowadzenia:** prostokąt na pełną szerokość kontenera, tło `#DCE7F7`, akapity jeden pod drugim, tekst wyrównany do lewej. Od 1024 px tekst zaczyna się na osi kolumny treści sekcji (pusta przestrzeń po lewej jest zamierzona), szerokość akapitów 600 px (ok. 65–80 znaków). Do 1023 px blok od krawędzi do krawędzi ekranu, tekst na marginesie strony. Bez zdjęć, ikon, nagłówków i dekoracji.
- **Sekcje:** od 1024 px nagłówek sekcji po lewej, treść po prawej (siatka 30/70, odstęp kolumn 64 px); do 1023 px jedna kolumna, nagłówek nad treścią. Poziome separatory między sekcjami; odstępy 56 / 48 / 40 px (desktop / tablet / telefon).
- **Elementy treści:** akapity; listy numerowane jako etapy 01–0n (wzór sekcji „Dlaczego…” z D); dalsze elementy wynikające z treści (np. podsekcje H3, listy punktowane, listy z pogrubionym początkiem) projektowane w tym samym systemie i przedstawiane właścicielowi do akceptacji przy pierwszej podstronie, która ich wymaga.
- Bez dodatkowych zdjęć, ikon i dekoracji w treści, chyba że właściciel zdecyduje inaczej.
- **Treści źródłowe bez zmian:** tekst 1:1 z zatwierdzonych plików `content/*.md` (PL i EN); żadnych zmian słów, interpunkcji ani metadanych bez zgody.
- **Twarde spacje (D-144):** w polskich tekstach HTML pojedyncze „a”, „i”, „o”, „u”, „w”, „z” łączone `&nbsp;` z następnym wyrazem; na etapie przygotowania HTML, nie w plikach Markdown; nie dotyczy tekstów angielskich.
- **Telefon (D-145–D-147):** PL „505 518 718”, EN „+48 505 518 718”; link zawsze `tel:+48505518718`.

## 5. Responsywność, dostępność i testy

- Progi: 768 px, 1024 px (układ hero i sekcji), 1100 px (menu desktop). Brak przewijania poziomego od 320 px.
- WCAG 2.2 AA: kontrast, hierarchia nagłówków (jeden H1), widoczny i niezasłonięty fokus, obsługa klawiaturą, cele dotykowe, `alt=""` dla dekoracyjnego zdjęcia hero.
- Kontrola każdej podstrony: treść = Markdown; twarde spacje; etykieta okruszków; telefon; wyróżnienie „Usługi”; układ przy 390 / 768 / 1024 / 1440 px; łamanie tytułu; kontrast tytułu na zdjęciu; klawiatura (Tab i Shift+Tab, menu); walidator HTML.
- Testy rozszerzone (Chromium, Firefox, WebKit, Lighthouse, axe) – dla kompletu podstron na zakończenie etapu i przy implementacji.

## 6. Statusy decyzji etapu P1 (raport podstron)

| Nr | Kwestia | Status |
|---|---|---|
| 1 | Nagłówek podstrony | rozstrzygnięte – hero z fotografią (D-143) |
| 2 | Okruszki i etykieta ARIA | rozstrzygnięte (D-143, D-145) |
| 3 | Układ treści na desktopie | rozstrzygnięte (D-143) |
| 4 | Blok CTA na końcu usług | zamknięte – bez bloku (D-145) |
| 5 | Typografia treści | rozstrzygnięte (D-143) |
| 6 | Wyróżnienie „Usługi” w menu | zatwierdzone (D-144) |
| 7 | Zdjęcia na podstronach usług | rozstrzygnięte – własna fotografia hero dla każdej usługi (D-143) |
| 8 | Nagłówek EN przy 1100–1159 px | zamknięte – wdrożone (D-146) |
| 9 | Hero strony głównej na tablecie | zamknięte – wdrożone (D-146) |
| 10 | Poprawki dostępności wspólnej nawigacji | zamknięte (D-144, D-145, D-146) |
| 11 | Format telefonu PL/EN | zatwierdzone – oczekuje na realizację w Git (osobny PR, D-147) |
| 12 | Wersja responsywna A2.4 | zatwierdzone (D-144) |
| 13 | Twarde spacje | zatwierdzone (D-144) |
| 14 | Optymalizacja fontów | odłożona (sekcja 7) |
| 15 | Końcowa akceptacja etapu P1 | zamknięte – etap P1 zakończony (D-147) |

## 7. Zadania odłożone (nieblokujące P2)

- Optymalizacja fontów i sposobu ich ładowania dla całej witryny (obecnie pliki TTF ok. 1,85 MB).
- Weryfikacja tytułu A2.4 i hero strony głównej na rzeczywistych urządzeniach Apple.
- Testy na iPhonie i w Safari przed publikacją.
- Kontrast desktopowego hero PL strony głównej w WebKit (0,3–1,7% pikseli nagłówka poniżej 3:1 przy 1180 i 1440 px w Playwright WebKit dla Windows) – otwarta kwestia do weryfikacji, nie potwierdzony problem wyłącznie środowiska testowego.
- Nagłówek PL w Firefoksie przy 1100 px – treść wchodzi ok. 7 px w wewnętrzny margines kontenera (bez przewijania poziomego).
