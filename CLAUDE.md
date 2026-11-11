# CLAUDE.md – zasady pracy nad projektem dr KASIA DENT

Projekt: strona internetowa gabinetu stomatologicznego dr KASIA DENT.
Repozytorium: https://github.com/jdostatni/kasiadent
Język komunikacji i treści strony: polski.

## 0. Role i podział decyzji
- **Właściciel projektu** podejmuje wszystkie ostateczne decyzje dotyczące architektury, technologii, wyglądu, funkcjonalności i treści.
- **ChatGPT** pełni funkcję analityka, planisty i recenzenta. Jego uwagi i rekomendacje są zapisywane w `docs/REVIEW.md`. ChatGPT widzi tylko to, co jest na GitHubie, a nie lokalne, niewysłane zmiany.
- **Claude Code** odpowiada za implementację, testowanie i przygotowanie zmian zatwierdzonych przez właściciela. Nie podejmuje decyzji projektowych na własną rękę.
- **Rekomendacje AI (Claude, ChatGPT i inne) nie są automatycznie zatwierdzonymi decyzjami.** Wdrożenie wymaga wyraźnej akceptacji właściciela.
- Model zgody na całe zadanie opisuje punkt 5 i decyzja D-001 w `docs/DECISIONS.md`.
- Zatwierdzone decyzje właściciela są rejestrowane w `docs/DECISIONS.md`. Wpis o statusie innym niż „Zatwierdzona" nie uprawnia do wdrożenia.
- Jeśli rekomendacja AI jest sprzeczna z zatwierdzoną decyzją, obowiązuje decyzja właściciela. Sprzeczność zgłoś do rozstrzygnięcia.
- Pliki `docs/DECISIONS.md` i `docs/REVIEW.md` aktualizuj tylko na polecenie właściciela.
- **Zatwierdzonych decyzji nie wolno merytorycznie nadpisywać ani usuwać.** Nowa decyzja zastępująca poprzednią jest zapisywana jako kolejny wpis, a poprzedni otrzymuje status „Zastąpiona przez D-xxx".
- Poprawki techniczne istniejących wpisów (np. literówka, błędny odnośnik, formatowanie) są dopuszczalne wyłącznie po zgodzie właściciela i nie mogą zmieniać treści decyzji.

## 1. Zatwierdzone elementy projektu
- Zatwierdzone teksty, logo, kolory, typografia i inne elementy identyfikacji wizualnej mogą być zmieniane **wyłącznie za wyraźną zgodą właściciela projektu** (zgoda może być zawarta w szczegółowo opisanym i zaakceptowanym planie zadania, punkt 2).
- Nie poprawiaj, nie skracaj i nie przeredagowuj zatwierdzonych treści na własną rękę, także w celu poprawy stylu lub pisowni. Zaproponuj zmianę i poczekaj na decyzję.
- Elementy zatwierdzone należy oznaczać w kodzie lub dokumentacji, aby było widać, które są chronione.
- Nie wymyślaj treści medycznych, cen, godzin otwarcia, danych kontaktowych ani opinii pacjentów. W razie braku danych użyj wyraźnie oznaczonego tekstu zastępczego i zapytaj.

## 2. Plan przed większymi zmianami
- Przed większą zmianą (nowa podstrona, zmiana struktury, układu, stylów globalnych, dodanie zależności lub narzędzia) przedstaw plan: cel, zakres, lista plików, ryzyka.
- Poczekaj na akceptację, zanim zaczniesz wprowadzać zmiany.
- Plan wymienia wprost także **operacje objęte zgodą**: gałąź (nazwa), zmieniane pliki, uzgodnione testy, poprawki błędów w zakresie, `git add` i `git commit`, `git push` gałęzi zadania oraz utworzenie Pull Requesta. Operacja niewymieniona w planie nie jest objęta zgodą (punkt 5).
- Zmiany architektury, technologii, zatwierdzonych treści i wyglądu wymagają wyraźnej akceptacji właściciela. Jeżeli zostały szczegółowo opisane i zaakceptowane w planie zadania, nie wymagają ponownej zgody podczas jego realizacji. **Każde odstępstwo od planu wymaga nowej zgody.**
- Przebieg zadania: plan, akceptacja właściciela, wykonanie, commit i push (jeśli objęte zgodą), Pull Request do przeglądu ChatGPT. Uwagi z przeglądu to rekomendacje i są wprowadzane dopiero po akceptacji właściciela. Merge następuje wyłącznie po osobnej zgodzie właściciela.
- Małe, jednoznaczne poprawki w ramach bieżącego zadania można wykonać bez planu, ale trzeba je zgłosić zgodnie z punktem 8.

## 3. Technologia i architektura
- Pierwsza wersja: czysty HTML, CSS i JavaScript, bez frameworków i bez kroku budowania, chyba że właściciel zdecyduje inaczej.
- Na początku stosuj **prostą, płaską strukturę HTML/CSS/JavaScript** (np. podstrony `.html`, wspólny folder na style, skrypty i obrazy). Nie narzucaj struktury folderów charakterystycznej dla Astro. Konkretną strukturę przedstaw w planie i uzgodnij przed utworzeniem.
- Struktura i kod mają ułatwiać późniejszą migrację do **Astro**:
  - powtarzalne elementy (nagłówek, stopka, nawigacja, kafelki usług) zapisuj w jednakowej, spójnej formie, tak aby dało się je później łatwo wydzielić do komponentów lub layoutu;
  - nie wymagaj ani nie udawaj komponentów, których czysty HTML nie obsługuje natywnie; powtarzalny fragment może być po prostu powielonym, identycznym blokiem kodu, wyraźnie oznaczonym komentarzem (np. początek i koniec fragmentu);
  - treści oddzielaj od struktury i stylów na tyle, na ile pozwala czysty HTML, i nie powielaj ich w wielu miejscach bez potrzeby;
  - JavaScript pisz modułowo i bez zależności od globalnego stanu, a style bez zależności od kolejności ładowania stron;
  - ścieżki do zasobów stosuj spójnie, aby uniknąć ich przepisywania przy migracji.
- Preferuj semantyczny HTML, dostępność (WCAG: kontrast, teksty alternatywne, nawigacja klawiaturą) i responsywność (podejście mobile-first).
- Nie dodawaj bibliotek ani zależności zewnętrznych bez zgody.

### Odporność na błędy i wydajność animacji
Zasady wizualne, ruch i dostępność opisuje `DESIGN.md`. Poniżej tylko wymagania techniczne.
- Treść i podstawowa nawigacja działają bez JavaScriptu i bez zewnętrznych bibliotek JS (progresywne ulepszanie). Awaria animacji nie może blokować strony ani ukrywać zawartości.
- Stan początkowy ukrywający element (np. `opacity: 0` przed animacją) ustawiaj dopiero po poprawnym uruchomieniu skryptu animacji (np. klasa dodana do `<html>`), a nie domyślnie w CSS.
- Skrypty animacji ładuj nieblokująco (`defer` lub moduł) i zabezpiecz je tak, aby ich błąd nie zatrzymał nawigacji ani menu mobilnego.
- Animuj wyłącznie `transform` i `opacity`. Nie animuj właściwości wymuszających przeliczanie układu (`width`, `height`, `top`, `left`, `margin`). `will-change` stosuj selektywnie i tylko dla elementów faktycznie animowanych.
- Preferuj CSS (`transition`, `animation`). Wejście sekcji w widok wykrywaj przez `IntersectionObserver`, a nie przez zdarzenie `scroll`.
- Rezerwuj miejsce na obrazy i placeholdery (`width` i `height` lub `aspect-ratio`), aby uniknąć przesunięć układu.
- `prefers-reduced-motion: reduce` wyłącza lub ogranicza ruch zbędny, a treść pozostaje widoczna.
- Przed zgłoszeniem animacji do akceptacji sprawdź ją przy wyłączonym JavaScripcie oraz przy ograniczonej wydajności (emulacja urządzenia mobilnego).

## 4. Spójność i style
- Wszystkie podstrony korzystają ze wspólnych arkuszy stylów. Nie duplikuj stylów w poszczególnych plikach HTML i nie używaj stylów inline.
- Kolory, czcionki, odstępy i rozmiary definiuj raz, jako zmienne CSS (custom properties) w jednym pliku, i używaj ich wszędzie.
- Nagłówek, stopka, nawigacja i przyciski mają wyglądać i działać tak samo na wszystkich podstronach.
- Przed dodaniem nowego stylu lub elementu sprawdź, czy nie istnieje już odpowiednik, i użyj go ponownie.
- Przyjmij jednolite nazewnictwo klas, plików i folderów (np. małe litery, myślniki, bez polskich znaków w nazwach plików).

## 5. Git, gałęzie i publikacja
### Zgoda na całe zadanie
- Zatwierdzony plan zadania (punkt 2) obejmuje wszystkie **wymienione w nim** operacje. Wykonuj je bez ponownych pytań i bez zatrzymywania się po każdym kroku.
- Zgoda dotyczy wyłącznie tego zadania, jego gałęzi i wymienionych plików. **Wygasa po zakończeniu zadania** i nie przenosi się na kolejne.
- Zgoda musi być wyraźna. Niejasną lub urwaną wiadomość traktuj jako brak zgody i dopytaj.
- Każde odstępstwo od zatwierdzonego planu (nowe pliki, nowe operacje, nowe narzędzia, zmiana zakresu) wymaga nowej zgody. Zatrzymaj się i zapytaj.
- Większe zmiany przygotowuj na **osobnej gałęzi**, nigdy bezpośrednio na `main`. Utworzenie i przełączenie na gałąź wymienioną w zatwierdzonym planie nie wymaga ponownej zgody.
- Przed commitem sprawdź listę zmienionych plików, zakres diff, brak sekretów i brak plików niezwiązanych z zadaniem. Przy niezgodności zatrzymaj się. Push wykonuj tylko gałęzi zadania, bez `--force`.

### Bez zgody (analiza)
- Czytanie plików i dokumentacji, `git status`, `git diff`, `git log`, `git fetch` i inne bezpieczne kontrole niezmieniające plików. Planowanie oraz zgłaszanie błędów, ryzyk i konfliktów.
- To nie jest zgoda na instalowanie narzędzi, uruchamianie niezweryfikowanego kodu ani zmienianie plików.

### Zawsze osobna zgoda właściciela, także w ramach zatwierdzonego zadania
- Scalanie do `main` (w tym merge Pull Requesta) i każda publikacja na hostingu (deployment).
- Instalacja nowych skilli, bibliotek i narzędzi.
- Zmiana zasad bezpieczeństwa.
- Usuwanie gałęzi, przepisywanie historii (`rebase`, `commit --amend` po wysłaniu, `reset --hard`, `push --force`) i inne operacje destrukcyjne.
- Zmiany architektury, technologii, zatwierdzonych treści, logo, kolorów, typografii, wyglądu oraz nowe funkcjonalności, chyba że zostały szczegółowo opisane i zaakceptowane w planie zadania (punkt 2). Każde odstępstwo od planu wymaga nowej zgody.

## 6. Bezpieczeństwo i dane
- Nie umieszczaj w repozytorium haseł, kluczy API, tokenów, plików `.env` ani innych sekretów.
- **Materiały zawierające wizerunek pacjentów lub dane osobowe** (imiona, nazwiska, zdjęcia, nagrania, dokumentacja, opinie z danymi osobowymi) **nie mogą trafiać do repozytorium bez wcześniejszego sprawdzenia podstawy prawnej (np. zgoda zgodna z RODO, tajemnica lekarska) i wyraźnej zgody właściciela projektu.** W przykładach i makietach używaj wyraźnie fikcyjnych danych.
- Pliki wrażliwe dodawaj do `.gitignore` (po uzgodnieniu).
- Jeśli znajdziesz w repozytorium dane wrażliwe, przerwij pracę i poinformuj o tym właściciela.
- Formularze kontaktowe i zgody (RODO, cookies, polityka prywatności) wymagają uzgodnienia przed wdrożeniem.

## 7. Zakres pracy
- Modyfikuj wyłącznie pliki związane z bieżącym zadaniem.
- Nie wykonuj przy okazji refaktoryzacji, formatowania ani porządków w plikach niezwiązanych z zadaniem.
- Jeśli zauważysz problem poza zakresem zadania, zgłoś go i poczekaj na decyzję, nie naprawiaj go samodzielnie.
- Zmieniaj pliki wskazane w zatwierdzonym planie, po sprawdzeniu ich zawartości. Usuwaj pliki tylko wtedy, gdy plan wymienia je wprost.

## 8. Raportowanie zmian
Po zakończeniu zadania przedstaw **jeden zbiorczy raport** (bez raportów pośrednich, chyba że pojawi się problem):
1. wykonane czynności,
2. listę zmodyfikowanych, dodanych i usuniętych plików z krótkim opisem zmian,
3. wyniki testów oraz to, czego nie sprawdzono lub nie zakończono,
4. identyfikator commita i link do Pull Requesta, jeśli istnieją,
5. problemy i ryzyka,
6. elementy wymagające decyzji właściciela.

## 9. Styl komunikacji
- Komunikuj się po polsku, zwięźle i konkretnie.
- W razie niejasności zapytaj, zamiast zgadywać.
- Jasno oddzielaj to, co zostało wykonane i sprawdzone, od tego, co jest propozycją.

## 10. Skill UI/UX Pro Max
- Skill `ui-ux-pro-max` (`.claude/skills/ui-ux-pro-max/`, wersja i źródło w pliku `VERSION`) daje wyłącznie **rekomendacje**. Nie zastępuje zatwierdzonych kolorów, logo, typografii ani tekstów (punkt 1).
- Flagi `--persist` i `--force` skryptu `search.py` (zapis plików `design-system/`) wymagają mojej zgody.
- Aktualizacja skilla lub dodanie innych skilli wymaga mojej zgody i wcześniejszego przeglądu kodu.
- Taste Skill jest odłożony: nie instaluj go ani nie uruchamiaj, dopóki właściciel nie zdecyduje inaczej.
