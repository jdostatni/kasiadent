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

## Decyzje po wyborze kierunku wizualnego

### D-138 – Prototyp D jako docelowy projekt graficzny strony głównej
- **Data:** 2026-11-22
- **Obszar:** wygląd
- **Opis:** Lokalny prototyp D (baza: prototyp C „Granat redakcyjny premium”) jest docelowym projektem graficznym strony głównej dr KASIA DENT. Ostatecznie zaakceptowane są wszystkie wymagania C1–C7 z `docs/PROTOTYPE_D_SPEC.md` (C1 zdjęcie hero, C2 nawigacja desktop, C3 stopka w układzie A i kolorach C z białym paskiem copyright, C4 kadrowanie hero W3 na telefonie, C5 usługi L4 z hoverem H2, kafelkiem konsultacji K1 i wariantem C oznaczenia klikalności, C6 sekcja „Dlaczego…” L6 z tekstem T2, C7 hamburger przechodzący w ×) oraz późniejsze poprawki mobilne: wewnętrzny odstęp 24 px z lewej i prawej w kafelkach usług dla szerokości do 639 px włącznie (jednakowo w spoczynku, przy hover i fokusie) oraz kreski hamburgera 2,5 / 2,0 / 2,5 px o równej długości, kwadratowych zakończeniach i kolorze #113269. Wdrożenie zachowuje zatwierdzony wygląd; nie oznacza zgody na publikację, merge kodu ani deployment.
- **Uzasadnienie:** Zakończenie etapu porównania koncepcji (D-134–D-137) i analiz C1–C7; wybór kierunku przed implementacją HTML/CSS/JS (D-126).
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

### D-139 – decyzje 192–198: hosting i poczta (zakres udokumentowany)
- **Data rejestracji:** 2026-11-22
- **Obszar:** technologia / proces
- **Opis:** Decyzje rozmowy nr 192–198 zostały zatwierdzone przez właściciela wcześniej (najpóźniej 2026-11-15), ale nie trafiły do rejestru. W repozytorium udokumentowany jest wyłącznie ich łączny zakres (`docs/SEO.md`, aktualizacja spójności z 15.11.2026): hosting Hostido lub porównywalny dostawca do wyboru, **bez wyboru konkretnego hostingu**; publiczny adres e-mail `drkasiadent@gmail.com`. Szczegółowe brzmienie poszczególnych decyzji 192–198 nie jest dostępne w repozytorium; jeśli właściciel je przekaże, zostaną dopisane jako kolejne wpisy bez zmiany niniejszego.
- **Uzasadnienie:** Uzupełnienie rejestru o decyzje przywołane w `docs/SEO.md`, bez dopowiadania treści, której nie ma w dokumentacji.
- **Źródło:** własna decyzja właściciela; zapis w `docs/SEO.md`
- **Status:** Zatwierdzona

### D-140 – Hosting, lokalny test adresów URL i zdjęcie hero
- **Data:** 2026-11-22
- **Obszar:** proces / technologia
- **Opis:** (1) Hosting nie jest na razie kupowany; środowisko testowe `/test/` z hasłem zostanie przygotowane po wyborze hostingu i nie blokuje lokalnych prac nad stroną. (2) Strategia adresów URL (konwencja z `docs/SEO.md`: bez `.html` i bez końcowego ukośnika) zostanie przeanalizowana i przetestowana lokalnie przed implementacją i przed wyborem ostatecznej konfiguracji, bez instalowania Docker Desktop; instalacja nowego oprogramowania wymaga wcześniejszej propozycji i akceptacji właściciela (zaakceptowano przenośne narzędzia lokalne poza repozytorium: Apache, Node.js z Lighthouse i axe-core, walidator HTML, fonttools do WOFF2 — po sprawdzeniu wersji i zależności). (3) Zdjęcie hero nie trafia do repozytorium bez osobnej zgody właściciela, do czasu ustalenia jego pochodzenia i warunków wykorzystania; bez nieuzgodnionych zmian w `.gitignore`.
- **Uzasadnienie:** Ustalenia właściciela do skorygowanego planu wdrożenia prototypu D (D-138).
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

### D-141 – Treści EN strony głównej, etykiety interfejsu PL/EN i metadane strony głównej
- **Data:** 2026-11-22
- **Obszar:** treść
- **Opis:** (1) Zatwierdzone treści EN strony głównej odpowiadające zmianom z prototypu D: kafelek konsultacji („Not sure where to start?” / „Start with a consultation – we will assess your dental health and recommend the next steps.” / przycisk „Book a consultation” do `/en/contact`) oraz cztery argumenty sekcji „Why do patients choose dr KASIA DENT?” w wersji T2 (bez myślników, opis od wielkiej litery), z czwartym argumentem „View our price list and book a consultation.”, w którym „price list” prowadzi do `/en/pricing`; zapis w `content/strona-glowna_en.md`. (2) Zatwierdzone etykiety interfejsu PL/EN zapisane w `docs/UI_LABELS_PL_EN.md`; na kafelkach usług EN „Learn more”, a przycisk sekcji pierwszej wizyty pozostaje „Find out more”. (3) Zatwierdzone meta title i meta description strony głównej PL i EN, zapisane w nagłówkach YAML (`slug`, `meta_title`, `meta_description`) plików `content/strona-glowna_pl.md` i `content/strona-glowna_en.md`; Open Graph korzysta z tych samych tekstów, obraz OG wymaga osobnej akceptacji.
- **Uzasadnienie:** Uzupełnienie wersji EN i metadanych przed wdrożeniem strony głównej PL/EN (D-138; zasada jednoczesnego startu PL/EN).
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

### D-142 – Strategia adresów URL: wariant A
- **Data:** 2026-11-22
- **Obszar:** architektura
- **Opis:** Strony zapisywane jako pliki `nazwa.html` (np. `kontakt.html`, `uslugi/protetyka.html`, `en/contact.html`; strony główne `index.html` i `en/index.html`) i serwowane przez reguły `.htaccess` pod adresami kanonicznymi bez rozszerzenia `.html` i bez końcowego ukośnika, z wyjątkiem `/` i `/en/`. Warianty adresów (z `.html`, z końcowym ukośnikiem, `index.html`, `/en`) przekierowywane 301 jednym skokiem na adres kanoniczny; nieznane adresy zwracają 404. Linki wewnętrzne względne (linki do adresów bez ukośnika budowane przez katalog nadrzędny, np. `../uslugi`), tak aby te same pliki działały w katalogu głównym i w wersji testowej `/test/`; `canonical`, `hreflang` i `og:url` pozostają adresami bezwzględnymi `https://www.kasiadent.pl/…`. Strategia przetestowana lokalnie na Apache 2.4.71 (86 kontroli bez błędów); po wyborze hostingu wymagane są ponowne testy.
- **Uzasadnienie:** Wynik lokalnego testu wariantów (D-140 pkt 2) i konwencja adresów z `docs/SEO.md` (pkt 3.2).
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

## Decyzje etapu P1 – projekt podstron usług

### D-143 – Podstrona usługi „Endodoncja mikroskopowa”: hero, blok wprowadzenia i układ desktopu (szkic A2.4)
- **Data:** 2026-11-24
- **Obszar:** wygląd
- **Opis:** Po ocenie lokalnych szkiców etapu P1 (A1, A2, A2.1–A2.3): (1) Szkic A2 z hero o wysokości 320 px jest bazą dalszego projektowania podstron usług. (2) Hero podstrony „Endodoncja mikroskopowa”: fotografia mikroskopu stomatologicznego z wariantu A2.3 (`kasiadent-prototypy/hero/hero-mikroskop.png`, poza repozytorium) i wysokość 320 px na desktopie; bez zmian pozostają kadrowanie, granatowy gradient, typografia, położenie tytułu i dekoracyjna kreska z A2.3 oraz okruszki nawigacyjne pod hero. (3) Każda z siedmiu podstron usług otrzyma własną, indywidualnie dobraną fotografię hero; fotografie mają docelowo tworzyć spójną wizualnie serię przy wspólnym szablonie hero. Fotografii i szkiców pozostałych sześciu usług jeszcze się nie przygotowuje. (4) Blok wprowadzenia: kolor tła `#DCE7F7` (soft blue z A2.1) i rozmieszczenie tekstu z pierwotnego A2 – prostokątny blok o pełnej szerokości, oba akapity jeden pod drugim, lewa krawędź tekstu wyrównana z lewą krawędzią kolumny tekstowej kolejnych sekcji (wspólna pionowa oś), tekst wyrównany do lewej bez rozciągania odstępów między słowami, czytelna szerokość ok. 65–80 znaków w wierszu; pusta przestrzeń po lewej stronie bloku jest zamierzona; zatwierdzona treść, typografia i wyróżnienia bez zmian; bez zdjęć, ikon, nagłówków, pionowych linii i innych dekoracji. Rozmieszczenie tekstu z A2.1–A2.3 nie zostało wybrane. (5) Pozostałe elementy desktopu zaakceptowane w obecnym układzie: nagłówki sekcji po lewej i treść po prawej, dotychczasowa typografia, numerowane etapy leczenia 01–05, poziome separatory, odstępy między sekcjami, nawigacja i stopka; dodatkowe zmiany estetyczne tych elementów wymagają zgody właściciela. (6) Scalony wariant desktopu jest przygotowywany jako szkic A2.4; jego wersja responsywna (mobilna) pozostaje do oceny właściciela, a etap P1 nie jest zakończony.
- **Uzasadnienie:** Wybór właściciela po ocenie szkiców A2.1–A2.3 (etap P1 projektowania podstron); scalenie najlepszych elementów trzech wariantów.
- **Źródło:** własna decyzja właściciela
- **Status:** Zatwierdzona

### D-144 – Akceptacja szkicu A2.4 i poprawki techniczne etapu P1 (WCAG 2.4.11, twarde spacje, WebKit, fonty)
- **Data:** 2026-11-25
- **Obszar:** wygląd / funkcjonalność / proces
- **Opis:** (1) Zatwierdzony wygląd desktopu i wersji mobilnej szkicu A2.4 podstrony „Endodoncja mikroskopowa” (uzupełnia D-143); bez zmian pozostają fotografia mikroskopu, gradient, kolor tła wprowadzenia `#DCE7F7`, typografia, układ treści i odstępy; bez dodatkowych zmian wizualnych. (2) Pozycja „Usługi” w menu jest wyróżniona na wszystkich siedmiu podstronach usług (otwarta decyzja nr 6 raportu P1). (3) Zgoda na naprawę problemu WCAG 2.4.11 – zasłaniania aktywnego elementu przez dolny pasek „Umów wizytę” podczas nawigacji klawiaturą – w A2.4 i w zatwierdzonym prototypie D (uzupełnia D-138), z zachowaniem wyglądu, położenia i działania paska, możliwie prostym i wspólnym rozwiązaniem, z testami Tab i Shift+Tab oraz testami regresji D i A2.4. Zgoda na modyfikację D obejmuje wyłącznie tę poprawkę oraz poprawkę typograficzną z pkt 4. (4) Wspólna zasada typograficzna całej witryny: w polskich tekstach pojedyncze litery „a”, „i”, „o”, „u”, „w”, „z” łączy się twardą spacją z następnym wyrazem, aby nie zostawały na końcu wiersza. Zasadę stosuje się na etapie przygotowania HTML (A2.4, prototyp D i kolejne podstrony), bez zmian zatwierdzonych źródłowych plików Markdown, słów, interpunkcji i treści; nie dotyczy tekstów angielskich. (5) Zgoda na instalację Playwright WebKit i niezbędnych zależności testowych (bez dodawania ich do kodu produkcyjnego witryny) oraz na testy WebKit prototypu D i podstrony A2.4; testy Playwright WebKit nie są równoważne testom na rzeczywistym urządzeniu Apple. (6) Optymalizacja fontów zostaje odłożona na późniejszy etap jako osobne zadanie dla całej witryny; na obecnym etapie bez zmian czcionek, ich wyglądu i sposobu ładowania. (7) Etap P1 pozostaje niezakończony do końcowej akceptacji właściciela; etap P2 i pozostałe sześć podstron usług nie są rozpoczynane.
- **Uzasadnienie:** Decyzje właściciela po ocenie szkicu A2.4 i otwartych kwestii etapu P1.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-145 – Zamykanie etapu P1: okruszki, rezygnacja z bloku CTA, dostępność menu, numer telefonu
- **Data:** 2026-11-25
- **Obszar:** funkcjonalność / treść / proces
- **Opis:** (1) Zaakceptowane poprawki techniczne szkicu A2.4 (D-144) i wyniki dotychczasowych testów. (2) Okruszki nawigacyjne: etykieta ARIA `aria-label="Ścieżka nawigacyjna"` (PL) i `aria-label="Breadcrumb"` (EN), z zachowaniem dotychczasowego wyglądu i działania; zasada obowiązuje również na kolejnych podstronach. (3) Rezygnacja z dodatkowego bloku CTA na końcu podstron usług – nie projektuje się go dla żadnej z siedmiu usług; dostęp do kontaktu i rejestracji zapewniają nawigacja, przycisk „Umów wizytę”, dolny pasek mobilny i stopka. (4) Zgoda na poprawkę dostępności modalnego menu mobilnego: fokus pozostaje wewnątrz otwartego menu, poprawna obsługa Tab i Shift+Tab, zamykanie klawiszem Escape i przywracanie fokusu do elementu otwierającego menu, bez zmian wyglądu i dotychczasowej funkcjonalności. (5) Zgoda na techniczne powiększenie obszaru aktywnego przycisku podmenu zgodnie z WCAG 2.2 AA (kryterium 2.5.8), w miarę możliwości do ok. 44 × 44 px, bez zmiany widocznej ikony, wyglądu, położenia i odstępów nawigacji oraz bez kolizji z sąsiednimi linkami; zmiana wymagająca widocznej zmiany układu wymaga osobnej akceptacji. Zgoda na modyfikację prototypu D obejmuje wyłącznie poprawki z pkt 4 i 5, stosowane spójnie we wszystkich istniejących prototypach korzystających z tej samej nawigacji (PL i EN). (6) Numer telefonu (zgodnie z D-097): PL „505 518 718”, EN „+48 505 518 718”; link telefoniczny w obu wersjach `tel:+48505518718`; zasada dla wszystkich istniejących prototypów i kolejnych podstron; pozostałe dane kontaktowe bez zmian. (7) Optymalizacja fontów pozostaje odłożona na późniejszy etap jako wspólne zadanie dla całej witryny (D-144), bez zmian fontów i sposobu ich ładowania; jako zadanie na później odnotowano też różnicę wyświetlania tytułu A2.4 w WebKit i potrzebę sprawdzenia na rzeczywistym urządzeniu Apple. (8) Decyzje dotyczące nagłówka EN przy 1100–1159 px, hero strony głównej D na tablecie i podmenu bez JavaScriptu pozostają otwarte do czasu oceny przygotowanych materiałów; etap P1 nie jest zamknięty.
- **Uzasadnienie:** Decyzje właściciela dotyczące otwartych kwestii etapu P1.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-146 – Zamknięcie otwartych kwestii etapu P1: nagłówek EN, hero strony głównej na tablecie, podmenu bez JavaScriptu, telefon w Markdown EN
- **Data:** 2026-11-26
- **Obszar:** wygląd / treść / proces
- **Opis:** (1) Nagłówek EN przy 1100–1159 px: zatwierdzone mniejsze odstępy między elementami nagłówka wyłącznie w wersji EN i w tym zakresie szerokości, bez zmiany wielkości logo i czcionek, bez skracania nazw pozycji menu i tekstu przycisku, z zachowaniem odpowiednich obszarów aktywnych, bez przewijania poziomego i ucinania elementów (także z klasycznym paskiem przewijania Windows); wersja PL i pozostałe szerokości bez zmian; rozwiązanie obowiązuje na wszystkich stronach EN ze wspólnym nagłówkiem. (2) Hero strony głównej D: 320–599 px – dotychczasowy układ mobilny bez zmian; 600–1023 px – zdjęcie u góry, płynne przejście w granatowe tło, tekst poniżej (kadr zgodny z zaakceptowaną propozycją, czytelność i ekspozycja twarzy, dotychczasowa treść, typografia, kolorystyka i przycisk CTA); 1024–1179 px – tekst po lewej w węższej kolumnie, fotografia po prawej, z płynnym skalowaniem nagłówka (np. `clamp()`), przy priorytetach: kontrast zgodny z WCAG 2.2 AA, brak nachodzenia tekstu na twarz, czytelność i proporcje typografii, możliwie płynne przejście do układu desktopowego – bez zwiększania nagłówka kosztem kontrastu lub czytelności; od 1180 px – dotychczasowy układ desktopowy bez zmian. Poprawka spójna w wersjach PL i EN strony głównej i ich kopiach roboczych, z uwzględnieniem różnic długości tekstów; bez zmian zatwierdzonych treści, fotografii, fontów, kolorystyki, pozostałych sekcji D i hero A2.4. Zgoda na modyfikację prototypu D obejmuje wyłącznie ten zakres (uzupełnia D-138). (3) Podmenu „Usługi” bez JavaScriptu: obecne rozwiązanie pozostaje bez zmian; wcześniejsze ostrzeżenie testu uznane za fałszywy alarm. (4) Zatwierdzona aktualizacja źródłowych plików Markdown EN do formatu numeru telefonu z D-145 (PL „505 518 718”, EN „+48 505 518 718”, link `tel:+48505518718` w obu wersjach): `kontakt_en.md` (dwa wystąpienia), `pierwsza-wizyta_en.md`, `cennik_en.md` oraz trzy artykuły blogowe EN z uzupełnieniem linków telefonicznych; bez zmian innych treści, tłumaczeń, danych kontaktowych i metadanych; zmiana w osobnym PR, niezależnym od zmian `docs/DECISIONS.md`; commit, push i utworzenie PR dopiero po końcowej akceptacji przygotowanego zakresu. (5) Optymalizacja fontów pozostaje odłożona jako wspólne zadanie dla całej witryny, bez zmian fontów, ich plików i sposobu ładowania; jako zadania na później, nieblokujące zakończenia P1: weryfikacja tytułu A2.4 na rzeczywistym urządzeniu Apple, testy na rzeczywistym iPhonie i w Safari, optymalizacja wydajności ładowania fontów. (6) Zamknięcie decyzji 15 i całego etapu P1 wymaga końcowej akceptacji właściciela; etap P2 i pozostałe sześć podstron usług nie są rozpoczynane.
- **Uzasadnienie:** Decyzje właściciela po konsultacji z ChatGPT i analizie plansz dotyczących decyzji 8 i 9.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-147 – Zakończenie etapu P1, wzorzec podstron usług i zakres PR z telefonem (PL i EN)
- **Data:** 2026-11-26
- **Obszar:** proces / wygląd / treść
- **Opis:** (1) Ostateczna akceptacja etapu P1: końcowy wygląd nagłówka EN, końcowy wygląd hero strony głównej D we wszystkich przedstawionych szerokościach w wersjach PL i EN oraz płynne skalowanie nagłówka hero. Szablon podstrony usług A2.4 jest obowiązującym wzorcem dla etapu P2; zasady zapisano w `docs/WZORZEC_PODSTRON_USLUG.md`. Decyzja 15 raportu P1 zamknięta, etap P1 zakończony; bez kolejnych zmian projektowych w ramach P1. (2) PR A: dokumentacja i decyzje etapu P1 (wpisy D-143–D-147, wzorzec podstron usług, statusy decyzji, zadania odłożone) bez przenoszenia do repozytorium prototypów, plansz, raportu i narzędzi testowych; scalenie wyłącznie za osobną zgodą właściciela. (3) PR B obejmuje pliki Markdown PL i EN: PL – widoczny numer „505 518 718”, w Markdown `[505 518 718](tel:+48505518718)`; EN – widoczny numer „+48 505 518 718”, w Markdown `[+48 505 518 718](tel:+48505518718)`; link `tel:+48505518718` w obu wersjach. Zatwierdzone: wcześniej przygotowana aktualizacja plików EN, uzupełnienie pięciu brakujących linków w plikach PL oraz numer w `metaDescription` pliku `kontakt_en.md` w formacie „+48 505 518 718” jako zwykły tekst, bez linku; bez zmian innych treści i metadanych. PR B jest realizowany po zatwierdzeniu i scaleniu PR A. Decyzja 11 raportu P1 zatwierdzona, oczekuje na realizację w Git. (4) Zadania odłożone, nieblokujące zakończenia P1 ani rozpoczęcia P2: optymalizacja fontów i sposobu ich ładowania; weryfikacja tytułu A2.4 i hero strony głównej D na rzeczywistych urządzeniach Apple; testy na iPhonie i w Safari przed publikacją; kontrast desktopowego hero PL w WebKit jako otwarta kwestia wymagająca weryfikacji (nie potwierdzony problem wyłącznie środowiska testowego); drobne naruszenie wewnętrznego marginesu nagłówka PL w Firefoksie przy 1100 px. (5) Plan etapu P2 (sześć pozostałych podstron usług) zostanie przedstawiony do akceptacji przed rozpoczęciem implementacji.
- **Uzasadnienie:** Ocena końcowych plansz i zakończenie etapu P1.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

## Decyzje etapu P2

### D-148 – Fotografie hero podstron usług: przyporządkowanie, kadrowanie i optymalizacja (etap P2)
- **Data:** 2026-11-27
- **Obszar:** wygląd / materiały graficzne
- **Opis:** (1) Zatwierdzone przyporządkowanie fotografii hero (fotografie przygotowane w Higgsfield, lokalny katalog prototypów `kasiadent-prototypy/hero`): Stomatologia zachowawcza – `zachowawcza-hero.png`; Endodoncja mikroskopowa – `hero-mikroskop.png` (zatwierdzona wcześniej, D-143); Protetyka – `protetyka-konsultacja.png`; Stomatologia estetyczna – `estetyczna-hero.png`; Profilaktyka – `higienizacja-hero.png`; Stomatologia dziecięca – `bear-dziecieca-hero.png`; Diagnostyka RTG – `rtg-hero.png`, zatwierdzona warunkowo do weryfikacji anatomii przez lekarza. (2) Warunkowa akceptacja fotografii RTG nie blokuje wcześniejszych etapów P2; ostateczna akceptacja fotografii przez lekarza jest wymagana przed zamknięciem podstrony „Diagnostyka RTG”. (3) Indywidualne kadrowanie fotografii w CSS i indywidualny dobór gradientu dla każdej usługi przy zachowaniu systemu A2.4 (`docs/WZORZEC_PODSTRON_USLUG.md`). Akceptacja różnic jasności i kolorystyki między fotografiami; granatowy akcent nie jest obowiązkowy w każdej fotografii – spójność wizualną zapewnia wspólny system A2.4. (4) Optymalizacja WebP analogicznie do A2.4, w sześciu szerokościach (640, 960, 1280, 1600, 1920 i 2400 px). (5) Kontrola kontrastu tytułu na fotografii (co najmniej 4,5:1) i widoczności głównego obiektu fotografii przy różnych szerokościach ekranu; testy automatyczne uzupełniane oceną wizualną plansz, szczególnie w zakresie kadrowania i widoczności głównego obiektu. (6) Oryginały PNG pozostają bez zmian; bez generowania nowych fotografii. (7) `hero-zab.png` zachowany jako niewykorzystany materiał, potencjalnie przydatny na blogu.
- **Uzasadnienie:** Inwentaryzacja fotografii hero, zbiorcza plansza z kompletem siedmiu usług i kontrola fotografii stomatologii estetycznej w szablonie A2.4.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-149 – Architektura techniczna etapu P2: struktura katalogów, adresy URL, wspólny arkusz CSS, generator HTML i zabezpieczenia
- **Data:** 2026-11-27
- **Obszar:** architektura / technologia
- **Opis:** (1) **Struktura i adresy.** Podstrony usług w lokalnych prototypach zapisywane jako `podstrony/uslugi/<slug>.html` (PL) i `podstrony/en/services/<slug>.html` (EN). Adresy docelowe zgodne z zatwierdzoną mapą adresów PL i EN (`content/docs/URL_MAP_PL_EN.md`, `docs/SEO.md` pkt 4.2) i strategią D-142: `/uslugi/stomatologia-zachowawcza` – `/en/services/general-dentistry`; `/uslugi/leczenie-kanalowe-pod-mikroskopem` – `/en/services/root-canal-treatment`; `/uslugi/protetyka` – `/en/services/prosthodontics`; `/uslugi/stomatologia-estetyczna` – `/en/services/cosmetic-dentistry`; `/uslugi/profilaktyka` – `/en/services/preventive-dentistry`; `/uslugi/stomatologia-dziecieca` – `/en/services/childrens-dentistry`; `/uslugi/diagnostyka-rtg` – `/en/services/dental-x-rays`; strona zbiorcza `/uslugi` – `/en/services`. (2) **Archiwum.** Istniejące strony S1 Endodoncji PL i EN zostają zarchiwizowane (kopie zachowane), a następnie zastąpione wersjami opartymi na A2.4 – po przeprowadzeniu wymaganych testów i akceptacji właściciela. Wszystkie historyczne szkice A1–A2.4 pozostają zachowane; szkic A2.4 pozostaje niezmiennym wzorcem referencyjnym. (3) **CSS.** Jeden wspólny arkusz `usluga.css` dla wszystkich siedmiu usług w wersjach PL i EN; nazwy klas z przedrostkiem `usluga-*` zamiast roboczego `sz-*`; przeniesienie zatwierdzonych wartości i reguł A2.4 bez zmian wizualnych; indywidualne ustawienia fotografii przez klasy modyfikujące i zmienne CSS. Kolejność warstw: `d/style.css` (prototyp D), `podstrony.css` (elementy wspólne podstron), `usluga.css`. Nawigacja, menu, stopka i dolny pasek mobilny pochodzą z aktualnego, zatwierdzonego prototypu D; bez dodatkowych zmian wizualnych i funkcjonalnych w D. (4) **Generator HTML.** Rozwinięcie istniejącego generatora w języku Python zamiast tworzenia nowego narzędzia: jeden wspólny plik konfiguracji usług; generowanie statycznych plików HTML z zatwierdzonych źródeł Markdown; bez obowiązkowego kroku budowania (build-stepu); bez nowych bibliotek i zależności bez zgody właściciela; generowanie pojedynczej usługi, wybranej wersji językowej lub wszystkich usług; powtarzalność (identyczne dane wejściowe dają identyczne pliki wynikowe); generowanie w pierwszej kolejności do osobnego katalogu testowego; brak automatycznego nadpisywania zatwierdzonych prototypów oraz statusów akceptacji i decyzji w centralnym raporcie; automatyczna kontrola zgodności wygenerowanej treści z zatwierdzonym Markdown; zachowanie zatwierdzonych metadanych, nagłówków, wyróżnień, list i linków; twarde spacje w polskich tekstach (D-144); format telefonów (D-145–D-147); okruszki, dostępność, aktywna pozycja „Usługi” w menu i pozostałe zasady zatwierdzonego wzorca; bez dodatkowego bloku CTA na końcu podstron usług (D-145). (5) **Metoda pracy.** Ręczne poprawianie wygenerowanych plików HTML nie jest docelową metodą pracy – poprawki wprowadza się w źródłach, szablonie, konfiguracji lub generatorze. Dotychczasowa wersja generatora nie może być uruchamiana w sposób, który mógłby nadpisać istniejące prototypy lub statusy raportu. (6) **Warunek zgodności z A2.4.** Przed zastąpieniem jakiegokolwiek istniejącego prototypu wersją wygenerowaną przez generator wymagane jest potwierdzenie zgodności Endodoncji PL z zatwierdzonym szkicem A2.4: porównanie pikselowe w identycznych warunkach testowych, przy szerokościach reprezentatywnych dla telefonu, tabletu i desktopu, przy identycznych warunkach ładowania fontów, zdjęć i pozostałych zasobów, oraz kontrola treści, metadanych, linków, responsywności i funkcjonalności. Oczekiwany wynik wizualny: 0 różniących się pikseli w powtarzalnych warunkach testowych. Przy różnicach – ustalenie przyczyny i przedstawienie jej do oceny właściciela; wzorca A2.4 nie zmienia się w celu dopasowania do generatora, a odstępstw nie akceptuje się samodzielnie. (7) **Repozytorium.** Kod generatora, arkusze CSS, prototypy, fotografie, plansze i narzędzia testowe pozostają poza repozytorium; ich przeniesienie wymaga osobnej zgody właściciela.
- **Uzasadnienie:** Plan techniczny etapu P2 z 27.11.2026 (struktura, adresy, CSS, generator, fotografie, kolejność prac) zaakceptowany przez właściciela z uzupełnieniami.
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-150 – Zakres i harmonogram etapu P2 (P2.0–P2.6), punkty akceptacji i obowiązkowa strona zbiorcza „Usługi”
- **Data:** 2026-11-27
- **Obszar:** proces / zakres
- **Opis:** (1) **Zakres P2:** siedem podstron usług w wersjach PL i EN na wzorcu A2.4 oraz zbiorcza strona „Usługi” w wersjach PL i EN. (2) **Harmonogram:** **P2.0 – przygotowanie techniczne:** rozwinięcie generatora, wspólny arkusz CSS, konfiguracja usług, zabezpieczenia generatora, wygenerowanie testowej Endodoncji PL i test zgodności z A2.4 (D-149 pkt 6). **P2.1 – Endodoncja EN:** wersja EN na wzorcu A2.4 z zachowaniem zatwierdzonego tłumaczenia, testy obu wersji językowych, akceptacja fundamentu technicznego i wersji EN przez właściciela. **P2.2 – pierwsza partia:** Stomatologia zachowawcza i Protetyka (PL i EN); zaprojektowanie brakujących elementów systemu treści – podsekcji H3, list punktowanych i list z pogrubionym początkiem – i przedstawienie ich do akceptacji przed wykorzystaniem w kolejnych usługach; akceptacja partii. **P2.3 – druga partia:** Stomatologia estetyczna i Profilaktyka (PL i EN) z wykorzystaniem zatwierdzonego systemu projektowego; akceptacja partii. **P2.4 – trzecia partia:** Stomatologia dziecięca i Diagnostyka RTG (PL i EN) z uwzględnieniem warunkowej akceptacji fotografii RTG (D-148); akceptacja partii. **P2.5 – zbiorcza strona „Usługi”:** obowiązkowa część P2, przygotowywana po zatwierdzeniu wszystkich siedmiu podstron usług, w kolejności: ustalenie struktury i zakresu treści; przygotowanie i akceptacja treści PL; przygotowanie i akceptacja treści EN; przygotowanie i akceptacja meta title i meta description PL i EN; przygotowanie projektu wizualnego; akceptacja projektu desktopowego i responsywnego; testy obu wersji językowych. Nowych zatwierdzonych treści ani metadanych nie tworzy się samodzielnie; obowiązują zasady `CLAUDE.md` i `docs/SEO.md`. **P2.6 – testy końcowe i zamknięcie P2:** kontrola wszystkich siedmiu usług PL i EN oraz zbiorczej strony „Usługi” PL i EN: zgodność treści z zatwierdzonymi źródłami, spójność wizualna, responsywność, dostępność WCAG 2.2 AA, testy w Chromium, Firefox i WebKit, axe, Lighthouse i walidacja HTML, kontrola linków, metadanych, nawigacji i przełączania języków; raport końcowy i akceptacja właściciela. (3) **Zasady akceptacji:** każdy etap i każda partia wymagają osobnej akceptacji właściciela przed przejściem do kolejnej. Centralny raport zawiera: aktualny status każdej podstrony PL i EN, linki do działających prototypów, zbiorcze plansze desktopowe i responsywne, mapę sekcji wynikającą z zatwierdzonych treści, wyniki testów i listę kwestii wymagających decyzji właściciela. (4) **Testy:** przy kolejnych podstronach testy ukierunkowane, bez powtarzania pełnego zestawu testów P1; rozszerzone testy regresji przy zmianach wspólnych elementów i na zakończenie P2. (5) Zadania odłożone z etapu P1 pozostają odnotowane i nie są rozwiązywane przy okazji bez osobnej zgody właściciela. (6) Realizacja P2.0 rozpoczyna się po scaleniu PR z decyzjami D-148–D-150 i osobnej zgodzie właściciela.
- **Uzasadnienie:** Plan techniczny etapu P2 z 27.11.2026 z uzupełnieniami właściciela; strona zbiorcza „Usługi” włączona do P2 jako obowiązkowa (w planie technicznym proponowana jako opcjonalna).
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

### D-151 – Zmiana kolejności realizacji P2: najpierw wszystkie podstrony PL, następnie EN; akceptacja P2.0
- **Data:** 2026-11-27
- **Obszar:** proces / zakres
- **Opis:** (1) **Akceptacja i zamknięcie P2.0.** Etap P2.0 (przygotowanie techniczne i Endodoncja PL) zatwierdzony i zakończony. Zatwierdzone: wyniki P2.0, rozwinięty generator w języku Python, wspólny arkusz `usluga.css`, konfiguracja siedmiu usług i zabezpieczenia przed nadpisaniem (D-149 pkt 3–5). Zaakceptowane wyniki pełnego porównania pikselowego testowej Endodoncji PL ze szkicem A2.4 oraz osobnego testu diagnostycznego, w którym po ukryciu paska prototypu w obu stronach uzyskano 0 różniących się pikseli we wszystkich 24 kombinacjach szerokości (320, 390, 768, 1023, 1024, 1150, 1440 i 1920 px) i przeglądarek (Chromium, Firefox i WebKit). (2) **Zaakceptowane odstępstwo od pełnej zgodności pikselowej (D-149 pkt 6).** Jedyna różnica na pełnej stronie wynika z innego tekstu roboczego paska prototypu – oznaczenia roboczego, które nie jest elementem projektu strony; odstępstwo zaakceptowane przez właściciela. Paska prototypu nie zmienia się w celu sztucznego uzyskania wyniku 0 różnic. Wyniki testów, plansze porównawcze i obrazy różnic pozostają zachowane. (3) **Zmiana kolejności realizacji.** Najpierw przygotowuje się, testuje i zatwierdza wszystkie polskie podstrony usług i zbiorczą stronę „Usługi” PL, a dopiero później ich angielskie odpowiedniki. Zmiana dotyczy kolejności realizacji, a nie zakresu projektu. (4) **Zakres dwujęzyczny bez zmian.** Nadal obowiązuje przygotowanie siedmiu podstron usług oraz obowiązkowej zbiorczej strony „Usługi” w wersjach PL i EN (D-150 pkt 1). D-148 i D-149 pozostają w mocy. Generator nadal obsługuje wersje PL i EN; architektury nie upraszcza się do rozwiązania jednojęzycznego. Projekt podstron PL uwzględnia przyszłą obsługę dłuższych angielskich nagłówków, opisów i etykiet; układ nie może zależeć od konkretnej długości polskiego tekstu. (5) **Harmonogram P2:** **P2.0 – przygotowanie techniczne i Endodoncja PL:** zatwierdzony i zakończony. **P2.1 – Stomatologia zachowawcza i Protetyka PL:** przygotowanie dwóch podstron wyłącznie w wersji PL; indywidualne kadrowanie fotografii hero i dobór gradientów; zaprojektowanie brakujących elementów systemu treści – podsekcji H3, list punktowanych i list z pogrubionym początkiem – i przedstawienie nowych elementów do akceptacji właściciela; testy i akceptacja obu podstron. **P2.2 – Stomatologia estetyczna i Profilaktyka PL:** przygotowanie dwóch podstron PL z wykorzystaniem zatwierdzonego systemu wizualnego i elementów treści; indywidualne kadrowanie fotografii; testy i akceptacja obu podstron. **P2.3 – Stomatologia dziecięca i Diagnostyka RTG PL:** przygotowanie dwóch podstron PL z wykorzystaniem zatwierdzonego systemu wizualnego; uwzględnienie warunkowej akceptacji fotografii RTG zgodnie z D-148 i ostateczna weryfikacja fotografii RTG przez lekarza przed zamknięciem tej podstrony; testy i akceptacja obu podstron. **P2.4 – zbiorcza strona „Usługi” PL:** obowiązkowa część P2, w kolejności: ustalenie struktury i zakresu treści; przygotowanie i akceptacja treści PL; przygotowanie i akceptacja meta title i meta description PL; przygotowanie projektu wizualnego; akceptacja projektu desktopowego i responsywnego; testy strony. Zatwierdzonych treści ani metadanych nie tworzy się samodzielnie. **P2.5 – akceptacja i testy kompletu polskich podstron:** kontrola wszystkich siedmiu usług PL i zbiorczej strony „Usługi” PL; kontrola spójności wizualnej; kontrola wspólnego arkusza CSS i generatora; kontrola treści, metadanych, linków i nawigacji; testy responsywności i dostępności; rozszerzone testy regresji; zatwierdzenie kompletnego systemu wizualnego PL przez właściciela. Przed zakończeniem P2.5 nie rozpoczyna się przygotowania podstron EN. **P2.6 – Endodoncja EN jako wzorzec angielski:** przygotowanie angielskiej Endodoncji na podstawie zatwierdzonego systemu PL z zachowaniem zatwierdzonych treści i metadanych EN; dostosowanie podziału tytułu H1 na frazy; kontrola angielskich etykiet dostępności i okruszków; kontrola angielskiej nawigacji, stopki i dolnego paska mobilnego; kontrola twardych spacji i typografii EN; format telefonu „+48 505 518 718”; testy przełączania języków; testy regresji PL; akceptacja wzorca EN przez właściciela. **P2.7 – pozostałe podstrony EN:** Stomatologia zachowawcza, Protetyka, Stomatologia estetyczna, Profilaktyka, Stomatologia dziecięca, Diagnostyka RTG i zbiorcza strona „Services”, z wykorzystaniem zatwierdzonego systemu wizualnego PL i wzorca EN z P2.6; z zachowaniem wcześniej zatwierdzonych tłumaczeń i metadanych sześciu usług; zbiorcza strona „Services” wymaga osobnej akceptacji tłumaczenia, metadanych i wyglądu; przed realizacją P2.7 właściciel otrzymuje do akceptacji propozycję podziału prac na partie. **P2.8 – testy końcowe i zamknięcie P2:** testy wszystkich 16 podstron (siedem usług PL, siedem usług EN, zbiorcza strona „Usługi” PL i zbiorcza strona „Services” EN) w zakresie zgodnym z D-150, w tym: zgodność treści z zatwierdzonymi źródłami, spójność wizualna, responsywność, dostępność WCAG 2.2 AA, Chromium, Firefox i WebKit, axe, Lighthouse i walidacja HTML, metadane i linki, nawigacja i przełączanie języków; raport końcowy i akceptacja właściciela. (6) **Zasady akceptacji i testowania bez zmian:** osobna akceptacja każdego etapu; osobna akceptacja nowych elementów wizualnych; brak samodzielnych zmian zatwierdzonych treści; testy ukierunkowane przy kolejnych podstronach; rozszerzone testy regresji przy zmianach wspólnych elementów; zachowanie zatwierdzonych prototypów i historycznych plansz; odłożone problemy etapu P1 nie są rozwiązywane bez osobnej zgody właściciela. W fazie PL brak nowych odpowiedników EN jest stanem przejściowym wynikającym z harmonogramu, a nie błędem wymagającym przedwczesnego generowania wersji angielskich; rzeczywistych problemów z linkami się nie ukrywa, a zależności oczekujące na realizację EN oznacza się w raportach. (7) **Katalog testowy, archiwizacja S1 i przenoszenie podstron.** Dotychczas planowany termin przeniesienia Endodoncji PL i EN (po akceptacji P2.1 według harmonogramu z D-150) przestaje być aktualny. Do czasu nowej decyzji: prace są kontynuowane w katalogu testowym `podstrony-test/`; istniejące strony S1 i wszystkie szkice A1–A2.4 pozostają zachowane; szkic A2.4 pozostaje niezmiennym wzorcem referencyjnym; zatwierdzone prototypy nie są nadpisywane; testowa Endodoncja PL nie jest przenoszona. Moment archiwizacji S1 (D-149 pkt 2) i przenoszenia zatwierdzonych podstron do docelowego katalogu prototypów wymaga ponownego ustalenia i osobnej decyzji właściciela, z uwzględnieniem możliwości przeniesienia kompletu PL po P2.5 i kompletu EN po P2.7. Przyszły mechanizm przenoszenia ma tryb próbny (dry-run), kopie archiwalne, kontrolę sum kontrolnych i możliwość przywrócenia wcześniejszych wersji. (8) **Relacja z D-150:** D-151 zastępuje harmonogram etapu P2 z D-150 pkt 2; pozostałe ustalenia D-150 (w szczególności zakres P2, zasady akceptacji, zasady testów i zadania odłożone z etapu P1) nie zostają unieważnione. (9) Realizacja P2.1 rozpoczyna się po scaleniu PR z decyzją D-151 i osobnej zgodzie właściciela.
- **Uzasadnienie:** Koncentracja na projektowaniu jednego spójnego systemu wizualnego; uniknięcie równoległego poprawiania dwóch wersji językowych; wcześniejsze zatwierdzenie wszystkich elementów systemu treści; sprawniejsze przygotowanie wersji EN na podstawie kompletnego i zatwierdzonego systemu PL. Akceptacja P2.0 po analizie trzech plansz porównawczych P2.0 (telefon 390 px, tablet 768 px, desktop 1440 px).
- **Źródło:** własna decyzja właściciela (po konsultacji z ChatGPT)
- **Status:** Zatwierdzona

