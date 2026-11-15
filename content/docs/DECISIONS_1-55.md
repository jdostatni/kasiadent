# dr KASIA DENT — rejestr decyzji 1–55

Status: decyzje z rozmów projektowych. Ten dokument porządkuje ustalenia; nie zastępuje zatwierdzonych treści Markdown. Przy sprzeczności sprawdzić najnowszą decyzję i uzyskać akceptację przed zmianą treści.

| Nr | Ustalenie |
|---|---|
| 1 | „Usługi” prowadzą do `/uslugi`; rozwijane menu siedmiu usług i „Wszystkie usługi”; kafelki usług na stronie głównej i przeglądowej. |
| 2 | Polskie adresy: `/`, `/o-mnie`, `/uslugi`, `/cennik`, `/pierwsza-wizyta`, `/blog`, `/kontakt`; zachować zatwierdzone ścieżki usług. |
| 3 | Pierwsza wersja: HTML/CSS/JS; ewentualne Astro dopiero później. |
| 4 | Hosting: Hostido lub ViperHost — wybór przed publikacją. |
| 5 | Kanoniczna domena `https://www.kasiadent.pl`; `drkasiadent.pl` przekierować 301; HTTPS. |
| 6 | Strona błędu 404 z poprawnym kodem HTTP. |
| 7 | Breadcrumbs pod hero, przed treścią podstron. |
| 8 | Zmiana języka zachowuje odpowiednią podstronę; gdy brak odpowiednika, przejście na stronę główną języka docelowego; bez automatycznego przekierowania według przeglądarki. |
| 9 | Przełącznik języka `PL | EN` w nagłówku. |
| 10 | Angielskie tłumaczone slugi URL; ostateczna mapa ścieżek do uzgodnienia. |
| 11 | Dane strukturalne: Dentist, Service, BreadcrumbList, BlogPosting, WebSite. |
| 12 | GA4 odłożone na później. |
| 13 | Google Search Console na start. |
| 14 | Formularz kontaktowy: imię, e-mail, wiadomość, prywatność, antyspam; IQ Dental później. |
| 15 | Interaktywna mapa Google i wskazówki dojazdu na stronie Kontakt, z uwzględnieniem prywatności. |
| 16 | Przycisk „Umów wizytę” prowadzi do `/kontakt`; telefon i e-mail klikalne. |
| 17 | Antyspam: Cloudflare Turnstile, limitowanie żądań po stronie serwera, wykrywanie duplikatów i honeypot. |
| 18 | Formspree do Gmail pod warunkiem weryfikacji RODO; alternatywa PHP na hostingu. RODO wymaga weryfikacji przed startem. |
| 19 | Jedna strona polityki prywatności i cookies w PL/EN; weryfikacja prawna przed publikacją. |
| 20 | Bez bannera cookies, jeśli prawo na to pozwala; w przeciwnym razie mechanizm zgody. |
| 21 | Stopka: cztery kolumny desktop (gabinet, nawigacja, usługi, kontakt), na telefonie pionowo; copyright i prywatność poniżej. |
| 22 | Ikony social media w stopce tylko dla faktycznie aktywnych profili. |
| 23 | FAQ na stronach usług i „Pierwsza wizyta”, bez oddzielnej podstrony FAQ. |
| 24 | FAQ w postaci akordeonu. |
| 25 | Hero na podstronach usług: szeroki obraz, tytuł i breadcrumbs, jeśli dostępny odpowiedni obraz. |
| 26 | Początkowo dopuszczalne ilustracje AI (Higgsfield/ChatGPT/Claude); później autentyczne zdjęcia profesjonalne; nie przedstawiać fikcyjnych zdjęć jako realnego gabinetu. |
| 27 | Jeden wspólny obraz hero dla wszystkich siedmiu podstron usług; zmienia się tytuł. |
| 28 | Hero na innych podstronach tylko tam, gdzie są dobre materiały. |
| 29 | Zdjęcia w treści usług opcjonalnie, tylko jeśli pasują. |
| 30 | Podstrona usługi: hero i breadcrumbs, pierwsza sekcja tekst po lewej i opcjonalny obraz po prawej, następne elastycznie; mobile jedna kolumna; zachować treść MD. |
| 31 | Kafelki usług według inspiracji OWS: trzy w rzędzie desktop, ikona liniowa, nazwa, zatwierdzony opis, „Dowiedz się więcej”; 7 usług. |
| 32 | Dawna propozycja sekcji „O mnie” na homepage: zdjęcie lekarza po lewej, tekst po prawej; **odłożona decyzją 43**. |
| 33 | Hero homepage: duży obraz AI z nałożonym tekstem i „Umów wizytę”. |
| 34 | Hero homepage wysokie, prawie na wysokość ekranu, inspirowane OWS. |
| 35 | Tekst hero po lewej stronie centralnej szerokości treści. |
| 36 | Uproszczony kierunek kolejności: Hero → Usługi → O mnie → Pierwsza wizyta → Kontakt; **nie usuwać pozostałych zatwierdzonych sekcji MD**; „O mnie” odłożone decyzją 43. |
| 37 | Trzy wyróżniki bezpośrednio pod Hero; dokładne zatwierdzone teksty z `strona-glowna_pl.md`. |
| 38 | „Twój uśmiech w dobrych rękach”: tekst wyśrodkowany, bez obrazu, zgodny z MD. |
| 39 | „Zajrzyj do naszego gabinetu”: galeria ukryta do czasu prawdziwych zdjęć. |
| 40 | „Jak wygląda pierwsza wizyta?”: tekst i przycisk „Dowiedz się więcej” do `/pierwsza-wizyta`, bez zdjęcia. |
| 41 | „Dlaczego pacjenci wybierają…”: lista jednokolumnowa, wyrównana do lewej, z pogrubionymi tytułami i opisami z MD; bez ikon/kafelków. |
| 42 | Mobile: jeden kafelek usług na rząd. |
| 43 | Bez osobnej sekcji „O mnie” na homepage na start; możliwość dodania później (To Do Later). Podstrona `/o-mnie` pozostaje. |
| 44 | Styl przycisków na podstawie dobrych rozwiązań OWS i doradztwa UI/UX Pro Max; bez odrębnego wyboru kształtu. |
| 45 | Menu zawsze widoczne podczas przewijania w dół (sticky), desktop i mobile. |
| 46 | Subtelne animacje przy przewijaniu, z obsługą `prefers-reduced-motion`. |
| 47 | Klasyczne mobilne menu hamburger, wzorowane na OWS. |
| 48 | Na telefonie „Umów wizytę” przyklejone do dolnej krawędzi ekranu. |
| 49 | Nagłówek ma stałą wysokość także podczas przewijania. |
| 50 | Dopuszczamy różne koncepcje obrazu Hero; nie tylko uśmiechnięta kobieta. Finalny obraz do akceptacji. |
| 51 | Przygotować tłumaczenia EN wszystkich trzech artykułów blogowych, do zatwierdzenia przed publikacją. |
| 52 | Publikacja PL i EN jednocześnie po zatwierdzeniu tłumaczeń i testach. |
| 53 | Godziny przyjęć: poniedziałek 9:00–18:00, czwartek 13:00–19:00. Nie dopowiadać godzin w pozostałe dni. |
| 54 | Adres e-mail do kontaktu: `drkasiadent@gmail.com`. |
| 55 | Zachować informacje o parkingu z zatwierdzonych MD: duży bezpłatny parking przed gabinetem, większy płatny w pobliżu. |

## Reguła pytań projektowych

Jeśli OWS Stomatologia ma dobre rozwiązanie, można przyjąć je jako wzorzec bez pytania o każdy drobiazg. Skill UI/UX Pro Max jest doradczy. Istotne zmiany wyglądu, funkcjonalności, treści i zatwierdzonych ustaleń wymagają akceptacji właściciela. Nie kopiować cudzych tekstów, grafik ani kodu.

## To Do Later

1. Google Analytics 4.
2. Integracja rezerwacji online z IQ Dental.
3. Ewentualna migracja HTML/CSS/JS do Astro.
4. Autentyczne profesjonalne zdjęcia lekarza, gabinetu i wyposażenia; wymiana stosownych grafik AI i uruchomienie galerii.
5. Rozważyć osobną sekcję „O mnie” na stronie głównej.

## Przed publikacją

- Zatwierdzić tłumaczenia EN trzech artykułów i poddać je weryfikacji medycznej.
- Uzgodnić finalną mapę adresów URL EN i skorygować linki w treści.
- Uzgodnić politykę prywatności/RODO, formularz i cookies.
- Zatwierdzić obraz Hero i rzeczywiste zdjęcia.
- Wybrać hosting i przetestować obie wersje językowe.
