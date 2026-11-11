# DESIGN.md – dr KASIA DENT

**Status dokumentu:** wytyczne projektowe oparte na projekcie dokumentu i zasadach zatwierdzonych przez właściciela projektu.
**Nie jest to zatwierdzony Design System.** Paleta, typografia, ikony, fotografie, układ sekcji i wygląd komponentów pozostają **DO ZATWIERDZENIA** (punkt 12). Wszystko, co oznaczono „DO ZATWIERDZENIA", jest propozycją lub brakiem decyzji, a nie ustaleniem.

## 0. Zasady czytania
- `CLAUDE.md`, `docs/DECISIONS.md` i zatwierdzone materiały właściciela mają pierwszeństwo przed tym dokumentem.
- Brak danych oznaczamy **DO ZATWIERDZENIA** i nie zastępujemy zgadywaniem.
- Wartości liczbowe oznaczone jako „orientacyjne" mogą być dopracowane na etapie makiety, po akceptacji właściciela.

## 1. Marka
- Gabinet: **dr KASIA DENT**, Reda.
- Lekarz: lek. dent. Katarzyna Dostatnia.
- Charakter: profesjonalna, spokojna, przejrzysta strona informacyjna dla pacjentów dorosłych i rodziców dzieci.
- Treści medyczne, cennik i kontakt wyłącznie z zatwierdzonych plików `.md`. Nie wymyślać danych ani obietnic.

## 2. Strony referencyjne
- https://www.ows-stomatologia.pl/ – inspiracja **strukturą i funkcjonalnością**: układ menu i banerów, nawigacja, mechanika strony, prezentacja usług i ikon.
- https://netgonet.pl/ – inspiracja **kolorystyką i estetyką**: biel, niebieski i granat.
- Referencje służą wyłącznie do inspiracji. Nie kopiować cudzych tekstów, zdjęć, grafik, kodu ani układu 1:1.

## 3. Kierunek wizualny (przed makietą)
Zanim powstanie makieta, Claude Design przedstawia **kierunek wizualny** wraz z uzasadnieniem każdego elementu i czeka na akceptację właściciela:

| Element | Co należy przedstawić | Status |
|---|---|---|
| Nastrój | Opis charakteru wizualnego i dlaczego pasuje do gabinetu | DO ZATWIERDZENIA |
| Paleta HEX | Pełna paleta z wartościami HEX i rolami kolorów | DO ZATWIERDZENIA |
| Typografia | Kroje pisma, licencje, skala nagłówków, sposób użycia | DO ZATWIERDZENIA |
| Motywy dekoracyjne | Kształty, linie, ilustracje, ikony, ich zakres i umiar | DO ZATWIERDZENIA |
| Charakter ruchu | Zgodny z punktem 6, wraz z uzasadnieniem | DO ZATWIERDZENIA |

Ograniczenia znane już dziś: kierunek kolorystyczny biel, niebieski, granat; zasady z punktów 5–7; bez nieuzgodnionych zewnętrznych fontów, skryptów, zdjęć i integracji.

## 4. Identyfikacja wizualna
- **Logo:** wyłącznie zatwierdzony, oryginalny plik dr KASIA DENT, bez przerabiania znaku i proporcji. Plik logo: DO ZATWIERDZENIA (wskazanie finalnego pliku przez właściciela).
- **Granat `#113269`:** kolor użyty w pracach nad logo. **Jego rola w interfejsie wymaga potwierdzenia przez właściciela** (czy ma być głównym kolorem UI).
  - Informacyjnie: kontrast `#113269` do bieli wynosi około 12,5:1 (wyliczenie, do potwierdzenia narzędziem do kontroli kontrastu).
- **Kierunek kolorystyczny:** biel / niebieski / granat.
- **DO ZATWIERDZENIA:** pełna paleta z wartościami HEX; typografia i licencje fontów; skala nagłówków; odstępy; promienie narożników; ikony; fotografie; style przycisków i kart.
- Claude Design może przedstawić warianty brakujących tokenów, ale nie może uznać ich samodzielnie za zatwierdzone. Po zatwierdzeniu tokeny trafiają do zmiennych CSS (`CLAUDE.md`, punkt 4).

## 5. Zdjęcia
- Nie generować fikcyjnych zdjęć lekarza, personelu ani gabinetu. Zdjęcia stockowe i cudze nie są używane bez zgody właściciela.
- Zdjęcia osób i materiały z wizerunkiem pacjentów: tylko po sprawdzeniu podstawy prawnej i za zgodą właściciela (`CLAUDE.md`, punkt 6).
- **Brakujące zdjęcia zastępujemy opisanymi placeholderami** umożliwiającymi późniejszą wymianę na rzeczywiste fotografie.
  - Placeholder jest wyraźnie rozpoznawalny jako zastępczy (neutralne tło i widoczny napis „ZDJĘCIE – PLACEHOLDER"), nie udaje prawdziwej fotografii.
  - Każdy placeholder ma opis w jednolitym formacie:

    | Pole | Zawartość |
    |---|---|
    | Identyfikator | np. `foto-start-hero` (nazwa pliku docelowego bez polskich znaków) |
    | Miejsce | Strona i sekcja, w której występuje |
    | Motyw | Co ma przedstawiać docelowa fotografia (opis, nie wymyślone fakty) |
    | Proporcje i orientacja | Ustalane w makiecie, DO ZATWIERDZENIA |
    | Minimalna rozdzielczość | DO ZATWIERDZENIA |
    | Tekst alternatywny PL / EN | Roboczy opis do zatwierdzenia |
    | Status | brak / dostarczone / zatwierdzone |

  - Placeholder rezerwuje miejsce o docelowych proporcjach, tak aby wymiana na zdjęcie nie zmieniała układu strony.
  - Lista wszystkich placeholderów jest częścią materiałów przekazywanych do akceptacji.

## 6. Interakcje i animacje
**Kierunek: subtelny.** Ruch ma pomagać w orientacji i dawać informację zwrotną, a nie być ozdobą.

| Rodzaj | Parametr (orientacyjny) |
|---|---|
| Interakcje (hover, focus, active) | 150–250 ms |
| Pojawianie się sekcji | 300–500 ms |
| Opcjonalne przesunięcie przy pojawianiu | 8–16 px |

Parametry mogą być dopracowane na etapie makiety i zatwierdzone przez właściciela.

**Domyślnie nie stosujemy:** preloaderów, marquee, intensywnej paralaksy, magnetycznych przycisków, tilt 3D ani wymuszonego smooth scroll. Wyjątek wymaga zgody właściciela.

Zasady dodatkowe:
- Pojawianie sekcji jest jednorazowe i nie może ukrywać treści, gdy animacja nie zadziała (patrz „Odporność" poniżej).
- Brak ruchu samoczynnego, który trwa dłużej niż kilka sekund, bez możliwości zatrzymania.
- **`prefers-reduced-motion`:** gdy użytkownik ogranicza ruch, wyłączamy lub zastępujemy animacje natychmiastową zmianą stanu, a przesunięcia nie występują. Treść pozostaje widoczna.
- **Odporność:** treści i podstawowa nawigacja są dostępne bez zewnętrznych bibliotek JavaScript. Awaria animacji nie może blokować strony ani ukrywać zawartości.
- **Wydajność:** animacje powinny być płynne, szczególnie na urządzeniach mobilnych. Preferujemy `transform` i `opacity`, a `will-change` stosujemy selektywnie. Wymagania techniczne: `CLAUDE.md`, punkt 3.

## 7. Dostępność i jakość
- Cel: **WCAG 2.2, poziom AA**, na komputerze i telefonie (podejście mobile-first).
- Kontrast: tekst co najmniej 4,5:1 (duży tekst 3:1), elementy interfejsu i ich stany co najmniej 3:1.
- Pełna obsługa klawiaturą, w tym menu desktopowe i mobilne, logiczna kolejność tabulacji.
- **Widoczny focus** na każdym elemencie interaktywnym, niezasłonięty przez inne elementy (np. przyklejony nagłówek).
- Cele dotykowe i klikalne o rozmiarze co najmniej 24 × 24 px CSS (WCAG 2.2, 2.5.8), a dla głównych akcji większe, DO ZATWIERDZENIA w makiecie.
- Struktura nagłówków bez przeskoków, semantyczny HTML, sensowne etykiety i teksty alternatywne w PL i EN.
- Atrybut języka dla wersji PL i EN oraz dla fragmentów w innym języku.
- Responsywność, czytelna hierarchia, brak poziomego przewijania.
- Bez nieuzgodnionych zewnętrznych fontów, skryptów, zdjęć i integracji.

## 8. Struktura strony
Menu: **Start · O mnie · Usługi · Cennik · Pierwsza wizyta · Blog · Kontakt**.
Przycisk **„Umów się na wizytę"** prowadzi na razie do **Kontakt**.

Siedem podstron usług:
1. Stomatologia zachowawcza
2. Endodoncja mikroskopowa
3. Protetyka
4. Stomatologia estetyczna
5. Profilaktyka
6. Stomatologia dziecięca
7. Diagnostyka RTG

- Wersje **PL i EN**, na komputer i telefon.
- **Rezerwacja online / IQDental:** planowana w przyszłości. **Nie implementować teraz.**

## 9. Komponenty do zaprojektowania
- Nagłówek, logo, menu desktopowe i mobilne, odnośnik do kontaktu.
- Hero strony głównej z zatwierdzonym tekstem i miejscem na zatwierdzone zdjęcie (do czasu dostarczenia: placeholder, punkt 5).
- Karty siedmiu usług i spójna nawigacja do podstron.
- Sekcja „O mnie", treść usług, cennik, pierwsza wizyta, blog, kontakt, stopka.
- Stany hover, focus, active i zachowanie mobilne.
- **Kolejność sekcji i ich szczegółowy wygląd są dopiero do zaprojektowania i akceptacji.**

## 10. Przebieg pracy z Claude Design
1. Wczytać ten dokument i zatwierdzone materiały `.md`.
2. Przedstawić **kierunek wizualny** (punkt 3) i poczekać na akceptację.
3. Utworzyć **wireframe strony głównej**, także dla mobile.
4. Przedstawić warianty układu do zatwierdzenia.
5. Przygotować wizualną makietę i propozycję brakujących tokenów.
6. Zatwierdzić wygląd, następnie projektować pozostałe podstrony.
7. Dopiero po akceptacji przekazać projekt do Claude Code.

- Żadnych automatycznych zmian w repozytorium, publikacji ani instalacji nowych narzędzi.
- OpenDesign i Taste Skill pozostają odłożone. UI/UX Pro Max jest narzędziem doradczym.

## 11. Zasady nadrzędne
- `CLAUDE.md`, `docs/DECISIONS.md` i zatwierdzone materiały mają pierwszeństwo.
- Zmiany wyglądu, tekstów, cen, funkcji i technologii wymagają akceptacji właściciela.
- Brak danych oznaczyć **DO ZATWIERDZENIA**, nie zastępować zgadywaniem.

## 12. Lista otwartych decyzji
- [ ] Potwierdzić rolę granatu `#113269` w UI i zatwierdzić paletę (HEX).
- [ ] Zatwierdzić fonty, licencje i sposób ich użycia.
- [ ] Wskazać finalne pliki logo i zdjęć.
- [ ] Zatwierdzić kierunek wizualny: nastrój, motywy dekoracyjne, charakter ruchu.
- [ ] Zatwierdzić parametry animacji po dopracowaniu w makiecie.
- [ ] Zatwierdzić proporcje i listę placeholderów zdjęć.
- [ ] Zatwierdzić wireframe desktop i mobile.
- [ ] Zatwierdzić wygląd strony głównej i szablonów usług.
