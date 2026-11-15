# Wdrożenie dr KASIA DENT — aktualny punkt startowy

**Stan dokumentacji: 2026-11-15.** Dokument operacyjny dla Claude Code. Nie stanowi zgody na wdrożenie, merge, deployment, zakup hostingu ani modyfikację zatwierdzonych treści.

## Hierarchia źródeł prawdy

1. `CLAUDE.md` — zasady pracy, zakres uprawnień, technologia i wymóg odrębnej zgody na merge.
2. `docs/DECISIONS.md` — **oficjalny, append-only rejestr zatwierdzonych decyzji właściciela** (D-001 i kolejne; decyzje rozmowy 56–118 jako D-002–D-064).
3. `content/docs/DECISIONS_1-55.md` — historyczny rejestr decyzji rozmowy 1–55, wraz z późniejszą akceptacją tłumaczeń EN i mapy URL. Nie nadpisywać historii.
4. `content/docs/URL_MAP_PL_EN.md` — zatwierdzona mapa tras PL/EN, w tym artykułów i polityki prywatności.
5. `content/*_pl.md` i `content/*_en.md` — zatwierdzone treści; zmiany wymagają osobnej akceptacji.
6. `content/docs/CONTENT_AUDIT.md` — audyt, w tym historyczne uwagi oraz aktualizacja po akceptacji tłumaczeń; czytać najnowsze sekcje.
7. `content/WYMAGANIA_DLA_CLAUDE.md` — **archiwalne** wymagania; nie nadpisują powyższych decyzji.

## Najważniejsze wiążące decyzje

- **Technologia:** początkowo statyczny HTML/CSS/JS, bez Astro i bez obowiązkowego kroku build (decyzja rozmowy 3; CLAUDE.md).
- **PL/EN:** start jednoczesny; tłumaczenia EN zatwierdzone przez właściciela; weryfikacja medyczna pozostaje zadaniem przed publikacją. Stosować zatwierdzoną mapę URL.
- **Hosting:** Hostido/ViperHost lub inny wybór dopiero przed publikacją (56 C).
- **Testy:** prywatna wersja `https://www.kasiadent.pl/test/` z Basic Auth, wspólnym kontem, `noindex`, poza sitemap; wersja EN `/test/en/`; formularz oznaczony TEST (60 C, 65 A, 66 A, 110 A). **Decyzja 60 B (wyłącznie lokalnie) jest zastąpiona**.
- **Publikacja:** po zatwierdzonej checkliście, testach i osobnej zgodzie; kontrolowane przejście na domenę główną, rollback i 14 dni wzmożonej kontroli (74–78).
- **Formularz:** obowiązkowe imię, e-mail, **telefon**, wiadomość oraz wymagane zaznaczenie pola dotyczącego polityki prywatności; bez załączników. Formspree po weryfikacji RODO, PHP jako rezerwa; odbiorca `drkasiadent@gmail.com`. Uwaga: decyzja 104 zastępuje opcjonalność telefonu z 72; treść checkboxa wymaga weryfikacji prawnej. Nie zbierać szczegółów leczenia. Potwierdzenie na tej samej stronie; błędy z możliwością ponownej próby.
- **Wzorzec formularza:** nagłówek „Napisz do nas”, pola jedno pod drugim, checkbox z linkiem do polityki, przycisk „WYŚLIJ WIADOMOŚĆ”; użytkownik pokazał zrzut jako wzorzec układu. Nie przenosić jego kolorystyki ani stylu jako automatycznie zatwierdzonej identyfikacji wizualnej.
- **Kontakt:** godziny przyjęć **tylko na stronie Kontakt** (92 B). Telefon na telefonach jako `tel:`, na komputerach jako zwykły tekst (90 B). Adres i parking według zatwierdzonego Markdown.
- **Blog:** bez dat publikacji na stronie i kartach (81 B), autor widoczny jako `dr KASIA DENT` (82 B); bez wyszukiwarki, powiązanych artykułów, przycisków udostępniania (84 A, 85 B, 88 B). Nowe artykuły wymagają akceptacji PL/EN i metadanych (77 A).
- **Nawigacja:** bez przycisku „Powrót na górę” (87 B), bez sekcji „Poznaj pozostałe usługi” (86 B), aktywna pozycja menu, hamburger z Escape i kliknięciem poza menu, sticky CTA. Bez dedykowanego linku „Przejdź do treści” (96 B); **możliwy konflikt z celem WCAG 2.2 AA**, do sprawdzenia i rozstrzygnięcia, bez jednostronnego nadpisywania decyzji.
- **SEO:** Reda, pobliskie miejscowości/wsie, Rumia i Wejherowo; bez dopisywania nazw na siłę. Wizytówka Google do utworzenia. Canonical, hreflang, sitemap.xml, 301, HTTPS, Open Graph, Search Console.
- **Jakość:** WCAG 2.2 AA jako cel, testy wielu przeglądarek i urządzeń, Lighthouse >=90 w czterech kategoriach na mobile i desktop; Lighthouse nie dowodzi WCAG.
- **Bezpieczeństwo:** Turnstile, honeypot, rate limiting, logi bez treści wiadomości, nagłówki CSP/HSTS, 2FA, backup hostingu i GitHub, monitoring HTTPS/uptime.
- **Proces:** każda aktualizacja przez PR i zgodę przed merge; poprawki z testów w uporządkowanym rejestrze; CI kontroluje HTML i linki. Nie instalować narzędzi ani zależności bez odrębnej zgody.

## Rzeczy niewykonane i blokery publikacji

- Sama paczka `content/` zawiera Markdown, nie gotową witrynę HTML.
- Brak gotowych indeksów `/uslugi` i `/blog`; budować z zatwierdzonych treści, bez tworzenia nowych opisów bez zgody.
- Brak zatwierdzonej treści polityki prywatności/cookies PL/EN i strony 404; potrzebne opracowanie i akceptacja.
- Do potwierdzenia RODO: usługa formularza, zakres danych, podstawa przetwarzania i brzmienie checkboxa; mapa Google i ewentualne cookies.
- Potrzebne: ostateczna grafika Hero, zaakceptowana grafika Open Graph, licencje fontów, konfiguracja hostingu, uwierzytelnienie /test/, konfiguracja DNS/HTTPS, monitoring i backup.
- Zweryfikować możliwy konflikt 96 B z WCAG 2.2 AA; nie deklarować zgodności bez audytu.
- Ustalenia o domenie, URL i SEO są wymaganiami do wdrożenia, nie potwierdzeniem działania na produkcji.

## Minimalna checklista przed oddaniem do akceptacji

1. Zgodność tras z `content/docs/URL_MAP_PL_EN.md`; linki wewnętrzne, menu i breadcrumbs PL/EN.
2. Zgodność treści z zatwierdzonym Markdown; brak samodzielnych zmian copy i danych medycznych.
3. Formularz z wymaganym telefonem i checkboxem; testy poprawnej wysyłki, błędów, antyspamu, trybu TEST i RODO.
4. Testy mobile/desktop, klawiatury, dostępności, czytelności, WCAG, Lighthouse i ładowania obrazów.
5. HTTPS, przekierowania 301, canonical, hreflang, robots.txt, sitemap.xml, schema.org, Open Graph, GSC.
6. Backup/rollback, monitoring, ochrona /test/ hasłem, noindex i brak testowych URL w sitemap.
7. Ostateczny przegląd właściciela i **osobna zgoda na merge oraz deployment**.

## Zasada postępowania przy rozbieżnościach

Nie edytuj historycznych decyzji ani zatwierdzonych tekstów „dla spójności”. Stosuj nowszą wyraźnie zatwierdzoną decyzję, odnotuj konflikt i przedstaw go właścicielowi, jeśli nie da się go rozstrzygnąć bez nowej decyzji.

## Aktualizacja zatwierdzonych decyzji 119–191 (2026-11-15)

- Pełna treść decyzji: `docs/DECISIONS.md`, wpisy D-065–D-137. Wcześniejsze rozbieżności rozstrzygają nowsze decyzje: 181 A dopuszcza link „Przejdź do treści” widoczny przy fokusie klawiatury (zamiast 96 B); 184 B odkłada rozwój Google Business Profile na po uruchomieniu strony (zamiast 63 B).
- **Bezwzględna bramka projektowa:** przed pisaniem właściwej witryny Claude Design przygotowuje **trzy rzeczywiste, wyraźnie różne wizualne szkice strony głównej**, każdy desktop + mobile. Nie wystarczą opisy tekstowe. Stosować zatwierdzone treści, logo i kolorystykę; wykorzystać istniejący skill UI/UX Pro Max i ewentualne inne sprawdzone, dostępne skille. Instalacja nowych narzędzi wymaga osobnej zgody. Na tym etapie **nie** przygotowywać makiet podstron usług (189 B). Właściciel ocenia i może połączyć elementy propozycji; **bez jego akceptacji nie zaczynać implementacji**.
- Dopiero po akceptacji koncepcji: HTML/CSS/JS, etapami i osobnymi PR (180 A). Pierwszy etap wspólny układ i homepage PL/EN; kolejne: pozostałe strony, integracje i testy. Merge oraz deployment wymagają osobnych zgód.
- **Blog:** bez widocznych dat; w metadanych `BlogPosting.datePublished` rzeczywiste daty: mycie zębów 2026-11-15, leczenie kanałowe 2026-11-20, licówki 2026-11-25. Dat przyszłych nie deklarować jako już opublikowanych przed faktyczną publikacją. Blog rozwijać regularnie dla ruchu organicznego, bez CMS; każdy artykuł zatwierdzany PL/EN.
- **Strategia:** wszystkie siedem usług równorzędne (182 B), lokalne SEO skoncentrowane na Redzie i naturalnych odniesieniach do Rumi/Wejherowa (183 A), Google Business Profile po starcie strony (184 B), Search Console na start, GA4 później (186 A).
- **Kontakt i prywatność:** Google Maps ładuje się bezpośrednio na Kontakcie (159 B), ale wyłącznie po weryfikacji zgodności z wymogami prywatności; jeśli wymagana zgoda, należy ją obsłużyć przed załadowaniem mapy, a konflikt przedstawić właścicielowi. Formularz z wymaganymi polami i zabezpieczeniami z wcześniejszych decyzji; bez automatycznych odpowiedzi, z zachowaniem danych po błędzie. Nie dodawać osobnego komunikatu o pilnych przypadkach (149 B). Numer PL bez +48, EN z +48 (151 B).
- **Mobile i dostępność:** dolny CTA stale widoczny, ale nie zasłania treści ani formularza (168 A); sticky header stale widoczny (165 A); dopuszczony dyskretny skip link po fokusie (181 A); cel WCAG 2.2 AA pozostaje.
- **Operacje:** żadnych automatycznych deploymentów po merge, staging /test/ chroniony hasłem i oddzielnie zatwierdzany; testy realnego doręczenia formularza PL/EN na desktop/mobile; pełny odbiór i osobna zgoda na produkcję.

**Uwaga do wcześniejszych akapitów tego przewodnika:** w razie sprzeczności z niniejszą aktualizacją stosować nowsze decyzje 119–191, bez przepisywania historycznych zapisów.
