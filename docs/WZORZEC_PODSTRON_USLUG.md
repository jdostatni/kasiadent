# Wzorzec podstron usług dr KASIA DENT

Obowiązujący wzorzec dla etapu P2 i implementacji podstron usług. Zatwierdzony przez właściciela po zakończeniu etapu P1 (2026-11-26).
Źródła: decyzje D-138 i D-143–D-147 w `docs/DECISIONS.md`. Przy rozbieżności obowiązuje rejestr decyzji.
Rozszerzenia z etapu P2.1 (2026-11-27): D-152 (Stomatologia zachowawcza i Protetyka PL, ustawienia fotografii, tytuły jednowierszowe), D-153 (elementy treści: podsekcja H3 i listy), D-154 (ustalenia techniczne: metadane, semantyka list, okruszki przy 320 px, kontrolowana aktualizacja), D-155 (harmonogram przenoszenia podstron), D-156 (zamknięcie P2.1; warunkowe odstępstwo od progu kontrastu tytułu Endodoncji w WebKit).

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
- **Ustawienia fotografii i tytuł jednowierszowy (D-152):** kadr, położenie i gradient każdej usługi – w klasie modyfikującej `.usluga-hero--<usługa>` wspólnego arkusza `usluga.css`. Od 1024 px tytuł położony jak przy wyśrodkowaniu w pionie dla rzeczywistej liczby wierszy: `padding-top: calc((320px - 24px - var(--usluga-h1-wiersze, 2) * 1.14 * var(--usluga-h1)) / 2)`; zmienna `--usluga-h1-wiersze` w klasie usługi – domyślnie 2 (A2.4), tytuły jednowierszowe – 1.
- Wymagania: kontrast tytułu na zdjęciu co najmniej 4,5:1 (mierzony na pikselach pod tekstem), kluczowy element zdjęcia w pełni widoczny i nienachodzący na tytuł przy wszystkich szerokościach.

## 3. Okruszki i nawigacja

- Okruszki pod hero: Start › Usługi › nazwa usługi; `aria-label="Ścieżka nawigacyjna"` (PL) i `aria-label="Breadcrumb"` (EN); bieżąca strona bez linku, z `aria-current="page"` (D-145). Na ekranach dotykowych pole linku ok. 45 px wysokości.
- Nawigacja, menu mobilne, dolny pasek „Umów wizytę” i stopka – jak w prototypie D; pozycja **„Usługi” wyróżniona** na wszystkich podstronach usług (D-144).
- Zatwierdzone poprawki dostępności wspólnej nawigacji: `scroll-padding-bottom` nad dolnym paskiem (WCAG 2.4.11, D-144); modalne menu mobilne z pułapką fokusu, atrybutem `inert` tła, Escape i powrotem fokusu (D-145); pole kliknięcia przycisku podmenu 26 × 44 px bez zmiany wyglądu (WCAG 2.5.8, D-145); nagłówek EN przy 1100–1159 px z mniejszymi odstępami (D-146).

## 4. Treść

- **Blok wprowadzenia:** prostokąt na pełną szerokość kontenera, tło `#DCE7F7`, akapity jeden pod drugim, tekst wyrównany do lewej. Od 1024 px tekst zaczyna się na osi kolumny treści sekcji (pusta przestrzeń po lewej jest zamierzona), szerokość akapitów 600 px (ok. 65–80 znaków). Do 1023 px blok od krawędzi do krawędzi ekranu, tekst na marginesie strony. Bez zdjęć, ikon, nagłówków i dekoracji.
- **Sekcje:** od 1024 px nagłówek sekcji po lewej, treść po prawej (siatka 30/70, odstęp kolumn 64 px); do 1023 px jedna kolumna, nagłówek nad treścią. Poziome separatory między sekcjami; odstępy 56 / 48 / 40 px (desktop / tablet / telefon).
- **Elementy treści:** akapity; listy numerowane jako etapy 01–0n (wzór sekcji „Dlaczego…” z D); dalsze elementy wynikające z treści (np. podsekcje H3, listy punktowane, listy z pogrubionym początkiem) projektowane w tym samym systemie i przedstawiane właścicielowi do akceptacji przy pierwszej podstronie, która ich wymaga. Podsekcja H3, lista punktowana i lista z pogrubionym początkiem – zatwierdzone w P2.1 jako standard (D-153), opis w punkcie 4a.
- Bez dodatkowych zdjęć, ikon i dekoracji w treści, chyba że właściciel zdecyduje inaczej.
- **Treści źródłowe bez zmian:** tekst 1:1 z zatwierdzonych plików `content/*.md` (PL i EN); żadnych zmian słów, interpunkcji ani metadanych bez zgody.
- **Metadane (D-154):** `<title>` z pola `metaTitle` i `<meta name="description">` z pola `metaDescription` zatwierdzonego pliku Markdown, bez zmian treści; brak zatwierdzonych metadanych blokuje wygenerowanie strony – generator ich nie tworzy.
- **Twarde spacje (D-144):** w polskich tekstach HTML pojedyncze „a”, „i”, „o”, „u”, „w”, „z” łączone `&nbsp;` z następnym wyrazem; na etapie przygotowania HTML, nie w plikach Markdown; nie dotyczy tekstów angielskich.
- **Telefon (D-145–D-147):** PL „505 518 718”, EN „+48 505 518 718”; link zawsze `tel:+48505518718`.

## 4a. Elementy treści zatwierdzone w P2.1 (D-153, D-154)

- **Zasada:** standard wszystkich podstron usług PL i EN; reguły we wspólnym arkuszu `usluga.css` (sekcja „ELEMENTY TREŚCI”). Wyłącznie tokeny prototypu D i zatwierdzone fonty; bez kart, ramek, ikon i efektów. Szerokość wyznacza kolumna tekstu (od 1024 px `--usluga-tekst: 600px`, do 1023 px pełna szerokość z marginesem strony) – dłuższe teksty EN łamią się naturalnie. Semantyka z Markdown: `###` → `<h3>`, `- ` → `<ul>` / `<li>`, `**…**` → `<strong>`. Zatwierdzonych wartości nie zmienia się bez decyzji właściciela.
- **Podsekcja H3** (`.usluga-tresc .prose h3`): Source Serif 4, grubość 600, kolor `#113269`; rozmiar `clamp(1.1875rem, 1.05rem + .55vw, var(--fs-h3))` – 19 px przy szerokości okna do 400 px, płynnie do 20,8 px (`--fs-h3` = 1,3 rem) osiąganych przy ok. 727 px; interlinia 1,25; margines 32 px nad i 10 px pod nagłówkiem, od 768 px 40 px nad; `text-wrap: balance`; jako pierwszy element kolumny – bez górnego marginesu. Hierarchia: H1 32–48 px, H2 sekcji 24–32 px, H3 19–20,8 px, tekst 18 px.
- **Lista punktowana** (`.usluga-tresc .prose ul`): natywne znaczniki – `list-style: square`, znacznik w kolorze `#113269` (`::marker`); lista `margin: 0 0 1.1em`, `padding-left: 1.25em`; pozycja `margin: 0`, `padding: 3px 0 3px 4px`, `text-wrap: pretty`; dłuższe pozycje zawijają się z wcięciem (kolejne wiersze na osi tekstu pozycji); tekst Source Sans 3, 18 px, interlinia 1,65, kolor `#1A2230`.
- **Lista z pogrubionym początkiem – wariant A z separatorami** (`ul.usluga-lista-opis`; klasę nadaje generator, gdy każda pozycja listy zaczyna się od pogrubienia): bez znaczników (`list-style: none`, `padding: 0`), `margin: 20px 0 0`, linia górna `1px solid #C9D3E0`; pozycja `padding: 18px 0 20px` z linią dolną `1px solid #C9D3E0`; pogrubiony początek (`<strong>`, 600, `#1A2230`) i opis – jeden element listy, w jednym ciągu tekstu. Zakończenie: na końcu sekcji ostatnia pozycja bez linii dolnej i dolnego dopełnienia (listę zamyka separator sekcji); gdy po liście następuje dalsza treść – linia dolna ostatniej pozycji (dopełnienie 20 px) i margines 24 px pod listą. Wariant B (bez separatorów) – wyłącznie propozycja historyczna.
- **Semantyka list (D-154):** struktury `ul` / `ol` > `li`; listy bez standardowych znaczników (CSS `list-style: none`) – lista etapów (`ol`) i lista z pogrubionym początkiem – z `role="list"` (heurystyka WebKit/VoiceOver dla list bez znaczników), bez zmiany wyglądu; lista punktowana z natywnymi znacznikami – bez atrybutów ARIA.
- **Responsywność:** elementy jednakowe przy wszystkich szerokościach, z wyjątkiem rozmiaru i górnego marginesu H3.

## 5. Responsywność, dostępność i testy

- Progi: 768 px, 1024 px (układ hero i sekcji), 1100 px (menu desktop). Brak przewijania poziomego od 320 px.
- WCAG 2.2 AA: kontrast, hierarchia nagłówków (jeden H1), widoczny i niezasłonięty fokus, obsługa klawiaturą, cele dotykowe, `alt=""` dla dekoracyjnego zdjęcia hero.
- Kontrola każdej podstrony: treść = Markdown; twarde spacje; etykieta okruszków; telefon; wyróżnienie „Usługi”; układ przy 390 / 768 / 1024 / 1440 px; łamanie tytułu; kontrast tytułu na zdjęciu; klawiatura (Tab i Shift+Tab, menu); walidator HTML.
- Testy rozszerzone (Chromium, Firefox, WebKit, Lighthouse, axe) – dla kompletu podstron na zakończenie etapu i przy implementacji.
- **Okruszki przy 320 px (D-154):** dłuższa nazwa usługi może przechodzić do kolejnego wiersza razem z separatorem – dopuszczalne przy braku przewijania poziomego i obcięcia tekstu oraz zachowanej czytelności, semantyce i dostępności.
- **Regresja i aktualizacja zaakceptowanych podstron (D-154):** przy zmianach wspólnych elementów – regresja wizualna zatwierdzonych usług w Chromium, Firefox i WebKit przy 320, 390, 768, 1023, 1024, 1150, 1440 i 1920 px; zaakceptowaną podstronę aktualizuje się wyłącznie procedurą kontrolowanej aktualizacji (kopia archiwalna z sumą SHA-256, nowa wersja w odrębnym katalogu testowym, pełny diff i kontrola zakresu zmian, regresja wizualna, kontrola linków, zatwierdzona suma w konfiguracji generatora).

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
- Testy list (w tym list z `role="list"`) z VoiceOver w Safari na urządzeniach Apple przed publikacją (D-154).
- Weryfikacja kontrastu hero Endodoncji (tytuł na fotografii) w rzeczywistym Safari na urządzeniu Apple przed publikacją; ponowna ocena warunkowego odstępstwa od progu 4,5:1 (WebKit – Playwright na Windows, 1440 px, 4 piksele, minimalny kontrast 4,43:1; identycznie w A2.4; przyczyna nieustalona) na podstawie wyników tych testów; w razie potwierdzenia problemu – propozycja korekty gradientu do osobnej akceptacji właściciela (D-156). Ogólny próg 4,5:1 (D-148) bez zmian.
- Kontrast desktopowego hero PL strony głównej w WebKit (0,3–1,7% pikseli nagłówka poniżej 3:1 przy 1180 i 1440 px w Playwright WebKit dla Windows) – otwarta kwestia do weryfikacji, nie potwierdzony problem wyłącznie środowiska testowego.
- Nagłówek PL w Firefoksie przy 1100 px – treść wchodzi ok. 7 px w wewnętrzny margines kontenera (bez przewijania poziomego).

## 8. Przenoszenie podstron do katalogu docelowego (D-155)

- Etap 1 – po akceptacji P2.5: archiwizacja strony S1 Endodoncji PL; przeniesienie siedmiu podstron usług PL, strony zbiorczej „Usługi” PL oraz wymaganych wspólnych arkuszy CSS, skryptów i zasobów graficznych; weryfikacja linków i zasobów. Strona S1 Endodoncji EN – do etapu 2.
- Etap 2 – po akceptacji P2.7: archiwizacja strony S1 Endodoncji EN; przeniesienie siedmiu podstron usług EN i strony zbiorczej „Services” EN; weryfikacja wspólnych zasobów i przełączania języków.
- P2.8 – testy końcowe 16 podstron w docelowym katalogu prototypów.
- Mechanizm przenoszenia (dry-run domyślnie, wykaz plików, kontrola kompletności, kopie archiwalne z datą, sumy SHA-256 przed i po, ochrona przed nadpisaniem, przywracanie, kontrola linków i zasobów) – do akceptacji właściciela przed użyciem; każde przeniesienie wymaga osobnej zgody.
