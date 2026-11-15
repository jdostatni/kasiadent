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

## Decyzje z konsultacji projektu strony — numery rozmowy 56–118

Poniższe zatwierdzenia właściciela przeniesiono z rozmowy projektowej. Numery **56–118** są numerami pytań z rozmowy, a identyfikatory **D-002–D-064** są identyfikatorami rejestru GitHub. Data rejestracji: 2026-11-15; daty poszczególnych wcześniejszych zatwierdzeń nie są tu osobno potwierdzone. Wszystkie poniższe wpisy mają źródło „własna decyzja właściciela”. Uzasadnienie: zaakceptowany wariant projektowy; w razie rozbieżności obowiązuje późniejsza decyzja wskazana w opisie.

### D-002 – decyzja 56: Hosting
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Hosting
- **Opis:** Wybór hostingu Hostido/ViperHost odłożony do etapu przed publikacją.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 56
- **Status:** Zatwierdzona

### D-003 – decyzja 57: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Formspree po weryfikacji RODO; rezerwowo formularz PHP na własnym hostingu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 57
- **Status:** Zatwierdzona

### D-004 – decyzja 58: Prywatność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Prywatność
- **Opis:** Przygotować projekt polityki prywatności i cookies PL/EN do weryfikacji prawnej.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 58
- **Status:** Zatwierdzona

### D-005 – decyzja 59: Publikacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Publikacja
- **Opis:** Bez sztywnej daty; PL i EN uruchomić razem po ukończeniu i testach.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 59
- **Status:** Zatwierdzona

### D-006 – decyzja 60: Środowisko testowe
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Środowisko testowe
- **Opis:** Ostateczna decyzja C zastępuje wcześniejszą B (testy wyłącznie lokalne): prywatne środowisko pod https://www.kasiadent.pl/test/, chronione hasłem; testowe EN pod /test/en/. Wdrożenie zależy od hostingu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 60
- **Status:** Zatwierdzona

### D-007 – decyzja 61: Proces
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Proces
- **Opis:** GitHub głównym źródłem; praca na gałęziach, przegląd i akceptacja przed publikacją.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 61
- **Status:** Zatwierdzona

### D-008 – decyzja 62: SEO lokalne
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** SEO lokalne
- **Opis:** Priorytet Reda i okoliczne wsie/miejscowości, również Rumia i Wejherowo; bez sztucznego nasycania tekstów nazwami. Dodatkowe miejscowości były propozycją, nie zatwierdzoną listą.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 62
- **Status:** Zatwierdzona

### D-009 – decyzja 63: Wizytówka Google
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Wizytówka Google
- **Opis:** Wizytówka Google gabinetu jeszcze nie istnieje; utworzyć i zweryfikować przed publikacją.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 63
- **Status:** Zatwierdzona

### D-010 – decyzja 64: Obrazy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Obrazy
- **Opis:** Automatyczna optymalizacja: WebP/AVIF gdy obsługiwane, responsywne rozmiary, lazy loading poza pierwszym ekranem.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 64
- **Status:** Zatwierdzona

### D-011 – decyzja 65: Testy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Testy
- **Opis:** Jedno wspólne konto dostępowe do prywatnego środowiska testowego.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 65
- **Status:** Zatwierdzona

### D-012 – decyzja 66: Testy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Testy
- **Opis:** Formularz w trybie testowym; zgłoszenia oznaczone TEST i nieobsługiwane jako zgłoszenia pacjentów.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 66
- **Status:** Zatwierdzona

### D-013 – decyzja 67: Backup
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Backup
- **Opis:** GitHub plus kopie zapasowe hostingu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 67
- **Status:** Zatwierdzona

### D-014 – decyzja 68: Dostępność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Dostępność
- **Opis:** WCAG 2.2 AA jako cel projektowy; wymagane również testy manualne.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 68
- **Status:** Zatwierdzona

### D-015 – decyzja 69: Testy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Testy
- **Opis:** Rozszerzone testy Windows, Android, iPhone, tablet; Chrome, Firefox, Edge i Safari; PL/EN.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 69
- **Status:** Zatwierdzona

### D-016 – decyzja 70: Wydajność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Wydajność
- **Opis:** Cel co najmniej 90 Lighthouse w każdej z czterech kategorii na mobile i desktop, dla reprezentatywnych podstron.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 70
- **Status:** Zatwierdzona

### D-017 – decyzja 71: Proces
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Proces
- **Opis:** Wszystkie aktualizacje przez PR i akceptację właściciela przed merge; pilne poprawki bezpieczeństwa mają priorytet, lecz też wymagają zgody.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 71
- **Status:** Zatwierdzona

### D-018 – decyzja 72: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Imię, e-mail, wiadomość i telefon (wówczas opcjonalny); zachować minimalizację danych i ostrzeżenie, by nie przesyłać danych medycznych. Obowiązkowość telefonu doprecyzowuje decyzja 104.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 72
- **Status:** Zatwierdzona

### D-019 – decyzja 73: Monitoring
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Monitoring
- **Opis:** Automatyczny monitoring dostępności strony i certyfikatu HTTPS z powiadomieniami e-mail.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 73
- **Status:** Zatwierdzona

### D-020 – decyzja 74: Odbiór
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Odbiór
- **Opis:** Formalna checklista odbioru: wygląd, PL/EN, linki, formularz, mobile, SEO, bezpieczeństwo, wydajność; publikacja po akceptacji.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 74
- **Status:** Zatwierdzona

### D-021 – decyzja 75: Publikacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Publikacja
- **Opis:** Kontrolowane uruchomienie po testach /test/; sprawdzić HTTPS, przekierowania, formularz, PL/EN i indeksowanie.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 75
- **Status:** Zatwierdzona

### D-022 – decyzja 76: Utrzymanie
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Utrzymanie
- **Opis:** 14 dni wzmożonej kontroli po publikacji; poprawki nadal wymagają zgody.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 76
- **Status:** Zatwierdzona

### D-023 – decyzja 77: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Każdy nowy artykuł wymaga akceptacji PL/EN, metadanych i linków przed publikacją.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 77
- **Status:** Zatwierdzona

### D-024 – decyzja 78: Rollback
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Rollback
- **Opis:** Zachować ostatnią działającą wersję dla szybkiego wycofania nieudanej publikacji.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 78
- **Status:** Zatwierdzona

### D-025 – decyzja 79: Usługi
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Usługi
- **Opis:** Indeks /uslugi: siedem kart, nazwa, krótkie opisy z zatwierdzonych materiałów i linki.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 79
- **Status:** Zatwierdzona

### D-026 – decyzja 80: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Indeks bloga: karty artykułów, wprowadzenie, link Czytaj więcej. Wcześniejszy element daty na kartach zastępuje decyzja 81.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 80
- **Status:** Zatwierdzona

### D-027 – decyzja 81: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Nie wyświetlać dat publikacji artykułów, także na kartach bloga.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 81
- **Status:** Zatwierdzona

### D-028 – decyzja 82: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Jako autora wyświetlać tylko nazwę gabinetu dr KASIA DENT, bez imienia i nazwiska.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 82
- **Status:** Zatwierdzona

### D-029 – decyzja 83: Proces
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Proces
- **Opis:** Poprawki strony testowej rejestrować w uporządkowanym rejestrze, preferowane GitHub Issues.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 83
- **Status:** Zatwierdzona

### D-030 – decyzja 84: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Bez wyszukiwarki bloga w pierwszej wersji.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 84
- **Status:** Zatwierdzona

### D-031 – decyzja 85: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Bez sekcji powiązanych artykułów.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 85
- **Status:** Zatwierdzona

### D-032 – decyzja 86: Usługi
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Usługi
- **Opis:** Bez sekcji Poznaj pozostałe usługi na końcu podstron usług.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 86
- **Status:** Zatwierdzona

### D-033 – decyzja 87: Nawigacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Nawigacja
- **Opis:** Bez przycisku Powrót na górę.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 87
- **Status:** Zatwierdzona

### D-034 – decyzja 88: Blog
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Blog
- **Opis:** Bez przycisków udostępniania artykułów.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 88
- **Status:** Zatwierdzona

### D-035 – decyzja 89: Nawigacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Nawigacja
- **Opis:** Wyróżniony przycisk Umów wizytę w sticky header desktop; prowadzi do Kontaktu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 89
- **Status:** Zatwierdzona

### D-036 – decyzja 90: Kontakt
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Kontakt
- **Opis:** Telefon jako link tel: na urządzeniach mobilnych; na desktopie numer wyświetlany jako zwykły tekst. Doprecyzowuje wcześniejszą ogólną decyzję 16.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 90
- **Status:** Zatwierdzona

### D-037 – decyzja 91: Kontakt
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Kontakt
- **Opis:** Przycisk Wyznacz trasę obok mapy, otwiera Google Maps do gabinetu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 91
- **Status:** Zatwierdzona

### D-038 – decyzja 92: Kontakt
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Kontakt
- **Opis:** Godziny przyjęć tylko na stronie Kontakt, nie w stopce.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 92
- **Status:** Zatwierdzona

### D-039 – decyzja 93: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Po wysłaniu komunikat sukcesu na tej samej stronie, bez przekierowania.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 93
- **Status:** Zatwierdzona

### D-040 – decyzja 94: Nawigacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Nawigacja
- **Opis:** Dyskretnie wyróżniać aktywną pozycję menu, także mobilnie.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 94
- **Status:** Zatwierdzona

### D-041 – decyzja 95: Nawigacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Nawigacja
- **Opis:** Mobilne Usługi rozwijają siedem usług; osobny link do indeksu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 95
- **Status:** Zatwierdzona

### D-042 – decyzja 96: Dostępność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Dostępność
- **Opis:** Bez osobnego linku Przejdź do treści; zachować pozostałe wymagania WCAG i obsługę klawiaturą. Ryzyko niespełnienia kryterium 2.4.1 WCAG wymaga weryfikacji i rozstrzygnięcia przed deklarowaniem zgodności.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 96
- **Status:** Zatwierdzona

### D-043 – decyzja 97: Nawigacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Nawigacja
- **Opis:** Mobilne menu zamyka się po wyborze linku, Escape lub kliknięciu poza nim.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 97
- **Status:** Zatwierdzona

### D-044 – decyzja 98: 404
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** 404
- **Opis:** Przyjazna strona 404 PL/EN z linkiem do homepage i poprawnym kodem HTTP 404.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 98
- **Status:** Zatwierdzona

### D-045 – decyzja 99: SEO
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** SEO
- **Opis:** Automatyczna sitemap.xml z PL/EN, bez tras testowych.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 99
- **Status:** Zatwierdzona

### D-046 – decyzja 100: Domeny
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Domeny
- **Opis:** 301 z drkasiadent.pl na https://www.kasiadent.pl i wymuszanie HTTPS.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 100
- **Status:** Zatwierdzona

### D-047 – decyzja 101: SEO
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** SEO
- **Opis:** Metadane Open Graph z zatwierdzoną grafiką podglądu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 101
- **Status:** Zatwierdzona

### D-048 – decyzja 102: SEO
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** SEO
- **Opis:** Przed publikacją sprawdzić canonical, hreflang, robots.txt, sitemap.xml; zgłosić do Search Console.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 102
- **Status:** Zatwierdzona

### D-049 – decyzja 103: CI
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** CI
- **Opis:** Każdy PR: automatyczna kontrola linków, podstawowej poprawności HTML i kompilacji/testów projektu; dla statycznego HTML bez builda nie narzucać nowego frameworka.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 103
- **Status:** Zatwierdzona

### D-050 – decyzja 104: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Obowiązkowe: imię, e-mail, telefon i wiadomość. Zastępuje opcjonalność telefonu z decyzji 72.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 104
- **Status:** Zatwierdzona

### D-051 – decyzja 105: Prywatność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Prywatność
- **Opis:** Obowiązkowe zaznaczenie pola akceptacji polityki prywatności przed wysłaniem; bez zgody marketingowej. Ostateczne brzmienie i podstawa prawna wymagają kontroli prawnej.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 105
- **Status:** Zatwierdzona

### D-052 – decyzja 106: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Wiadomości na drkasiadent@gmail.com; Reply-To ustawiony na adres pacjenta.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 106
- **Status:** Zatwierdzona

### D-053 – decyzja 107: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Bez załączników i zdjęć.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 107
- **Status:** Zatwierdzona

### D-054 – decyzja 108: Formularz
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Formularz
- **Opis:** Przy błędzie czytelny komunikat, ponowna próba oraz telefon i e-mail gabinetu.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 108
- **Status:** Zatwierdzona

### D-055 – decyzja 109: Antyspam
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Antyspam
- **Opis:** Dyskretny Cloudflare Turnstile, bez widocznego wyzwania w typowych przypadkach.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 109
- **Status:** Zatwierdzona

### D-056 – decyzja 110: Testy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Testy
- **Opis:** Środowisko /test/ chronione hasłem serwera oraz noindex, wykluczone z sitemap.xml.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 110
- **Status:** Zatwierdzona

### D-057 – decyzja 111: Prywatność
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Prywatność
- **Opis:** Nie przechowywać treści wiadomości w bazie/na serwerze strony; przesyłanie do usługi pocztowej po weryfikacji RODO.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 111
- **Status:** Zatwierdzona

### D-058 – decyzja 112: Bezpieczeństwo
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Bezpieczeństwo
- **Opis:** Logi błędów technicznych bez treści formularzy i zbędnych danych osobowych.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 112
- **Status:** Zatwierdzona

### D-059 – decyzja 113: Bezpieczeństwo
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Bezpieczeństwo
- **Opis:** Dostęp administracyjny tylko dla upoważnionych osób, z 2FA tam, gdzie dostępne.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 113
- **Status:** Zatwierdzona

### D-060 – decyzja 114: Testy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Testy
- **Opis:** Automatyczna kontrola linków zewnętrznych, ręczna weryfikacja przypadków blokowanych.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 114
- **Status:** Zatwierdzona

### D-061 – decyzja 115: Obrazy
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Obrazy
- **Opis:** Dopasowane rozmiary, kompresja, priorytet ładowania Hero.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 115
- **Status:** Zatwierdzona

### D-062 – decyzja 116: Typografia
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Typografia
- **Opis:** Fonty lokalnie hostowane, wyłącznie przy odpowiedniej licencji.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 116
- **Status:** Zatwierdzona

### D-063 – decyzja 117: Bezpieczeństwo
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Bezpieczeństwo
- **Opis:** Nagłówki HTTP: m.in. CSP, HSTS, ochrona przed osadzaniem, po testach integracji.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 117
- **Status:** Zatwierdzona

### D-064 – decyzja 118: Dokumentacja
- **Data rejestracji:** 2026-11-15 (data decyzji nieustalona osobno)
- **Obszar:** Dokumentacja
- **Opis:** Jeden aktualny dokument wdrożeniowy dla Claude Code: decyzje, mapa URL, testy i kryteria odbioru, z odsyłaczami do źródeł prawdy.
- **Uzasadnienie:** wybór właściciela po przedstawieniu wariantów.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 118
- **Status:** Zatwierdzona

