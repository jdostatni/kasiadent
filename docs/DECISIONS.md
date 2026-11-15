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


## Decyzje z konsultacji projektu — numery rozmowy 119–191

Data rejestracji: 2026-11-15. Zatwierdzone przez właściciela w rozmowie. Każda pozycja poniżej jest osobnym wpisem o statusie **Zatwierdzona**; identyfikator rejestru D-065–D-137 odpowiada numerowi rozmowy 119–191. Późniejsze decyzje mają pierwszeństwo w zakresie wyraźnie wskazanych zmian.

### D-065 – decyzja 119: Układ
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Układ
- **Opis:** Czytelna maksymalna szerokość tekstu na dużych ekranach; Hero na pełną szerokość.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 119
- **Status:** Zatwierdzona

### D-066 – decyzja 120: Mobile
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Mobile
- **Opis:** Kompaktowy sticky header ok. 64 px: logo po lewej, hamburger po prawej; dolny CTA.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 120
- **Status:** Zatwierdzona

### D-067 – decyzja 121: Obrazy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Obrazy
- **Opis:** Osobne kadrowanie zdjęć na urządzenia mobilne.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 121
- **Status:** Zatwierdzona

### D-068 – decyzja 122: Animacje
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Animacje
- **Opis:** Subtelne animacje wejścia podczas przewijania; bez paralaksy; respektować reduced motion.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 122
- **Status:** Zatwierdzona

### D-069 – decyzja 123: Dostępność
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dostępność
- **Opis:** Odpowiednio duże cele dotykowe i odstępy na telefonach.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 123
- **Status:** Zatwierdzona

### D-070 – decyzja 124: Języki
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Języki
- **Opis:** Przełącznik PL/EN przez adres URL; bez zapamiętywania preferencji i automatycznego przekierowania.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 124
- **Status:** Zatwierdzona

### D-071 – decyzja 125: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Etykiety, błędy walidacji i komunikaty sukcesu w obu językach.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 125
- **Status:** Zatwierdzona

### D-072 – decyzja 126: Publikacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Publikacja
- **Opis:** Nową podstronę publikować dopiero po zatwierdzeniu wersji PL i EN.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 126
- **Status:** Zatwierdzona

### D-073 – decyzja 127: SEO
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** SEO
- **Opis:** Unikalne meta title i description dla każdej podstrony PL/EN; osobna akceptacja.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 127
- **Status:** Zatwierdzona

### D-074 – decyzja 128: Blog
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Blog
- **Opis:** BlogPosting z autorem dr KASIA DENT i rzeczywistymi datami w metadanych; dat nie wyświetlać. Artykuły kolejno: „Jak prawidłowo myć zęby?” 2026-11-15; „Leczenie kanałowe – czego się spodziewać?” 2026-11-20; „Licówki porcelanowe czy kompozytowe?” 2026-11-25. Nie oznaczać przyszłego artykułu jako już opublikowanego przed faktyczną publikacją.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 128
- **Status:** Zatwierdzona

### D-075 – decyzja 129: Wdrożenie
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Wdrożenie
- **Opis:** Merge do main nie uruchamia automatycznie produkcji; wymagana osobna zgoda na deployment.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 129
- **Status:** Zatwierdzona

### D-076 – decyzja 130: Testy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Testy
- **Opis:** Po zatwierdzonym merge osobne wdrożenie do chronionego hasłem /test/ do przeglądu, nie automatyczne.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 130
- **Status:** Zatwierdzona

### D-077 – decyzja 131: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Przed startem rzeczywisty test dostarczenia wiadomości e-mail end-to-end.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 131
- **Status:** Zatwierdzona

### D-078 – decyzja 132: Bezpieczeństwo
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Bezpieczeństwo
- **Opis:** Sekrety poza repozytorium: konfiguracja hostingu lub GitHub Secrets.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 132
- **Status:** Zatwierdzona

### D-079 – decyzja 133: Dokumentacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dokumentacja
- **Opis:** Krótki podręcznik utrzymania: treści, artykuły, testy, deployment i rollback.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 133
- **Status:** Zatwierdzona

### D-080 – decyzja 134: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Komunikat sukcesu na stronie; bez automatycznego maila potwierdzającego do pacjenta.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 134
- **Status:** Zatwierdzona

### D-081 – decyzja 135: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Kontakt
- **Opis:** Bez automatycznej odpowiedzi poza godzinami pracy.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 135
- **Status:** Zatwierdzona

### D-082 – decyzja 136: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Zablokować przycisk wysyłania na czas oczekiwania na odpowiedź serwera.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 136
- **Status:** Zatwierdzona

### D-083 – decyzja 137: Dostępność
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dostępność
- **Opis:** Dostępne błędy walidacji przy odpowiednich polach.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 137
- **Status:** Zatwierdzona

### D-084 – decyzja 138: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Kontakt
- **Opis:** Publicznie pokazać e-mail gabinetu i zastosować standardowe zabezpieczenia antyspamowe.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 138
- **Status:** Zatwierdzona

### D-085 – decyzja 139: SEO
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** SEO
- **Opis:** Dane strukturalne Service dla siedmiu usług, zgodnie z faktyczną ofertą.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 139
- **Status:** Zatwierdzona

### D-086 – decyzja 140: SEO
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** SEO
- **Opis:** FAQ dla pacjentów; FAQPage tylko jeśli dopuszczają to aktualne wytyczne Google.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 140
- **Status:** Zatwierdzona

### D-087 – decyzja 141: Testy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Testy
- **Opis:** Na /test/ dodatkowo X-Robots-Tag, jeśli hosting obsługuje; niezależnie hasło i noindex.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 141
- **Status:** Zatwierdzona

### D-088 – decyzja 142: SEO
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** SEO
- **Opis:** Przy zmianie sluga przekierowanie 301 oraz aktualizacja linków, sitemap i canonical.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 142
- **Status:** Zatwierdzona

### D-089 – decyzja 143: Obrazy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Obrazy
- **Opis:** Opisowe nazwy plików i teksty alt adekwatne do funkcji obrazu.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 143
- **Status:** Zatwierdzona

### D-090 – decyzja 144: Blog
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Blog
- **Opis:** Nowe artykuły jako pliki repozytorium przez Claude Code i zatwierdzony PR; bez CMS na start.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 144
- **Status:** Zatwierdzona

### D-091 – decyzja 145: Cennik
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Cennik
- **Opis:** Aktualizacje cennika przez GitHub PR i akceptację; bez CMS.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 145
- **Status:** Zatwierdzona

### D-092 – decyzja 146: Proces
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Proces
- **Opis:** GitHub i Pull Requesty jako historia zmian; bez osobnego dziennika administracyjnego.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 146
- **Status:** Zatwierdzona

### D-093 – decyzja 147: Monitoring
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Monitoring
- **Opis:** Na start testy i uptime; zewnętrzny monitoring błędów przeglądarki dopiero po uzasadnieniu i analizie prywatności.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 147
- **Status:** Zatwierdzona

### D-094 – decyzja 148: Utrzymanie
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Utrzymanie
- **Opis:** Po 14 dniach wzmożonego monitoringu testy przy zmianach i przegląd techniczny kwartalnie.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 148
- **Status:** Zatwierdzona

### D-095 – decyzja 149: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Kontakt
- **Opis:** Nie dodawać osobnej informacji, że formularz nie służy do pilnych przypadków.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 149
- **Status:** Zatwierdzona

### D-096 – decyzja 150: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Kontakt
- **Opis:** Nie obiecywać konkretnego czasu odpowiedzi na wiadomość.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 150
- **Status:** Zatwierdzona

### D-097 – decyzja 151: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Kontakt
- **Opis:** W PL telefon bez prefiksu +48; w EN z prefiksem +48.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 151
- **Status:** Zatwierdzona

### D-098 – decyzja 152: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Po błędzie wysyłki zachować wpisane dane w bieżącym formularzu, bez trwałego zapisu w przeglądarce.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 152
- **Status:** Zatwierdzona

### D-099 – decyzja 153: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Formularz
- **Opis:** Bez ostrzeżenia przy opuszczaniu strony z niewysłaną wiadomością.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 153
- **Status:** Zatwierdzona

### D-100 – decyzja 154: Obrazy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Obrazy
- **Opis:** Neutralne, estetyczne zdjęcia bez drastycznych ujęć medycznych.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 154
- **Status:** Zatwierdzona

### D-101 – decyzja 155: Obrazy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Obrazy
- **Opis:** Nie przedstawiać wygenerowanych zdjęć jako autentycznych zdjęć gabinetu; ilustracje lub neutralne obrazy.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 155
- **Status:** Zatwierdzona

### D-102 – decyzja 156: Logo
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Logo
- **Opis:** Na mobile zatwierdzone logo, skalowane proporcjonalnie, bez zmiany układu.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 156
- **Status:** Zatwierdzona

### D-103 – decyzja 157: Logo
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Logo
- **Opis:** Favicon z zatwierdzonego symbolu zęba bez pełnego napisu; projekt do akceptacji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 157
- **Status:** Zatwierdzona

### D-104 – decyzja 158: Wygląd
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Wygląd
- **Opis:** Na start tylko jasny wariant strony, bez automatycznego dark mode.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 158
- **Status:** Zatwierdzona

### D-105 – decyzja 159: Mapa
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Mapa
- **Opis:** Interaktywna mapa Google ładowana bezpośrednio na Kontakcie, pod warunkiem zgodności z prywatnością i przepisami.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 159
- **Status:** Zatwierdzona

### D-106 – decyzja 160: Technologia
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Technologia
- **Opis:** Ograniczyć zewnętrzne skrypty, fonty i biblioteki do minimum.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 160
- **Status:** Zatwierdzona

### D-107 – decyzja 161: Backup
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Backup
- **Opis:** Ustalić harmonogram i retencję kopii hostingu oraz przetestować możliwość odtworzenia.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 161
- **Status:** Zatwierdzona

### D-108 – decyzja 162: Dane gabinetu
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dane gabinetu
- **Opis:** Adres, telefon, e-mail i godziny utrzymywać w jednym źródle konfiguracji, bez zmiany zatwierdzonej technologii.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 162
- **Status:** Zatwierdzona

### D-109 – decyzja 163: Dokumentacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dokumentacja
- **Opis:** Zatwierdzone decyzje w oficjalnym rejestrze GitHub; zachować historię i oznaczać zastąpione.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 163
- **Status:** Zatwierdzona

### D-110 – decyzja 164: Dostępność
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dostępność
- **Opis:** Czytelność przy powiększeniu tekstu do 200% i widoku do 400%, bez utraty funkcji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 164
- **Status:** Zatwierdzona

### D-111 – decyzja 165: Nawigacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Nawigacja
- **Opis:** Sticky header stale widoczny również podczas przewijania w dół.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 165
- **Status:** Zatwierdzona

### D-112 – decyzja 166: Nawigacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Nawigacja
- **Opis:** Logo w nagłówku prowadzi do strony głównej aktualnego języka.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 166
- **Status:** Zatwierdzona

### D-113 – decyzja 167: Usługi
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Usługi
- **Opis:** Naturalne przewijanie długich podstron; bez dodatkowego spisu treści na początku.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 167
- **Status:** Zatwierdzona

### D-114 – decyzja 168: Mobile
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Mobile
- **Opis:** Dolny CTA Umów wizytę stale widoczny przy przewijaniu; nie może zasłaniać treści ani formularza.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 168
- **Status:** Zatwierdzona

### D-115 – decyzja 169: Kontakt
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Kontakt
- **Opis:** Kolejność: telefon i adres, godziny, mapa, formularz.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 169
- **Status:** Zatwierdzona

### D-116 – decyzja 170: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Telefon: dopuszczać odstępy, +48 i poprawne numery zagraniczne; bez nadmiernie restrykcyjnej walidacji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 170
- **Status:** Zatwierdzona

### D-117 – decyzja 171: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Sprawdzać format e-mail bez przesadnych restrykcji i bez pola powtórzenia adresu.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 171
- **Status:** Zatwierdzona

### D-118 – decyzja 172: Formularz
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Formularz
- **Opis:** Rozsądny limit wiadomości, np. 2000 znaków, z jasnym komunikatem.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 172
- **Status:** Zatwierdzona

### D-119 – decyzja 173: Mapa
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Mapa
- **Opis:** Wyznacz trasę otwiera Google Maps w nowej karcie, z gabinetem jako celem.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 173
- **Status:** Zatwierdzona

### D-120 – decyzja 174: Odbiór
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Odbiór
- **Opis:** Przed publikacją zatwierdzenie widoku desktop i mobile w obu językach.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 174
- **Status:** Zatwierdzona

### D-121 – decyzja 175: Testy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Testy
- **Opis:** Rzeczywista wysyłka formularza na komputerze i telefonie, w PL i EN.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 175
- **Status:** Zatwierdzona

### D-122 – decyzja 176: Testy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Testy
- **Opis:** Sprawdzić linki wewnętrzne, zewnętrzne, przełącznik języka i przekierowania; błędy krytyczne blokują publikację.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 176
- **Status:** Zatwierdzona

### D-123 – decyzja 177: Obrazy
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Obrazy
- **Opis:** Każde nowe zdjęcie i grafika, także AI, wymagają akceptacji właściciela.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 177
- **Status:** Zatwierdzona

### D-124 – decyzja 178: Publikacja
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Publikacja
- **Opis:** Raport gotowości po odbiorze /test/; produkcja dopiero po jednoznacznej zgodzie.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 178
- **Status:** Zatwierdzona

### D-125 – decyzja 179: Technologia
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Technologia
- **Opis:** Pozostaje HTML/CSS/JS bez frameworka; Claude Code ma przygotować plan implementacji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 179
- **Status:** Zatwierdzona

### D-126 – decyzja 180: Proces
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Proces
- **Opis:** Implementacja etapami i osobnymi PR: wspólny układ i homepage PL/EN, potem reszta, integracje, testy i publikacja. Przed implementacją obowiązkowo trzy koncepcje Claude Design i akceptacja kierunku.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 180
- **Status:** Zatwierdzona

### D-127 – decyzja 181: Dostępność
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Dostępność
- **Opis:** Dopuszczony dyskretny link Przejdź do treści, widoczny przy nawigacji klawiaturą, jeśli potrzebny do WCAG; zastępuje wcześniejszy zakaz z decyzji 96.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 181
- **Status:** Zatwierdzona

### D-128 – decyzja 182: Strategia usług
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Strategia usług
- **Opis:** Wszystkie siedem usług przedstawiać z równym priorytetem.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 182
- **Status:** Zatwierdzona

### D-129 – decyzja 183: SEO lokalne
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** SEO lokalne
- **Opis:** Jedna silna strona gabinetu w Redzie; naturalne odniesienia do Rumi, Wejherowa i okolic; bez sztucznych podstron lokalnych.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 183
- **Status:** Zatwierdzona

### D-130 – decyzja 184: Wizytówka Google
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Wizytówka Google
- **Opis:** Najpierw uruchomienie strony, rozwój Google Business Profile później; zastępuje wcześniejszy wymóg z decyzji 63 utworzenia wizytówki przed startem.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 184
- **Status:** Zatwierdzona

### D-131 – decyzja 185: Blog
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Blog
- **Opis:** Regularnie publikować artykuły również z myślą o wzroście ruchu organicznego; nadal obowiązuje akceptacja PL/EN i weryfikacja medyczna.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 185
- **Status:** Zatwierdzona

### D-132 – decyzja 186: Analityka
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Analityka
- **Opis:** Na start Google Search Console, GA4 odłożone.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 186
- **Status:** Zatwierdzona

### D-133 – decyzja 187: Claude Design
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Claude Design
- **Opis:** Trzy wyraźnie różne koncepcje, każda zgodna z zatwierdzonym logo, kolorami, treściami i wymaganiami.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 187
- **Status:** Zatwierdzona

### D-134 – decyzja 188: Claude Design
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Claude Design
- **Opis:** Trzy rzeczywiste szkice strony głównej: desktop i mobile dla każdej koncepcji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 188
- **Status:** Zatwierdzona

### D-135 – decyzja 189: Claude Design
- **Data rejestracji:** 2026-11-15
- **Wariant:** B
- **Obszar:** Claude Design
- **Opis:** Na początek wyłącznie homepage; podstrony usług projektować po wyborze kierunku.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 189
- **Status:** Zatwierdzona

### D-136 – decyzja 190: Claude Design
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Claude Design
- **Opis:** Wykorzystać UI/UX Pro Max i inne dostępne sprawdzone skille jako rekomendacje, bez samodzielnego zmieniania zatwierdzonych decyzji.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 190
- **Status:** Zatwierdzona

### D-137 – decyzja 191: Claude Design
- **Data rejestracji:** 2026-11-15
- **Wariant:** A
- **Obszar:** Claude Design
- **Opis:** Porównać trzy projekty pod kątem estetyki, czytelności, wiarygodności, mobile i zgodności; właściciel może wybrać jeden lub połączyć elementy kilku.
- **Źródło:** własna decyzja właściciela, rozmowa projektowa nr 191
- **Status:** Zatwierdzona

