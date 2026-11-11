# CLAUDE.md – zasady pracy nad projektem dr KASIA DENT

Projekt: strona internetowa gabinetu stomatologicznego dr KASIA DENT.
Repozytorium: https://github.com/jdostatni/kasiadent
Język komunikacji i treści strony: polski.

## 0. Role i podział decyzji
- **Właściciel projektu** podejmuje wszystkie ostateczne decyzje dotyczące architektury, technologii, wyglądu, funkcjonalności i treści.
- **ChatGPT** pełni funkcję analityka i recenzenta. Jego uwagi i rekomendacje są zapisywane w `docs/REVIEW.md`.
- **Claude Code** odpowiada za implementację i testowanie zmian zatwierdzonych przez właściciela. Nie podejmuje decyzji projektowych na własną rękę.
- **Rekomendacje AI (Claude, ChatGPT i inne) nie są automatycznie zatwierdzonymi decyzjami.** Wdrożenie wymaga wyraźnej akceptacji właściciela.
- Zatwierdzone decyzje właściciela są rejestrowane w `docs/DECISIONS.md`. Wpis o statusie innym niż „Zatwierdzona" nie uprawnia do wdrożenia.
- Jeśli rekomendacja AI jest sprzeczna z zatwierdzoną decyzją, obowiązuje decyzja właściciela. Sprzeczność zgłoś do rozstrzygnięcia.
- Pliki `docs/DECISIONS.md` i `docs/REVIEW.md` aktualizuj tylko na polecenie właściciela.
- **Zatwierdzonych decyzji nie wolno merytorycznie nadpisywać ani usuwać.** Nowa decyzja zastępująca poprzednią jest zapisywana jako kolejny wpis, a poprzedni otrzymuje status „Zastąpiona przez D-xxx".
- Poprawki techniczne istniejących wpisów (np. literówka, błędny odnośnik, formatowanie) są dopuszczalne wyłącznie po zgodzie właściciela i nie mogą zmieniać treści decyzji.

## 1. Zatwierdzone elementy projektu
- Zatwierdzone teksty, logo, kolory, typografia i inne elementy identyfikacji wizualnej mogą być zmieniane **wyłącznie za wyraźną zgodą właściciela projektu**.
- Nie poprawiaj, nie skracaj i nie przeredagowuj zatwierdzonych treści na własną rękę, także w celu poprawy stylu lub pisowni. Zaproponuj zmianę i poczekaj na decyzję.
- Elementy zatwierdzone należy oznaczać w kodzie lub dokumentacji, aby było widać, które są chronione.
- Nie wymyślaj treści medycznych, cen, godzin otwarcia, danych kontaktowych ani opinii pacjentów. W razie braku danych użyj wyraźnie oznaczonego tekstu zastępczego i zapytaj.

## 2. Plan przed większymi zmianami
- Przed większą zmianą (nowa podstrona, zmiana struktury, układu, stylów globalnych, dodanie zależności lub narzędzia) przedstaw plan: cel, zakres, lista plików, ryzyka.
- Poczekaj na akceptację, zanim zaczniesz wprowadzać zmiany.
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

## 4. Spójność i style
- Wszystkie podstrony korzystają ze wspólnych arkuszy stylów. Nie duplikuj stylów w poszczególnych plikach HTML i nie używaj stylów inline.
- Kolory, czcionki, odstępy i rozmiary definiuj raz, jako zmienne CSS (custom properties) w jednym pliku, i używaj ich wszędzie.
- Nagłówek, stopka, nawigacja i przyciski mają wyglądać i działać tak samo na wszystkich podstronach.
- Przed dodaniem nowego stylu lub elementu sprawdź, czy nie istnieje już odpowiednik, i użyj go ponownie.
- Przyjmij jednolite nazewnictwo klas, plików i folderów (np. małe litery, myślniki, bez polskich znaków w nazwach plików).

## 5. Git, gałęzie i publikacja
- **Nie wykonuj** `git add`, `git commit`, `git push`, `git merge`, `git rebase` ani żadnej publikacji (hosting, deployment) bez wyraźnej zgody właściciela projektu.
- Większe zmiany powinny być przygotowywane na **osobnych gałęziach Git**, a nie bezpośrednio na `main`. **Utworzenie gałęzi (podobnie jak jej usunięcie lub przełączenie) wymaga zgody właściciela.** Zaproponuj nazwę gałęzi i poczekaj na decyzję.
- Zgoda na jedną operację nie oznacza zgody na kolejne.
- Przed zaproponowaniem commita pokaż listę plików i proponowany opis commita.
- Operacji odczytowych (`git status`, `git diff`, `git log`) można używać swobodnie.

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
- Nie usuwaj ani nie nadpisuj istniejących plików bez wcześniejszego sprawdzenia ich zawartości i zgody.

## 8. Raportowanie zmian
Po każdej zmianie przedstaw:
1. listę zmodyfikowanych, dodanych i usuniętych plików,
2. krótki opis zmian w każdym pliku,
3. informację o tym, czego nie sprawdzono lub nie zakończono.

## 9. Styl komunikacji
- Komunikuj się po polsku, zwięźle i konkretnie.
- W razie niejasności zapytaj, zamiast zgadywać.
- Jasno oddzielaj to, co zostało wykonane i sprawdzone, od tego, co jest propozycją.

## 10. Skill UI/UX Pro Max
- Skill `ui-ux-pro-max` (`.claude/skills/ui-ux-pro-max/`, wersja i źródło w pliku `VERSION`) daje wyłącznie **rekomendacje**. Nie zastępuje zatwierdzonych kolorów, logo, typografii ani tekstów (punkt 1).
- Flagi `--persist` i `--force` skryptu `search.py` (zapis plików `design-system/`) wymagają mojej zgody.
- Aktualizacja skilla lub dodanie innych skilli wymaga mojej zgody i wcześniejszego przeglądu kodu.
