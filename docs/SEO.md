# docs/SEO.md – SEO i widoczność w wyszukiwarkach AI: dr KASIA DENT

**Status dokumentu:** specyfikacja SEO zatwierdzona przez właściciela do zapisu w repozytorium (13.11.2026). Dokument nie zastępuje `docs/DECISIONS.md`. Wpisy decyzji powstaną w osobnym zadaniu (`CLAUDE.md`, punkt 5).
**Data weryfikacji źródeł:** 13.11.2026. Dokumentacja dostawców zmienia się szybko, więc źródła i terminy weryfikujemy co kwartał (punkt 12.4).
**Domena kanoniczna:** `https://www.kasiadent.pl/`

## 0. Zasady nadrzędne i oznaczenia
- Pierwszeństwo mają `CLAUDE.md`, `DESIGN.md`, `docs/DECISIONS.md`, zatwierdzone teksty i najnowsze zatwierdzone decyzje właściciela.
- Oznaczenia:
  - **[POTWIERDZONE]**: oficjalna dokumentacja dostawcy, odczytana bezpośrednio, z odnośnikiem w punkcie 15.
  - **[ŹRÓDŁO POŚREDNIE]**: nie udało się odczytać oryginału, informacja pochodzi z podsumowania.
  - **[PRAKTYKA]**: dobra praktyka lub zasada projektu, niewymagana przez wyszukiwarki.
  - **[HIPOTEZA]**: praktyki eksperymentalne, badania firm SEO, deklaracje autorów narzędzi.
- Brak danych oznaczamy **DO ZATWIERDZENIA**. Czynności wymagające dostępu do domeny, DNS lub kont Google oznaczamy **WYMAGA DZIAŁANIA WŁAŚCICIELA**.
- Nie wymyślamy danych gabinetu, kwalifikacji, specjalizacji, opinii, godzin, cen, współrzędnych ani usług. Nie obiecujemy skuteczności leczenia.
- SEO, AEO i GEO **nie gwarantują** pozycji, cytowania ani rekomendacji gabinetu przez wyszukiwarki lub asystentów AI. `robots.txt` **nie jest gwarancją**, że treść nie zostanie wykorzystana do treningu modeli.
- Dokument nie zmienia zatwierdzonych polskich tekstów strony, nagłówków H1–H6, wyglądu ani funkcjonalności i nie upoważnia do implementacji strony, publikacji, instalacji narzędzi ani konfiguracji kont.

## 1. Decyzje zatwierdzone przez właściciela (wiążące)
| Obszar | Decyzja |
|---|---|
| Domena główna | `kasiadent.pl` |
| Host kanoniczny | `www.kasiadent.pl`; adres produkcyjny `https://www.kasiadent.pl/` |
| Domena dodatkowa | `drkasiadent.pl` oraz `www.drkasiadent.pl`, z przekierowaniem HTTP 301 na domenę główną. Wykupiona na 2 lata, przedłużenie to osobna decyzja |
| Adresy absolutne | Canonical, hreflang, `sitemap.xml`, JSON-LD, Open Graph i odnośniki absolutne używają wyłącznie `https://www.kasiadent.pl` |
| Języki | Wariant A: PL w katalogu głównym `/`, EN pod `/en/`. Polskie adresy bez zmian. Slugi EN są tłumaczone i czytelne. **Zatwierdzona jest architektura PL `/` i EN `/en/`. Pełna mapa slugów EN nie jest zatwierdzona i wymaga osobnej akceptacji.** Adres `/en/services/prosthetics` jest wyłącznie przykładem ilustracyjnym i nie zatwierdza pozostałej mapy |
| Wybór języka | Bez automatycznego przekierowania według lokalizacji lub języka przeglądarki jako jedynego sposobu dostępu do wersji językowej |
| hreflang i canonical | `pl` i `en`; metoda: znaczniki w `<head>`; każda istniejąca para ma wzajemne odnośniki (z odnośnikiem do siebie); każda wersja wskazuje własny canonical (EN nie wskazuje PL); bez hreflang do nieistniejących lub nieopublikowanych tłumaczeń; strona bez odpowiednika nie ma hreflang; `x-default` niewymagany |
| Przekierowania domen | 301, jednym skokiem, bez łańcuchów i pętli, z zachowaniem odpowiadających sobie ścieżek. Obsługa nieistniejących ścieżek zależna od możliwości hostingu (punkt 3.2) |
| Crawlery AI | Zezwalamy na indeksowanie i wyszukiwanie, ograniczamy wykorzystanie treści do treningu tam, gdzie można te mechanizmy rozdzielić. `robots.txt` ma pięć grup (punkt 5.2) |
| Google-Extended | **Dopuszczony** jako świadomie zatwierdzony wyjątek od polityki ograniczania treningu. Obejmuje zastosowania treningowe i uziemianie odpowiedzi Gemini (punkt 11.2a). Bez obietnic cytowania |
| AIPREF | **Odroczony.** Token `__usage_ai-training` nie jest częścią produkcyjnego `robots.txt`. Mechanizm do ponownej weryfikacji po ustabilizowaniu specyfikacji i polityk dostawców (punkt 11.5) |
| IndexNow | Odłożony na późniejszy etap. Bez pliku klucza, skryptów i integracji |
| Metadane | Końcowe meta title i meta description powstaną zbiorczo w osobnym etapie. Metadane z nagłówków plików treści są robocze i niezatwierdzone |
| Keyword Planner | Eksporty poza publicznym repozytorium. Obszar lokalny: Reda, województwo pomorskie, Polska (deklarowany, niepotwierdzony w plikach CSV). Dalsze badania są rekomendacją, a nie warunkiem etapu metadanych |
| Mapa fraz | Mapa intencji, priorytety P1/P2/P3 (RTG na P2) i główne przypisanie „licówki Reda" do Stomatologii estetycznej są zatwierdzone. Osobnej zgody wymagają dopiero konkretne zmiany treści, nagłówków lub metadanych |
| Schema.org | Jeden `WebSite` dla całego serwisu i odrębne `WebPage` dla wersji językowych. Placeholdery tylko w dokumentacji, a w implementacji niezatwierdzone właściwości pomijamy |
| Okruszki | Trzy warianty: ze stroną `/uslugi`, bez niej i bez znacznika BreadcrumbList. Wybór przy zatwierdzaniu struktury i projektu strony |
| Audyt AI | Zestaw pełny: 45 pytań. Zestaw podstawowy: 13 pytań. Bez automatyzacji płatnymi API |

Wpisy w `docs/DECISIONS.md` (kolejne identyfikatory) powstaną po zatwierdzeniu tego dokumentu, w osobnym zadaniu.

## 2. Dane podmiotu (NAP) i Profil Firmy w Google
- **Źródło NAP:** zatwierdzony plik `kontakt_pl.md` (nazwa, adres, telefon, e-mail, godziny). Dane w identycznej formie w stopce, na stronie Kontakt, w JSON-LD, w Profilu Firmy i w katalogach. Pliki treści są dziś poza repozytorium (punkt 16).
- **Rozbieżności do rozstrzygnięcia przed publikacją:** (a) e-mail jest w `kontakt_pl.md`, a `pierwsza-wizyta_pl.md` zawiera „do uzupełnienia"; (b) godziny „09:00 – 19:00" bez dni tygodnia; (c) jednolity zapis nazwy i adresu.
- **Profil Firmy [POTWIERDZONE]:** nazwa odzwierciedla rzeczywistą nazwę używaną w lokalu i na stronie, bez dodatków (hasła, godziny, telefon, adres www, opis usług); adres rzeczywisty; kategorie: jak najmniej, jak najbardziej szczegółowe i opisujące czym firma *jest*; opis bez linków, promocji i cen; jedna firma w jednej lokalizacji ma jeden profil; lekarz może mieć własny profil, jeśli jest osobą publicznie dostępną w zweryfikowanej lokalizacji w podanych godzinach, a przy kilku praktykach w jednym miejscu profil lekarza używa wyłącznie jego imienia i nazwiska ([wytyczne](https://support.google.com/business/answer/3038177)).
- **DO ZATWIERDZENIA:** czy Profil Firmy istnieje i kto go prowadzi; czy jeden profil, czy także profil lekarza; kategorie; zdjęcia (bez wizerunku pacjentów, `CLAUDE.md` punkt 6).
- **[PRAKTYKA]** Opinii nie kupujemy ani nie selekcjonujemy, a odpowiedzi na opinie nie ujawniają, że ktoś jest pacjentem (tajemnica lekarska, punkt 10.3). Zasady Google dotyczące opinii: do sprawdzenia w aktualnej polityce (nie weryfikowano).
- **Mapa:** zatwierdzony link do Map Google w `kontakt_pl.md` jako odnośnik. Osadzenie mapy to zewnętrzna integracja (`DESIGN.md`), więc wymaga decyzji. Telefon jako odnośnik `tel:`, dane kontaktowe jako tekst HTML.

## 3. Domena, hosting i przekierowania

### 3.1 Konfiguracja hostów
| Host | Rola | Zachowanie |
|---|---|---|
| `https://www.kasiadent.pl` | produkcja, host kanoniczny | odpowiedź 200, indeksowany |
| `kasiadent.pl` (http i https) | alias domeny głównej | 301 na `https://www.kasiadent.pl` |
| `http://www.kasiadent.pl` | alias protokołu | 301 na `https://www.kasiadent.pl` |
| `drkasiadent.pl`, `www.drkasiadent.pl` (http i https) | domena dodatkowa | 301 na `https://www.kasiadent.pl`. Brak własnej treści, sitemapy i canonical |

### 3.2 Reguły przekierowań
Każde z zatwierdzonych przekierowań prowadzi **jednym skokiem** na adres końcowy:

| Żądanie | Odpowiedź |
|---|---|
| `http://kasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `https://kasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `http://www.kasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `http://drkasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `https://drkasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `http://www.drkasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |
| `https://www.drkasiadent.pl/` | 301 → `https://www.kasiadent.pl/` |

- **Ścieżki:** dla adresów podstron stosujemy ten sam schemat z zachowaniem ścieżki, jeśli odpowiednik istnieje (np. `http://kasiadent.pl/uslugi/protetyka` → `https://www.kasiadent.pl/uslugi/protetyka`). **Nie przekierowujemy wszystkich adresów bezrefleksyjnie na stronę główną.**
- **Wymagania:** stałe HTTP 301 (**[POTWIERDZONE]** 301 i 308 są stałe, a rekomendowane są stałe przekierowania po stronie serwera, [Google](https://developers.google.com/search/docs/crawling-indexing/301-redirects)); **bez łańcuchów i pętli** (wskazówki Google w odczytanej treści nie opisują łańcuchów, więc to **[PRAKTYKA]**: z `http://drkasiadent.pl` bezpośrednio na adres końcowy HTTPS, nie przez pośredni host); **poprawne certyfikaty HTTPS dla wszystkich czterech nazw, które odpowiadają** (`www.kasiadent.pl`, `kasiadent.pl`, `drkasiadent.pl`, `www.drkasiadent.pl`), żeby użytkownik nie zobaczył ostrzeżenia przed przekierowaniem; jedna domena kanoniczna; domena dodatkowa nie jest indeksowana osobno i nie występuje w `sitemap.xml` ani jako canonical.
- **`robots.txt` na hostach przekierowujących:** żądanie `/robots.txt` kierujemy 301 na kanoniczny plik. **[POTWIERDZONE]** Google podąża za co najmniej pięcioma przekierowaniami przy pobieraniu `robots.txt` ([specyfikacja](https://developers.google.com/search/docs/crawling-indexing/robots/robots_txt)).
- **Konwencja adresów:** adres bez rozszerzenia `.html` i bez końcowego ukośnika (spójnie z zatwierdzonymi `/uslugi/protetyka`; adres główny `/`). Warianty (z ukośnikiem, `.html`) 301 na adres kanoniczny, połączone z przekierowaniem hosta w jednym skoku. Możliwość konfiguracji na wybranym hostingu: DO ZATWIERDZENIA.
- **Ścieżki bez odpowiednika.** Nie zakładamy, że nieznany adres musi najpierw zostać przekierowany na host kanoniczny, żeby dopiero tam zwrócić 404. Wybór wariantu zależy od możliwości hostingu (DO ZATWIERDZENIA razem z wyborem hostingu):

| Wariant | Działanie | Wymaga od hostingu | Adres nieznany |
|---|---|---|---|
| A. Selektywny (rekomendowany, jeśli hosting go obsługuje) | 301 tylko dla adresów, które istnieją na hoście kanonicznym (lista ścieżek lub warunek „plik lub trasa istnieje") | reguły z listą ścieżek albo warunkiem istnienia pliku | host aliasu zwraca 404 bezpośrednio, bez przekierowania |
| B. Ogólny z zachowaniem ścieżki | 301 każdego adresu na ten sam adres na `https://www.kasiadent.pl` | jedna reguła z zachowaniem ścieżki | jedno 301, po nim host kanoniczny zwraca 404 |
| C. Wszystko na stronę główną | 301 każdego adresu na `/` | – | **odrzucony** |

- Warianty A i B są poprawne, jeśli **końcowy status to 404** (nie 200). **[PRAKTYKA]** Wariant C wprowadza użytkownika i roboty w błąd. Wariant B działa na każdym hostingu, a wariant A wymaga aktualizacji listy przy dodaniu strony.
- Zasada dotyczy wszystkich hostów przekierowujących (`kasiadent.pl`, `http://www.kasiadent.pl`, `drkasiadent.pl`, `www.drkasiadent.pl`). W obu wariantach `/robots.txt` i `/sitemap.xml` (znane ścieżki) są kierowane 301 na adresy kanoniczne. Host aliasu zwracający 404 ma poprawny certyfikat.

### 3.3 Kontrola terminu ważności domen
- Domena dodatkowa jest wykupiona na 2 lata. **Data wygaśnięcia, rejestrator i automatyczne odnawianie obu domen:** dane do uzupełnienia (**WYMAGA DZIAŁANIA WŁAŚCICIELA**).
- **Plan kontroli [PRAKTYKA]:** przypomnienia 90, 60 i 30 dni przed wygaśnięciem w kalendarzu właściciela; kontrola terminu w audycie kwartalnym (panel rejestratora); decyzja o przedłużeniu domeny dodatkowej to osobna decyzja. Konsekwencja wygaśnięcia: przekierowania przestają działać, a domena może zostać zarejestrowana przez osoby trzecie.

### 3.4 Hosting i DNS (DO ZATWIERDZENIA)
- Wybór hostingu, dostawcy DNS i technicznego sposobu konfiguracji przekierowań (reguły hostingu, DNS, usługa przekierowań rejestratora) pozostaje otwarty. Przy usłudze rejestratora sprawdzamy, czy zwraca 301, obsługuje HTTPS i zachowuje ścieżkę. **[PRAKTYKA]**
- Wymagania wobec hostingu statycznej strony HTML: HTTPS z automatycznym odnawianiem certyfikatów dla czterech nazw; reguły 301 jak w punkcie 3.2; własna strona błędu 404 zwracająca status 404; `robots.txt` i `sitemap.xml` w katalogu głównym hosta kanonicznego; kompresja i nagłówki cache; **dostęp do logów żądań** (audyt botów AI, punkt 11.8); ochrona środowiska testowego hasłem; lokalizacja serwerów i zgodność z RODO.
- **Dane do sprawdzenia przed uruchomieniem:** czy `kasiadent.pl` lub `drkasiadent.pl` miały wcześniej treści i adresy w wynikach wyszukiwania (Search Console, wyszukiwarka). Jeśli tak, mapowanie starych adresów na odpowiedniki.
- **Środowisko testowe:** hasło lub `noindex`, nigdy `Disallow: /` skopiowane na produkcję.

## 4. Struktura URL i tabela adresów PL/EN
### 4.1 Zasady
- **[PRAKTYKA]** Małe litery, myślniki, bez polskich znaków i bez apostrofów (`CLAUDE.md`, punkt 4), bez parametrów w adresach treści. Adresy stabilne. Zmiana po publikacji wymaga 301 oraz aktualizacji sitemapy, canonical i hreflang.
- **Polskich adresów nie zmieniamy bez osobnej zgody.** Slugi EN są tłumaczone i czytelne. **Zatwierdzona jest architektura PL `/` i EN `/en/`. Pełna mapa slugów EN nie jest zatwierdzona i wymaga osobnej akceptacji.** Adres `/en/services/prosthetics` jest przykładem ilustracyjnym i nie zatwierdza pozostałej mapy. Wszystkie angielskie slugi w tabeli 4.2 są propozycjami.
- Strona EN trafia do hreflang i sitemapy dopiero, gdy jest opublikowana. Wersje EN są roboczymi tłumaczeniami wymagającymi przeglądu gabinetu przed publikacją.

### 4.2 Tabela adresów
| Strona | Adres PL (status) | Adres EN (status) | Alternatywa EN |
|---|---|---|---|
| Start | `/` (zatwierdzony) | `/en/` (zatwierdzony) | – |
| O mnie | adres DO ZATWIERDZENIA (proponowany: `/o-mnie`) | `/en/about-me` (propozycja) | `/en/about` |
| Usługi (przegląd) | `/uslugi` (brak zatwierdzonego pliku treści; punkt 7.3) | `/en/services` (propozycja) | – |
| Stomatologia zachowawcza | `/uslugi/stomatologia-zachowawcza` (zatwierdzony) | `/en/services/general-dentistry` (propozycja) | `/en/services/restorative-dentistry` |
| Endodoncja mikroskopowa | `/uslugi/leczenie-kanalowe-pod-mikroskopem` (zatwierdzony) | `/en/services/root-canal-treatment-under-microscope` (propozycja) | `/en/services/microscopic-endodontics` |
| Protetyka | `/uslugi/protetyka` (zatwierdzony) | `/en/services/prosthetics` (przykład ilustracyjny, mapa niezatwierdzona) | – |
| Stomatologia estetyczna | `/uslugi/stomatologia-estetyczna` (zatwierdzony) | `/en/services/cosmetic-dentistry` (propozycja) | `/en/services/aesthetic-dentistry` |
| Profilaktyka | `/uslugi/profilaktyka` (zatwierdzony) | `/en/services/preventive-dentistry` (propozycja) | – |
| Stomatologia dziecięca | `/uslugi/stomatologia-dziecieca` (zatwierdzony) | `/en/services/childrens-dentistry` (propozycja) | `/en/services/pediatric-dentistry` |
| Diagnostyka RTG | `/uslugi/diagnostyka-rtg` (zatwierdzony) | `/en/services/dental-x-ray` (propozycja) | `/en/services/dental-x-ray-diagnostics` |
| Cennik | `/cennik` (z zatwierdzonych odnośników, do potwierdzenia) | `/en/price-list` (propozycja) | `/en/prices` |
| Pierwsza wizyta | `/pierwsza-wizyta` (z zatwierdzonych odnośników, do potwierdzenia) | `/en/first-visit` (propozycja) | – |
| Kontakt | `/kontakt` (z zatwierdzonych odnośników, do potwierdzenia) | `/en/contact` (propozycja) | – |
| Blog | adres DO ZATWIERDZENIA (proponowany: `/blog`) | `/en/blog` (propozycja) | – |

## 5. Techniczne SEO: indeksowanie, `robots.txt`, `sitemap.xml`, canonical

### 5.1 Statusy HTTP i dostępność treści
- **[PRAKTYKA]** Strony treści zwracają 200. Stałe przekierowania: 301. Nieistniejące adresy: 404 ze statusem 404 (nie „soft 404"). Brak martwych odnośników i stron osieroconych. Odnośniki jako zwykłe `<a href>`.
- Treść i nawigacja działają bez JavaScriptu (`CLAUDE.md`). `<html lang="pl">` i `<html lang="en">`, `charset`, `viewport`.
- Nagłówek HSTS: opcjonalny, trudny do cofnięcia. Dopiero po stabilnym HTTPS i za zgodą.

### 5.2 `robots.txt`
**Fakty [POTWIERDZONE]** ([specyfikacja Google](https://developers.google.com/search/docs/crawling-indexing/robots/robots_txt), [wprowadzenie](https://developers.google.com/search/docs/crawling-indexing/robots/intro)):
- `robots.txt` służy do zarządzania ruchem robotów i **nie jest mechanizmem wykluczania stron z Google**. Zablokowany adres może pojawić się w wynikach bez opisu. Do wykluczenia służy `noindex` albo ochrona hasłem. Blokowanie zasobów potrzebnych do wyświetlenia strony może pogorszyć jej rozumienie.
- Plik obowiązuje **tylko dla hosta, protokołu i portu**, na którym leży (`www.kasiadent.pl` nie obejmuje `kasiadent.pl`). Dla robota obowiązuje **jedna, najbardziej szczegółowa grupa** (grupy nazwane i `*` nie są łączone). Obsługiwane pola: `user-agent`, `allow`, `disallow`, `sitemap`. UTF-8, do 500 KiB. `crawl-delay` jest przez Google ignorowany.
- Błędy: 4xx (poza 429) oznaczają brak ograniczeń; 5xx wstrzymuje crawlowanie na 12 godzin, a potem używa ostatniej poprawnej wersji do 30 dni. Cache do 24 godzin.

**Projekt produkcyjny** (`https://www.kasiadent.pl/robots.txt`), pięć grup `User-agent`:
```
# robots.txt dla https://www.kasiadent.pl/  (PROJEKT; stan źródeł: 13.11.2026)
#
# POLITYKA: wyszukiwanie dopuszczone; trening AI ograniczony tam, gdzie dostawca
# rozdziela trening i wyszukiwanie. TEN PLIK NIE JEST GWARANCJĄ niewykorzystania treści.
#
# Grupa "*" dopuszcza m.in. Googlebot, Bingbot, OAI-SearchBot, PerplexityBot,
# Claude-SearchBot, meta-webindexer oraz roboty działające na żądanie użytkownika.
# Dla robota obowiązuje tylko jedna, najbardziej szczegółowa grupa, więc reguły
# dopisane do "*" nie obejmą robotów nazwanych niżej.
User-agent: *
Allow: /

# Google-Extended: DOPUSZCZONY celowo (decyzja właściciela; wyjątek od polityki
# ograniczania treningu; obejmuje trening Gemini i uziemianie w Gemini Apps).
User-agent: Google-Extended
Allow: /

# Crawlery treningowe: zablokowane
User-agent: GPTBot
Disallow: /

User-agent: ClaudeBot
Disallow: /

User-agent: meta-externalagent
Disallow: /

# Sygnał AIPREF: odroczony (docs/SEO.md, punkt 11.5)

Sitemap: https://www.kasiadent.pl/sitemap.xml
```
**Objaśnienia:**
- Wyszukiwarki (`Googlebot`, `Bingbot`), roboty wyszukiwania AI (`OAI-SearchBot`, `PerplexityBot`, `Claude-SearchBot`, `meta-webindexer`) i roboty działające na żądanie użytkownika korzystają z grupy `*`. Osobne grupy `Allow: /` są zbędne.
- **Jawna grupa `Google-Extended` zostaje**, bo dokumentuje świadomą decyzję i chroni ją przed przyszłymi zmianami ogólnych reguł. **[POTWIERDZONE]** Google planuje po wdrożeniu wspólnego sygnału AIPREF traktować brak jawnej reguły `Google-Extended` przy zakazie treningu jak zablokowany `Google-Extended` ([blog Google, 30.10.2026](https://developers.google.com/search/blog/2026/10/ai-training-control)).
- Nazwy robotów i ich role **[POTWIERDZONE]**: `OAI-SearchBot` (wyszukiwanie ChatGPT), `GPTBot` (trening; „wyłączenie oznacza, że treść nie powinna być używana do treningu"), `ChatGPT-User` (na żądanie użytkownika, `robots.txt` może nie obowiązywać) ([OpenAI](https://developers.openai.com/api/docs/bots)); `PerplexityBot` (wyniki, nie trening), `Perplexity-User` (zasadniczo ignoruje `robots.txt`) ([Perplexity](https://docs.perplexity.ai/docs/resources/perplexity-crawlers)); `Claude-SearchBot`, `Claude-User`, `ClaudeBot` (trening) ([Anthropic](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler)); `Meta-WebIndexer` (wyszukiwanie Meta AI), `Meta-ExternalAgent`, `Meta-ExternalFetcher` ([Meta](https://developers.facebook.com/documentation/sharing/webmasters/web-crawlers)); `Google-Extended` ([Google](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers)); `Bingbot` (nazwa wynika z komunikatów Microsoftu o preferencjach AI).
- **Meta-ExternalAgent:** Meta opisuje go jako crawler treningowy i indeksujący na potrzeby produktów. Wyszukiwanie Meta AI obsługuje `Meta-WebIndexer`. Skutek blokady `Meta-ExternalAgent` dla innych produktów Meta nie jest opisany, więc nie zakładamy, że nie ma wpływu na wyszukiwanie.
- Nie ujęto robotów, których nie weryfikowano w tej analizie (m.in. Common Crawl, Applebot-Extended, ByteDance). Czy je dodać: punkt 17.3.
- Roboty uruchamiane przez użytkownika (`ChatGPT-User`, `Perplexity-User`, `Meta-ExternalFetcher`, `Google-Agent`, `Google-GeminiNotebook`) mogą ignorować `robots.txt` ([Google](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers)). Zmiany w `robots.txt` działają z opóźnieniem do około 24 godzin.
- Plik `robots.txt` musi być dostępny (status 200), a błąd 5xx wstrzymuje crawlowanie (punkt 12.3).

### 5.3 `sitemap.xml`
- **[POTWIERDZONE]** Format XML, UTF-8, adresy bezwzględne, do 50 000 adresów i 50 MB na plik; tylko adresy kanoniczne; Google ignoruje `<priority>` i `<changefreq>`, a `<lastmod>` uwzględnia, gdy jest konsekwentnie i wiarygodnie prawdziwy; sitemapa w katalogu głównym, zgłoszona w Search Console i linią `Sitemap:`; zgłoszenie to wskazówka, a nie gwarancja ([Google](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)). **[POTWIERDZONE]** Bing: sitemapy to fundamentalny sygnał pokrycia, `lastmod` ma odzwierciedlać rzeczywistą zmianę treści (ISO 8601 z godziną) ([Bing](https://blogs.bing.com/webmaster/2025/7/Keeping-Content-Discoverable-with-Sitemaps-in-AI-Powered-Search/)).
- **Projekt:** jedna sitemapa `https://www.kasiadent.pl/sitemap.xml` dla opublikowanych stron PL i EN. Adnotacje hreflang są w `<head>`, a nie w sitemapie (zatwierdzona metoda). **Domena dodatkowa i nieopublikowane tłumaczenia nie występują w sitemapie.** Strony `noindex` i przekierowane nie trafiają do sitemapy.
- **Placeholderów nie publikujemy w XML.** Poniżej rozróżniamy szablon dokumentacyjny od poprawnego pliku produkcyjnego.

**Szablon dokumentacyjny (NIE do publikacji; wartości w nawiasach kwadratowych są objaśnieniem):**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://www.kasiadent.pl/</loc>
    <lastmod>[RRRR-MM-DDThh:mm:ss+01:00 – data rzeczywistej zmiany treści]</lastmod>
  </url>
  <url>
    <loc>https://www.kasiadent.pl/uslugi/protetyka</loc>
    <lastmod>[RRRR-MM-DDThh:mm:ss+01:00 – data rzeczywistej zmiany treści]</lastmod>
  </url>
  <!-- wpisy EN (np. https://www.kasiadent.pl/en/) dopiero po publikacji tłumaczeń -->
</urlset>
```
**Poprawny plik produkcyjny (forma bez placeholderów; element `<lastmod>` pomijamy, dopóki nie znamy rzeczywistej daty zmiany, i dodajemy go z prawdziwą datą, np. `2026-12-01T10:00:00+01:00` w formacie ISO 8601):**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://www.kasiadent.pl/</loc>
  </url>
  <url>
    <loc>https://www.kasiadent.pl/uslugi/protetyka</loc>
  </url>
</urlset>
```
Lista adresów w pliku produkcyjnym obejmuje wyłącznie opublikowane strony (adresy z zatwierdzonej mapy). Przykładowa data w powyższym opisie nie jest wartością do skopiowania. Brak `<lastmod>` jest poprawny, a niewiarygodny `lastmod` jest gorszy niż jego brak.
- `lastmod` zmieniamy przy istotnej zmianie treści, a nie przy zmianie roku w stopce. Sposób utrzymania pliku bez kroku budowania (ręcznie lub prostym skryptem, który jest narzędziem wymagającym zgody, `CLAUDE.md` punkt 3): DO ZATWIERDZENIA (punkt 17.2).

### 5.4 Canonical
- **[POTWIERDZONE]** Metody od najsilniejszej: przekierowanie 301, `rel="canonical"`, sitemapa. Strona kanoniczna ma canonical do siebie. Adresy bezwzględne. Nie używać `robots.txt` ani `noindex` do wyboru wersji kanonicznej. Nie podawać różnych adresów kanonicznych różnymi metodami ([Google](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)).
- **Projekt:** każda strona ma canonical do własnego adresu `https://www.kasiadent.pl/...`. Wersja EN ma canonical do siebie, **nie do PL**. Canonical nigdy nie wskazuje domeny dodatkowej ani środowiska testowego.

### 5.5 Indeksowanie
- **Google:** Search Console (weryfikacja domeny rekordem TXT, sitemapa, inspekcja adresów). **Bing:** Bing Webmaster Tools. **WYMAGA DZIAŁANIA WŁAŚCICIELA** (konta, DNS). Szczegóły: punkt 13.
- **IndexNow: odłożony na późniejszy etap.** Nie dodajemy pliku klucza, skryptów ani integracji. Pozostaje w planie późniejszej optymalizacji. **[POTWIERDZONE]** Protokół powiadamia wyszukiwarki o zmianach adresów, kod 200 oznacza tylko przyjęcie, a nie indeksowanie ([IndexNow](https://www.indexnow.org/documentation)).
- **[PRAKTYKA]** Strony testowe i robocze są chronione hasłem lub mają `noindex`. Nie zgłaszamy ich do indeksowania.

### 5.6 Obrazy, znaczniki w `<head>` i Open Graph
- **[PRAKTYKA]** Tekst alternatywny PL i EN, nazwy plików bez polskich znaków, `width` i `height` lub `aspect-ratio`, opisane placeholdery do czasu zdjęć (`DESIGN.md`).
- **Open Graph:** `og:url` = adres kanoniczny `https://www.kasiadent.pl/...`, `og:locale` zgodny z wersją, obrazy pod adresem absolutnym `https://www.kasiadent.pl/...`. Teksty OG (`og:title`, `og:description`) powstają razem z zatwierdzonymi metadanymi. Obraz udostępniania wymaga zatwierdzonego zdjęcia lub grafiki (bez fikcyjnych zdjęć).

## 6. Wersje językowe: hreflang i canonical

### 6.1 Zasady
- **[POTWIERDZONE]** Adnotacje hreflang można podać w `<head>`, w nagłówku HTTP lub w sitemapie. Google traktuje metody równoważnie. Każda wersja wymienia siebie i pozostałe, a zestaw jest identyczny na każdej wersji. Adresy w pełni kwalifikowane. Wymagane są linki zwrotne. Kody: ISO 639-1 języka, opcjonalnie region. `x-default` to strona zapasowa dla języków spoza zestawu (np. strona wyboru języka). Google nie używa atrybutu `lang` do wyboru języka. Wersje z nieprzetłumaczoną treścią główną są duplikatami ([Google](https://developers.google.com/search/docs/specialty/international/localized-versions)).
- **Zatwierdzone zasady:** kody `pl` i `en`; metoda: `<head>`; każda istniejąca para ma wzajemne odnośniki (z odnośnikiem do siebie); canonical własny; brak hreflang do nieopublikowanych tłumaczeń; strona bez odpowiednika nie ma hreflang; `x-default` niewymagany.
- Wybór języka przez użytkownika: widoczny przełącznik języka (element interfejsu, punkt 16) i brak automatycznego przekierowania według lokalizacji lub języka przeglądarki jako jedynej drogi.

### 6.2 Przykłady (adres `/en/services/prosthetics` jest przykładem ilustracyjnym i nie zatwierdza mapy slugów EN)
**Strona główna PL (`https://www.kasiadent.pl/`):**
```html
<html lang="pl">
<head>
  <link rel="canonical" href="https://www.kasiadent.pl/">
  <link rel="alternate" hreflang="pl" href="https://www.kasiadent.pl/">
  <link rel="alternate" hreflang="en" href="https://www.kasiadent.pl/en/">
</head>
```
**Strona główna EN (`https://www.kasiadent.pl/en/`):**
```html
<html lang="en">
<head>
  <link rel="canonical" href="https://www.kasiadent.pl/en/">
  <link rel="alternate" hreflang="pl" href="https://www.kasiadent.pl/">
  <link rel="alternate" hreflang="en" href="https://www.kasiadent.pl/en/">
</head>
```
**Podstrona usługi PL (`/uslugi/protetyka`) i EN (`/en/services/prosthetics`, adres ilustracyjny):**
```html
<!-- https://www.kasiadent.pl/uslugi/protetyka -->
<link rel="canonical" href="https://www.kasiadent.pl/uslugi/protetyka">
<link rel="alternate" hreflang="pl" href="https://www.kasiadent.pl/uslugi/protetyka">
<link rel="alternate" hreflang="en" href="https://www.kasiadent.pl/en/services/prosthetics">

<!-- https://www.kasiadent.pl/en/services/prosthetics -->
<link rel="canonical" href="https://www.kasiadent.pl/en/services/prosthetics">
<link rel="alternate" hreflang="pl" href="https://www.kasiadent.pl/uslugi/protetyka">
<link rel="alternate" hreflang="en" href="https://www.kasiadent.pl/en/services/prosthetics">
```
Nie dodajemy `x-default`. Strona bez odpowiednika (np. Blog bez tłumaczenia) nie ma żadnych znaczników hreflang.

## 7. Nagłówki, metadane, okruszki i linkowanie wewnętrzne

### 7.1 Nagłówki H1–H6
Jeden H1 na stronie, pochodzący z zatwierdzonej treści. Hierarchia bez przeskoków. Nagłówki opisują treść i nie służą do stylowania (`DESIGN.md`). Zatwierdzonych nagłówków nie zmieniamy pod kątem fraz (punkt 8.2).

### 7.2 Meta title i meta description
- **Końcowe meta title i meta description nie zostały zatwierdzone** i powstaną zbiorczo w osobnym etapie, po zatwierdzeniu wszystkich treści usług, struktury URL i docelowej mapy fraz. **Nie tworzymy ich w tym dokumencie.** Metadane z nagłówków plików treści są robocze (punkt 8.2).
- **[POTWIERDZONE]** Tytuł jest opisowy, unikalny, zwięzły, bez powtarzania słów i upychania fraz; Google może go przepisać ([title link](https://developers.google.com/search/docs/appearance/title-link)). Opis to krótkie, dokładne streszczenie, unikalne dla strony, bez list słów kluczowych ([snippet](https://developers.google.com/search/docs/appearance/snippet)). Limitu długości nie ma, a wynik jest skracany do szerokości urządzenia.
- **[PRAKTYKA]** „Reda" w tytule jeden raz; nazwa gabinetu na końcu; opis streszcza zatwierdzony zakres, bez ocen jakości, obietnic skuteczności i cen. Orientacyjna długość 50–60 znaków pochodzi z praktyki SEO, a nie z wymagań Google (**[HIPOTEZA]**).
- Proces: propozycja w układzie „obecne robocze, propozycja, uzasadnienie danymi", zatwierdzenie zbiorcze. Dotychczasowe dane Keyword Plannera wystarczają do przygotowania pierwszej propozycji.

### 7.3 Okruszki nawigacyjne, `/uslugi` i BreadcrumbList
`/uslugi` nie ma zatwierdzonego pliku treści i nie zakładamy go jako gotowej strony. **Nowej podstrony nie tworzymy bez zatwierdzenia.**
- **[POTWIERDZONE]** BreadcrumbList wymaga `itemListElement` z co najmniej dwoma pozycjami (`item`, `name`, `position`; ostatnia pozycja może nie mieć `item`). Okruszki mają odzwierciedlać typową ścieżkę użytkownika, **co jest rekomendacją Google, a nie wymogiem** ([Google](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb)). Strona o okruszkach nie wymaga wprost widocznego komponentu.
- **[POTWIERDZONE]** Ogólne wytyczne Google: znacznik ma być prawdziwym odzwierciedleniem treści strony i nie może opisywać treści niewidocznych dla czytelników ([wytyczne](https://developers.google.com/search/docs/appearance/structured-data/sd-policies)).
- **Wniosek [PRAKTYKA]:** widoczny komponent okruszków **nie jest uniwersalnym wymogiem technicznym Google**, a **każda podstrona nie musi mieć BreadcrumbList.** Znacznik stosujemy tylko wtedy, gdy odpowiada rzeczywistej nawigacji na stronie (blok okruszków lub inny element, w którym użytkownik widzi ścieżkę i może się nią poruszać). Gdy takiej nawigacji nie ma, znacznika nie dodajemy, i to jest poprawne rozwiązanie.

| | Wariant 1: strona przeglądu | Wariant 2: bez pośredniego „Usługi" | Wariant 3: bez znacznika |
|---|---|---|---|
| Ścieżka widoczna dla użytkownika | Start › Usługi › usługa | Start › usługa | brak okruszków |
| Znacznik BreadcrumbList | 3 pozycje (zgodne z widoczną ścieżką) | 2 pozycje (zgodne z widoczną ścieżką) | brak |
| Wymaga | zatwierdzonej strony `/uslugi` i `/en/services` oraz zatwierdzonego wyglądu okruszków | zatwierdzonego wyglądu okruszków; „Usługi" w menu musi mieć cel | – |
| Ryzyko | nowa podstrona wymaga zatwierdzonej treści | segment `/uslugi` w adresie bez strony nadrzędnej | brak (znacznik nie jest wymagany) |

- Widoczne okruszki to element interfejsu niewymieniony w `DESIGN.md`, więc ich wygląd wymaga osobnej decyzji. **Znacznik i widoczna nawigacja muszą być zgodne.** Wybór wariantu następuje podczas zatwierdzania struktury i projektu strony. Do czasu decyzji stosujemy wariant 3. Przykłady JSON-LD: punkt 9.5.

### 7.4 Linkowanie wewnętrzne
- Start linkuje do siedmiu usług (zatwierdzone kafelki), Pierwszej wizyty i Kontaktu. Strony usług linkują do Cennika (kotwice kategorii), Pierwszej wizyty i Kontaktu.
- Powiązania merytoryczne z zatwierdzonych tekstów: Endodoncja z Protetyką (odbudowa po leczeniu kanałowym) i RTG; Zachowawcza z RTG; Estetyczna z Protetyką (licówki, punkt 8.6); Dziecięca z Pierwszą wizytą i Profilaktyką (fluoryzacja).
- Opisowe teksty odnośników, bez „Reda" w każdym. Linki absolutne tylko do `https://www.kasiadent.pl`. Bez odnośników do treści, których nie ma.

## 8. Strategia słów kluczowych i lokalne SEO

### 8.1 Zasady
- Priorytet: lokalna widoczność gabinetu w Redzie dla siedmiu kategorii usług. Zakres usług jest zamknięty i wynika z zatwierdzonych plików treści (w tym bonding, licówki i usługi protetyczne). Strategia **nie dopisuje** zabiegów ani wariantów leczenia spoza tych materiałów.
- **Jedna główna intencja wyszukiwania = jedna docelowa podstrona.** Jedna podstrona może obsługiwać wiele powiązanych fraz (odmiany, synonimy, frazy pokrewne i drugorzędne intencje), o ile nie jest dla nich główną docelową stroną inna podstrona. Kanibalizacja zachodzi, gdy **dwie podstrony mają tę samą główną intencję**. Nie tworzymy osobnych podstron dla odmian słów kluczowych.
- Nie powtarzamy sztucznie słowa „Reda". „Dobry dentysta Reda" i „dobry stomatolog Reda" są zapytaniami do analizy i **nie upoważniają** do twierdzeń o jakości gabinetu (punkt 10).
- Nie obiecujemy pozycji w Google ani rekomendacji w odpowiedziach AI.

### 8.2 Zatwierdzone teksty i nagłówki a robocze metadane
- **Zatwierdzone** są teksty stron oraz ich nagłówki (H1–H6) z zatwierdzonych plików treści. Pozostają bez zmian (`CLAUDE.md`, punkt 1).
- **Robocze (niezatwierdzone) są metadane** `metaTitle` i `metaDescription` z nagłówków plików treści (pochodzą z dokumentu źródłowego). Służą wyłącznie jako materiał porównawczy. **Końcowe meta title i meta description nie zostały jeszcze zatwierdzone** i powstaną zbiorczo w późniejszym etapie (punkt 7.2).
- **Mapa słów kluczowych jest dokumentem analitycznym.** Nie jest zatwierdzonym tekstem, nagłówkiem, meta title ani meta description i **nie upoważnia do automatycznej zmiany żadnej treści.** Propozycje zmian zgłaszamy pojedynczo jako rekomendacje w `docs/REVIEW.md` (strona, element, obecne brzmienie, propozycja, uzasadnienie, status). Każda wymaga osobnego zatwierdzenia właściciela.
- **Stan fraz w zatwierdzonych tekstach** (obserwacja, bez propozycji zmian): „dentysta" jako rzeczownik nie występuje w treści żadnej podstrony. Nie występują także „plomba", „protezy zębowe", „korony zębowe", „dentysta dziecięcy", „stomatolog dziecięcy", „dentysta dla dzieci", „koło Redy". H1 Startu: „Gabinet stomatologiczny dr KASIA DENT w Redzie". Występują m.in. „w Redzie" na stronach usług, „leczenie kanałowe pod mikroskopem", „licówki", „bonding", „wybielanie zębów", „mosty protetyczne", „skaling", „piaskowanie", „higienizacja", „rentgen" (tylko Diagnostyka RTG).
- **Robocze meta title a fraza „dentysta Reda":** fraza „dentysta Reda" występuje obecnie tylko w roboczych meta title O mnie i Kontakt. Stomatologia dziecięca ma w roboczym meta title „Dentysta dla dzieci Reda", czyli inną frazę.
- Brak frazy w tekście nie oznacza zmiany. Dwie drogi: pozostawić tekst i polegać na synonimach oraz sygnałach lokalnych albo zgłosić osobną propozycję zmiany do zatwierdzenia.

### 8.3 Wyniki badania Google Keyword Planner z 13.11.2026 (podsumowanie)
**Okres:** listopad 2025 – październik 2026.
**Obszar lokalny: Reda, województwo pomorskie, Polska.** Zasięg zadeklarowany przez właściciela w ustawieniach ostatnich badań Google Keyword Planner. **Pliki CSV nie zawierają potwierdzenia lokalizacji** (brak jej w metadanych). Zasięg „Polska" dla plików A–D ustalono na podstawie przebiegu analizy.

**Zasady odczytu:**
- Wartości są **zaokrąglone do progów** (0, 50, 500, 5 000, 50 000). Nie sumujemy wariantów fraz. Dla tak małego obszaru jak Reda dane lokalne mają najniższą rozdzielczość (próg „50").
- **Brak wolumenu nie oznacza zerowego zainteresowania.** „Brak wolumenu" znaczy, że Google nie podał danych, a „0" to jawna wartość.
- Kolumna „Konkurencja" to konkurencja reklamowa, a nie trudność SEO. Stawek reklamowych nie używamy.
- Trendy przy wartościach 50 i 500 są nieczytelne, a kolumny miesięczne i organiczne w eksportach są puste. Trendy bierzemy z Search Console.

| Fraza | Polska | Lokalny | Uwagi |
|---|---|---|---|
| dentysta Reda | 500 | 500 | |
| dentysta w Redzie | 500 | 500 | |
| reda dentysta | 500 | 50 | wariant z odwróconym szykiem; wartości potwierdzone w eksportach KP-2026-11-13-A i KP-2026-11-13-F |
| stomatolog Reda | 500 | 50 | |
| gabinet stomatologiczny Reda | 50 | 50 | |
| dentysta Reda cennik | 50 | 50 | |
| stomatolog dziecięcy Reda | 50 | 50 | |
| leczenie kanałowe Reda | 50 | **0** | |
| skaling Reda; piaskowanie zębów Reda | 50; 50 | nie badano | |
| dobry dentysta Reda | brak wolumenu | brak wolumenu | |
| dobry stomatolog Reda; stomatolog w Redzie; prywatny dentysta Reda | brak wolumenu | nie badano | |
| leczenie kanałowe pod mikroskopem Reda; protetyka Reda; protezy Reda; licówki Reda; bonding Reda | brak wolumenu | brak wolumenu | |
| endodoncja Reda; protezy zębowe Reda; korony zębowe Reda; stomatologia estetyczna Reda; leczenie próchnicy Reda; plomba Reda; higienizacja Reda; stomatologia dziecięca Reda; dentysta dla dzieci Reda | brak wolumenu | nie badano | |
| **nie badano w żadnym zasięgu:** leczenie zębów Reda; stomatologia zachowawcza Reda; mosty protetyczne Reda; wybielanie zębów Reda; profilaktyka stomatologiczna Reda; higienizacja zębów Reda; dentysta dziecięcy Reda; RTG zębów Reda; rentgen zębów Reda | – | – | rekomendowane dobadanie (punkt 8.8) |

**Frazy bez nazwy miasta (listy pomysłów; Polska / lokalny):** dentysta 50 000 / 50; leczenie kanałowe 50 000 / 50; leczenie kanałowe pod mikroskopem 5 000 / 50; endodoncja 5 000 / 50; protetyka 5 000 / 50; protezy zębowe 5 000 / 50; korony zębowe 5 000 / 50; mosty protetyczne 500 / 50; licówki 5 000 / 50; bonding 50 000 / 50; wybielanie zębów 50 000 / 50; stomatologia estetyczna 5 000 / 50; stomatologia zachowawcza 5 000 / 50; higienizacja zębów 50 000 / 50; dentysta dziecięcy 5 000 / 50. Dla części fraz (np. skaling, piaskowanie zębów, RTG zębów) w tych listach nie ma wierszy.

**Wnioski (ostrożne):** tylko ogólne frazy z „Reda" mają mierzalny wolumen. Frazy usługowe z „Reda" są rzadkie lub bez danych. Krajowe zainteresowanie tematami usług jest duże i nie jest popytem na gabinet w Redzie. Rozdzielczość danych lokalnych jest zbyt niska, by różnicować strony usług. Frazy o NFZ (gabinet jest wyłącznie prywatny), nazwiska innych lekarzy oraz ulice i sklepy z okolicy są poza strategią.

### 8.4 Mapa intencji i fraz (zatwierdzona; zmiany treści, nagłówków i metadanych tylko za osobną zgodą)
„(+)" oznacza frazy dodane w analizie.

| Podstrona (adres PL) | Główna intencja wyszukiwania | Powiązane frazy | KP (Polska / lokalny) | P |
|---|---|---|---|---|
| Start `/` | znaleźć dentystę lub gabinet w Redzie | dentysta Reda; stomatolog Reda; dentysta w Redzie; (+) gabinet stomatologiczny Reda; (+) prywatny dentysta Reda | 500/500; 500/50; 500/500; 50/50; brak/nie badano | **P1** |
| Stomatologia zachowawcza `/uslugi/stomatologia-zachowawcza` | leczenie zębów i próchnicy | leczenie zębów Reda; leczenie próchnicy Reda; plomba Reda; (+) stomatologia zachowawcza Reda | nie badano; brak; brak; nie badano | P2 |
| Endodoncja `/uslugi/leczenie-kanalowe-pod-mikroskopem` | leczenie kanałowe, także pod mikroskopem | leczenie kanałowe Reda; leczenie kanałowe pod mikroskopem Reda; (+) endodoncja Reda | 50/0; brak/brak; brak/nie badano | **P1** |
| Protetyka `/uslugi/protetyka` | uzupełnienia protetyczne: korony, mosty, protezy | protetyka Reda; protezy zębowe Reda; korony zębowe Reda; (+) mosty protetyczne Reda; (+) protezy Reda | brak/brak; brak/nie badano; brak/nie badano; nie badano; brak/brak | P2 |
| Stomatologia estetyczna `/uslugi/stomatologia-estetyczna` | poprawa estetyki uśmiechu (licówki, bonding, wybielanie) | **licówki Reda** (przede wszystkim); bonding Reda; wybielanie zębów Reda; (+) stomatologia estetyczna Reda | brak/brak; brak/brak; nie badano; brak/nie badano | **P1** |
| Profilaktyka `/uslugi/profilaktyka` | profilaktyka i higienizacja | higienizacja zębów Reda; skaling Reda; piaskowanie zębów Reda; (+) profilaktyka stomatologiczna Reda | nie badano; 50/nie badano; 50/nie badano; nie badano | P2 |
| Stomatologia dziecięca `/uslugi/stomatologia-dziecieca` | dentysta dla dzieci | dentysta dziecięcy Reda; stomatolog dziecięcy Reda; (+) dentysta dla dzieci Reda; (+) stomatologia dziecięca Reda | nie badano; 50/50; brak/nie badano; brak/nie badano | P2 |
| Diagnostyka RTG `/uslugi/diagnostyka-rtg` | RTG zębów (zatwierdzony zakres: cyfrowe, punktowe zdjęcia na miejscu) | RTG zębów Reda; rentgen zębów Reda | nie badano; nie badano | **P2** |
| Cennik `/cennik` | koszt usług stomatologicznych | (+) dentysta Reda cennik; (+) cennik stomatologiczny Reda | 50/50 | P2 |
| Kontakt `/kontakt` | adres, dojazd, kontakt z gabinetem | (+) dentysta Reda kontakt; gabinet stomatologiczny Reda adres | nie badano | P2 |
| Pierwsza wizyta `/pierwsza-wizyta` | jak wygląda pierwsza wizyta | (+) pierwsza wizyta u dentysty; wizyta adaptacyjna dziecka | nie badano | P3 |
| O mnie (adres DO ZATWIERDZENIA) | lekarz i marka | (+) Katarzyna Dostatnia dentysta Reda | nie badano | P3 |
| Blog, strona przeglądu `/uslugi` | po zatwierdzeniu planu treści | tematy tylko z zatwierdzonych materiałów | – | P3 |

Uwagi: Diagnostyka RTG nie rozszerza zatwierdzonego zakresu (tomografia CBCT to współpraca z zewnętrzną pracownią i nie jest celem fraz). Rekomendacja po dobadaniu: wybór frazy dominującej dla stomatologii dziecięcej („dentysta dziecięcy" czy „stomatolog dziecięcy"). Nie celujemy w frazy spoza zakresu (NFZ, nazwiska innych lekarzy, „endodonta", „protetyk", tomografia).

### 8.5 Priorytety P1/P2/P3
Priorytet określa kolejność prac i weryfikacji, a nie wartość usługi. Po publikacji zmieniamy go na podstawie danych z Search Console.
- **P1 Start:** jedyne frazy z Redą z mierzalnym (zaokrąglonym) wolumenem; wejście do serwisu; zatwierdzony H1 z „gabinet stomatologiczny … w Redzie".
- **P1 Endodoncja:** wyróżnik gabinetu w zatwierdzonych materiałach (specjalne zainteresowanie lekarza, mikroskop, koferdam) i duże krajowe zainteresowanie bez miasta. Lokalnie „leczenie kanałowe Reda" to 50 (Polska) i 0 (lokalny), więc strategia opiera się na autorytecie tematycznym i sygnałach lokalnych.
- **P1 Stomatologia estetyczna:** strona-właściciel „licówki Reda" oraz bondingu i wybielania. Krajowe zainteresowanie wysokie, frazy z Redą bez danych (nie zero).
- **P2 Profilaktyka, Stomatologia dziecięca, Protetyka, Stomatologia zachowawcza:** zakres z zatwierdzonych materiałów, frazy z Redą rzadkie lub bez danych, część nie była badana.
- **P2 Diagnostyka RTG:** frazy nie były badane w żadnym zasięgu, a usługa wspiera Zachowawczą, Endodoncję i Pierwszą wizytę. P2 do czasu zebrania dokładniejszych danych. Zakres bez zmian.
- **P2 Cennik i Kontakt:** „dentysta Reda cennik" 50/50 oraz zapytania nawigacyjne i sygnały lokalne (NAP, Profil Firmy).
- **P3 Pierwsza wizyta, O mnie, Blog, `/uslugi`:** treści informacyjne lub marki, bez danych. Rewizja po danych z Search Console.

### 8.6 Licówki
- **„Licówki Reda" przypisujemy przede wszystkim do Stomatologii estetycznej.** Nie usuwamy ani nie zmieniamy zatwierdzonych opisów licówek, także w Protetyce, która może wspierać frazę jako strona drugorzędna.
- Linkowanie: Protetyka linkuje do Stomatologii estetycznej w kontekście licówek (opisowy odnośnik), a Stomatologia estetyczna do Protetyki w kontekście koron i mostów. Identyczny akapit o licówkach na obu stronach pozostaje bez zmian. W Cenniku licówka porcelanowa jest w kategorii Protetyka i nie zmieniamy tego.

### 8.7 SEO lokalne i AI Search
Wymagania dla Google Search i Google Maps, ChatGPT Search, Gemini, Google AI Overviews i AI Mode, Claude, Perplexity i Microsoft Copilot oraz pozostałych asystentów opisuje punkt 11. Audyt AI obejmuje naturalne pytania pacjentów o dentystę w Redzie i usługi gabinetu (45 pytań, punkt 11.9). Nie obiecujemy pozycji ani rekomendacji.

### 8.8 Google Keyword Planner
- Konto Google Ads skonfigurowane przez właściciela, dostęp do Keyword Plannera bez uruchamiania kampanii. **Kampanii nie uruchamiamy i nie planujemy kosztów.**
- **Oryginalne eksporty przechowujemy poza publicznym repozytorium** (repozytorium jest publiczne): prywatny folder poza katalogiem projektu z kopią zapasową, prywatny dysk właściciela lub prywatne repozytorium (wybór: punkt 17.3). Oryginałów nie umieszczamy w żadnej gałęzi ani Pull Requeście. Dostęp Claude Code do takiego folderu następuje po wskazaniu ścieżki przez właściciela i wyłącznie do odczytu.
- **W dokumencie zostają:** metodologia, podsumowanie wyników (8.3) i rejestr badań, **bez danych identyfikujących konto Google Ads** (bez identyfikatora konta, e-maila, nazwy konta, planu lub kampanii, ścieżek lokalnych i zrzutów interfejsu). W pobranych plikach nie znaleziono takich danych.
- **Rejestr badań** (oryginały poza repozytorium; zasięg wg deklaracji właściciela i przebiegu analizy, bo CSV go nie zawierają):

| ID | Data eksportu | Okres | Zasięg | Zawartość | Wiersze | SHA-256 oryginału |
|---|---|---|---|---|---|---|
| KP-2026-11-13-A | 13.11.2026 | 11.2025–10.2026 | Polska (wg przebiegu analizy) | frazy z „Reda" (ogólne i warianty) | 34 | `404ba15ba20500e70bcf7e1de5da7573c183779671182af3f938d173ed52ba93` |
| KP-2026-11-13-B | 13.11.2026 | j.w. | Polska (wg przebiegu analizy) | endodoncja, protetyka, estetyka z „Reda" | 9 | `53523e9e17db76467d9bc39f723069839f42a56c8c393f2fce954880683ea02a` |
| KP-2026-11-13-C | 13.11.2026 | j.w. | Polska (wg przebiegu analizy) | profilaktyka, dzieci, zachowawcza z „Reda" | 8 | `632c23ff2daac99b4dd1869f589ba5ed5c627a67db342a5bb36d6fb839e0127d` |
| KP-2026-11-13-D | 13.11.2026 | j.w. | Polska (wg przebiegu analizy) | lista pomysłów (frazy bez miasta) | 3736 | `824dfde95d707b2c2861af3bfb5bf99f52e1656a025b298c8fb96bdf41d83ec9` |
| KP-2026-11-13-E | 13.11.2026 | j.w. | Reda, woj. pomorskie, Polska (deklarowany) | lista pomysłów (frazy bez miasta) | 3736 | `0b51e5ba7255276b9ad3c99eed8ec9de4af31a130538175f6b9c1fd6a3dd1ac7` |
| KP-2026-11-13-F | 13.11.2026 | j.w. | Reda, woj. pomorskie, Polska (deklarowany) | frazy z „Reda" | 37 | `fb4f2140cb2f77e99c67db95b2620a16806f24717a93cb9177f83b5c0cfc665e` |

Przy przyszłych eksportach zapis zasięgu, języka i sieci robimy w rejestrze w chwili eksportu.
- **Porównywanie Polski i obszaru lokalnego:** parami eksportów z identyczną listą fraz i okresem, jakościowo (progi zaokrąglenia), bez współczynników i bez sum wariantów.
- **Dotychczasowe dane (badanie z 13.11.2026) są wystarczającą podstawą do przygotowania pierwszej propozycji meta title i meta description.** Dalsze badania są **rekomendacją, a nie warunkiem** przejścia do etapu metadanych.
- **Rekomendowane (WYMAGA DZIAŁANIA WŁAŚCICIELA, jeśli właściciel zdecyduje):** dobadanie fraz z tabeli „nie badano" (w tym RTG zębów Reda i rentgen zębów Reda), uzupełnienie zasięgu lokalnego oraz frazy EN po zatwierdzeniu faktów.
- **Ponowne badania (rekomendacja):** przy istotnej zmianie treści lub struktury (nowa podstrona, zmiana H1, nowa usługa), 3 miesiące po publikacji i raz w roku (okno 12 miesięcy). Każde badanie wpisujemy do rejestru.
- Po publikacji dane z Search Console mają pierwszeństwo przed estymacjami z Keyword Plannera.

## 9. Dane strukturalne (Schema.org / JSON-LD)

### 9.1 Zasady
- Poprawność znaczników oceniamy według Schema.org, wymagania Google dla wyników rozszerzonych osobno, a wpływ na wyszukiwarki AI jako hipotezę (punkt 9.2). **Poprawny znacznik nie gwarantuje specjalnego wyglądu wyniku.** **[POTWIERDZONE]** Google nie gwarantuje wyświetlenia funkcji opartych na danych strukturalnych, a znaczniki łamiące zasady mogą skutkować działaniem ręcznym ([Organization](https://developers.google.com/search/docs/appearance/structured-data/organization)).
- **Wszystkie dane muszą odpowiadać zatwierdzonym treściom gabinetu.** Nie dodajemy niepotwierdzonych kwalifikacji, specjalizacji, opinii, godzin, cen, współrzędnych ani usług.
- Reprezentacja **serwisu** (`WebSite`, `Dentist`, `Person`) jest jedna dla wszystkich wersji językowych, a reprezentacja **stron** (`WebPage`) jest odrębna dla każdej wersji językowej. JSON-LD zapisany statycznie w HTML, ze stabilnymi identyfikatorami `@id` opartymi na `https://www.kasiadent.pl`.
- **Zasada dotycząca placeholderów.** Placeholdery typu `[DO ZATWIERDZENIA …]` i `[DO POTWIERDZENIA …]` służą **wyłącznie dokumentacji**. **Podczas implementacji niezatwierdzone właściwości należy pominąć w całości**, a nie publikować w produkcyjnym JSON-LD tekstów zastępczych ani pustych wartości. Węzeł lub właściwość pojawia się w znaczniku dopiero po zatwierdzeniu danych i musi zgadzać się z widoczną treścią. **Niezatwierdzone pola opcjonalne pomijamy.**
- **`WebPage.name`** może pochodzić z zatwierdzonej nazwy strony (np. zatwierdzony nagłówek lub nazwa usługi) i nie zależy od końcowego meta title. W przykładach 9.5 zapis `[zatwierdzona nazwa strony]` oznacza miejsce na taką nazwę. Jeśli zatwierdzonej nazwy brak, właściwość `name` pomijamy.
- Dane źródłowe: NAP z `kontakt_pl.md`, fakty o lekarzu z `o-mnie_pl.md`. Użycie każdego pola: DO ZATWIERDZENIA (punkt 9.6).

### 9.2 Trzy poziomy oceny (stan na 13.11.2026)
| Typ | 1. Poprawność w Schema.org | 2. Wymagania Google dla wyników rozszerzonych | 3. Wpływ na wyszukiwarki AI |
|---|---|---|---|
| `Dentist` | typ istnieje; nadrzędne: `LocalBusiness`, `MedicalBusiness`, `MedicalOrganization`. Poprawne właściwości m.in.: `name`, `url`, `address`, `telephone`, `email`, `openingHoursSpecification`, `geo`, `image`, `logo`, `sameAs`, `areaServed`, `knowsLanguage`, `hasMap`, `paymentAccepted`; niepoprawne: `availableService` | **[POTWIERDZONE]** funkcja „Local business": wymagane `name` i `address`; zalecane m.in. `telephone`, `url`, `openingHoursSpecification`, `geo`, `image` ([Google](https://developers.google.com/search/docs/appearance/structured-data/local-business)) | **[HIPOTEZA]** Google: dane strukturalne nie są wymagane dla funkcji AI. Microsoft: **[ŹRÓDŁO POŚREDNIE]**. Pozostali: brak oficjalnych informacji |
| `Person` | poprawne: `name`, `jobTitle`, `alumniOf`, `knowsLanguage`, `worksFor`, `url`, `sameAs`, `image`, `honorificPrefix` | brak osobnej funkcji wyników dla lekarza w odczytanej galerii. `Person` jest używany jako autor w Article | **[HIPOTEZA]** |
| `Service` | poprawne: `name`, `provider`, `areaServed`, `description`, `serviceType`, `url`, `offers`; **niepoprawne: `inLanguage`** | `Service` nie występuje w galerii obsługiwanych funkcji ([galeria](https://developers.google.com/search/docs/appearance/structured-data/search-gallery)) | **[HIPOTEZA]** wartość semantyczna |
| `WebSite` | poprawne: `name`, `url`, `publisher`, `alternateName`, `inLanguage` (strona Schema.org nie określa, czy dozwolonych jest wiele wartości, więc `inLanguage` w `WebSite` nie stosujemy) | nie występuje w odczytanej galerii jako osobna funkcja; wsparcie nazwy serwisu nie było weryfikowane w tej analizie | **[HIPOTEZA]** |
| `WebPage` | poprawne: `inLanguage`, `isPartOf`, `about`, `mainEntity`, `breadcrumb`, `url`, `name` (`inLanguage` dziedziczone po `CreativeWork`) | brak osobnej funkcji | **[HIPOTEZA]** |
| `BreadcrumbList` / `ListItem` | `BreadcrumbList`: `itemListElement`, `name`; `ListItem`: `position`, `name`, `item` | **[POTWIERDZONE]** „Breadcrumb" w galerii; wymaga co najmniej dwóch pozycji | **[HIPOTEZA]** |
| `Organization` | opcjonalnie (punkt 9.4) | **[POTWIERDZONE]** w galerii; brak wymaganych właściwości; logo min. 112×112 px, czytelne na białym tle | **[HIPOTEZA]** |
| `BlogPosting` | typ istnieje (w hierarchii Schema.org pod `SocialMediaPosting`/`Article`); poprawne: `headline`, `datePublished`, `dateModified`, `author`, `image`, `inLanguage`, `mainEntityOfPage` | **[POTWIERDZONE]** obsługiwany jako Article; brak wymaganych właściwości; zalecane `author` (osobno każdy autor, `Person`, nazwa bez tytułów, z `url` lub `sameAs`), `dateModified`, `datePublished`, `headline`, `image` ([Google](https://developers.google.com/search/docs/appearance/structured-data/article)) | **[HIPOTEZA]** |

Schema.org: wersja robocza 30.1 (odczyt 13.11.2026).

### 9.3 Czego nie stosujemy
- `aggregateRating` i `review` dla własnego gabinetu (**[POTWIERDZONE]** w dokumentacji Google zalecane dla serwisów oceniających *inne* firmy).
- `FAQPage` jako sposób na wyniki rozszerzone (**[POTWIERDZONE]** nie występuje w galerii). Sekcje pytań i odpowiedzi mogą istnieć jako zwykła treść.
- `inLanguage` w typie `Service` i `WebSite`, `availableService` w `Dentist`, `offers` i `priceRange` (ceny są orientacyjne), `medicalSpecialty` i `MedicalProcedure` bez zatwierdzenia, `potentialAction` rezerwacji (rezerwacja online IQDental jest planowana na przyszłość, `DESIGN.md`).
- Znaczników opisujących treści, których nie ma na stronie. `BreadcrumbList` bez rzeczywistej nawigacji (punkt 7.3).

### 9.4 Identyfikatory `@id`
Typy: `Dentist`, `Person`, `Service`, `BreadcrumbList` (po decyzji z punktu 7.3), `WebSite` i ewentualnie `Organization` (nadmiarowy, gdy `Dentist` jest podmiotem gabinetu), `BlogPosting` na późniejszym etapie.

| Podmiot | `@id` | Zasięg |
|---|---|---|
| Serwis (`WebSite`) | `https://www.kasiadent.pl/#website` | **jeden dla całego serwisu** (PL i EN), bez `inLanguage` |
| Gabinet (`Dentist`) | `https://www.kasiadent.pl/#gabinet` | jeden |
| Lekarz (`Person`) | `https://www.kasiadent.pl/#lekarz` | jeden |
| Strona (`WebPage`) | `<adres kanoniczny strony>#webpage` | osobny dla każdej wersji językowej, z `inLanguage` |
| Usługa (`Service`) | `<adres kanoniczny strony usługi>#service` | osobny dla każdej wersji językowej (opis tego, co jest na stronie) |
| Okruszki (`BreadcrumbList`) | `<adres kanoniczny strony>#breadcrumb` | tylko gdy spełnione są warunki z punktu 7.3 |

- `url` w `WebSite` zawsze wskazuje korzeń serwisu `https://www.kasiadent.pl/`, także w znacznikach stron EN.
- Powiązanie wersji językowych sygnalizuje hreflang (punkt 6). Właściwości `workTranslation` i `translationOfWork` są poprawne w Schema.org dla `CreativeWork`, ale Google nie opisuje ich użycia, więc ich nie stosujemy.
- **[HIPOTEZA]** Nie każdy odbiorca musi rozwiązywać odwołania `@id` między stronami. Dlatego każda strona zawiera pełny węzeł `WebSite` (identyczny na wszystkich stronach) i co najmniej minimalny węzeł `Dentist` (`@id`, `name`, `url`).

### 9.5 Przykłady JSON-LD (placeholdery tylko w dokumentacji)
Wartości `[DO ZATWIERDZENIA …]`, `[DO POTWIERDZENIA …]` i `[zatwierdzona nazwa strony]` **nie trafiają do implementacji**. Niezatwierdzone właściwości pomijamy w całości (zasada z punktu 9.1).

**Strona główna PL:**
```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebSite",
      "@id": "https://www.kasiadent.pl/#website",
      "url": "https://www.kasiadent.pl/",
      "name": "dr KASIA DENT",
      "publisher": { "@id": "https://www.kasiadent.pl/#gabinet" }
    },
    {
      "@type": "WebPage",
      "@id": "https://www.kasiadent.pl/#webpage",
      "url": "https://www.kasiadent.pl/",
      "name": "[zatwierdzona nazwa strony]",
      "inLanguage": "pl",
      "isPartOf": { "@id": "https://www.kasiadent.pl/#website" },
      "about": { "@id": "https://www.kasiadent.pl/#gabinet" }
    },
    {
      "@type": "Dentist",
      "@id": "https://www.kasiadent.pl/#gabinet",
      "name": "dr KASIA DENT",
      "url": "https://www.kasiadent.pl/",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "postalCode": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "addressLocality": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "addressCountry": "PL"
      },
      "telephone": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
      "email": "[DO ZATWIERDZENIA – rozbieżność w materiałach]",
      "openingHoursSpecification": "[DO ZATWIERDZENIA – dni tygodnia i godziny]",
      "geo": "[DO ZATWIERDZENIA – współrzędne]",
      "logo": "[DO ZATWIERDZENIA – adres zatwierdzonego pliku logo]",
      "image": "[DO ZATWIERDZENIA – zatwierdzone zdjęcie]",
      "areaServed": "[DO ZATWIERDZENIA]",
      "sameAs": ["[DO ZATWIERDZENIA – zatwierdzone profile]"]
    },
    {
      "@type": "Person",
      "@id": "https://www.kasiadent.pl/#lekarz",
      "name": "Katarzyna Dostatnia",
      "honorificPrefix": "[DO ZATWIERDZENIA – wg zatwierdzonego zapisu]",
      "jobTitle": "[DO ZATWIERDZENIA – wg opisu O mnie]",
      "worksFor": { "@id": "https://www.kasiadent.pl/#gabinet" },
      "knowsLanguage": "[DO POTWIERDZENIA – języki konsultacji lekarza]",
      "alumniOf": "[DO ZATWIERDZENIA – wg opisu O mnie]",
      "url": "[DO ZATWIERDZENIA – adres strony O mnie]"
    }
  ]
}
```
**Strona główna EN** (ten sam `WebSite` i te same `@id` gabinetu i lekarza; odrębne `WebPage`):
```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebSite",
      "@id": "https://www.kasiadent.pl/#website",
      "url": "https://www.kasiadent.pl/",
      "name": "dr KASIA DENT",
      "publisher": { "@id": "https://www.kasiadent.pl/#gabinet" }
    },
    {
      "@type": "WebPage",
      "@id": "https://www.kasiadent.pl/en/#webpage",
      "url": "https://www.kasiadent.pl/en/",
      "name": "[zatwierdzona nazwa strony]",
      "inLanguage": "en",
      "isPartOf": { "@id": "https://www.kasiadent.pl/#website" },
      "about": { "@id": "https://www.kasiadent.pl/#gabinet" }
    },
    {
      "@type": "Dentist",
      "@id": "https://www.kasiadent.pl/#gabinet",
      "name": "dr KASIA DENT",
      "url": "https://www.kasiadent.pl/en/",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "postalCode": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "addressLocality": "[DO ZATWIERDZENIA – z kontakt_pl.md]",
        "addressCountry": "PL"
      },
      "telephone": "[DO ZATWIERDZENIA – z kontakt_pl.md]"
    },
    {
      "@type": "Person",
      "@id": "https://www.kasiadent.pl/#lekarz",
      "name": "Katarzyna Dostatnia",
      "worksFor": { "@id": "https://www.kasiadent.pl/#gabinet" },
      "knowsLanguage": "[DO POTWIERDZENIA – języki konsultacji lekarza]"
    }
  ]
}
```
(Adres w węźle `Dentist` na stronie EN pochodzi z tego samego zatwierdzonego źródła co na stronie PL. Właściwość `url` w `Dentist` na stronie EN wskazuje wersję EN strony głównej tylko wtedy, gdy właściciel tak zdecyduje; w przeciwnym razie pozostaje `https://www.kasiadent.pl/`, co jest DO ZATWIERDZENIA.)

**Podstrona usługi PL (Protetyka):**
```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "WebSite", "@id": "https://www.kasiadent.pl/#website",
      "url": "https://www.kasiadent.pl/", "name": "dr KASIA DENT" },
    { "@type": "Dentist", "@id": "https://www.kasiadent.pl/#gabinet",
      "name": "dr KASIA DENT", "url": "https://www.kasiadent.pl/" },
    {
      "@type": "WebPage",
      "@id": "https://www.kasiadent.pl/uslugi/protetyka#webpage",
      "url": "https://www.kasiadent.pl/uslugi/protetyka",
      "name": "[zatwierdzona nazwa strony]",
      "inLanguage": "pl",
      "isPartOf": { "@id": "https://www.kasiadent.pl/#website" },
      "mainEntity": { "@id": "https://www.kasiadent.pl/uslugi/protetyka#service" }
    },
    {
      "@type": "Service",
      "@id": "https://www.kasiadent.pl/uslugi/protetyka#service",
      "name": "Protetyka",
      "url": "https://www.kasiadent.pl/uslugi/protetyka",
      "provider": { "@id": "https://www.kasiadent.pl/#gabinet" },
      "description": "[DO ZATWIERDZENIA – krótki opis zgodny z zatwierdzonym tekstem]",
      "areaServed": "[DO ZATWIERDZENIA]"
    }
  ]
}
```
**Podstrona usługi EN (adres `/en/services/prosthetics` jest przykładem ilustracyjnym):**
```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "WebSite", "@id": "https://www.kasiadent.pl/#website",
      "url": "https://www.kasiadent.pl/", "name": "dr KASIA DENT" },
    { "@type": "Dentist", "@id": "https://www.kasiadent.pl/#gabinet",
      "name": "dr KASIA DENT", "url": "https://www.kasiadent.pl/" },
    {
      "@type": "WebPage",
      "@id": "https://www.kasiadent.pl/en/services/prosthetics#webpage",
      "url": "https://www.kasiadent.pl/en/services/prosthetics",
      "name": "[zatwierdzona nazwa strony]",
      "inLanguage": "en",
      "isPartOf": { "@id": "https://www.kasiadent.pl/#website" },
      "mainEntity": { "@id": "https://www.kasiadent.pl/en/services/prosthetics#service" }
    },
    {
      "@type": "Service",
      "@id": "https://www.kasiadent.pl/en/services/prosthetics#service",
      "name": "[DO ZATWIERDZENIA – zatwierdzona angielska nazwa usługi]",
      "url": "https://www.kasiadent.pl/en/services/prosthetics",
      "provider": { "@id": "https://www.kasiadent.pl/#gabinet" },
      "description": "[DO ZATWIERDZENIA – opis zgodny z zatwierdzonym tekstem EN]"
    }
  ]
}
```
**Okruszki, wariant 1** (węzeł dodawany do grafu strony oraz właściwość `"breadcrumb": { "@id": "…#breadcrumb" }` w `WebPage`; tylko gdy widoczne okruszki są zatwierdzone):
```json
{
  "@type": "BreadcrumbList",
  "@id": "https://www.kasiadent.pl/uslugi/protetyka#breadcrumb",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Start", "item": "https://www.kasiadent.pl/" },
    { "@type": "ListItem", "position": 2, "name": "Usługi", "item": "https://www.kasiadent.pl/uslugi" },
    { "@type": "ListItem", "position": 3, "name": "Protetyka" }
  ]
}
```
**Okruszki, wariant 2:**
```json
{
  "@type": "BreadcrumbList",
  "@id": "https://www.kasiadent.pl/uslugi/protetyka#breadcrumb",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Start", "item": "https://www.kasiadent.pl/" },
    { "@type": "ListItem", "position": 2, "name": "Protetyka" }
  ]
}
```
**Okruszki, wariant 3:** brak węzła `BreadcrumbList` i brak właściwości `breadcrumb` w `WebPage`.
Walidacja przed publikacją: Rich Results Test (funkcje obsługiwane przez Google) i Schema Markup Validator (poprawność składni). Nazwa `Service` zgodna z zatwierdzoną nazwą usługi (źródło nazwy, nagłówek strony czy kafelek Startu: DO ZATWIERDZENIA).

### 9.6 Dane do potwierdzenia przed użyciem w znacznikach
Adres, telefon i e-mail z `kontakt_pl.md` (rozbieżność e-maila), dni tygodnia dla godzin 09:00–19:00, współrzędne `geo`, zatwierdzony plik logo, zdjęcia, obszar obsługi, profile `sameAs`, zapis honorific i stanowiska lekarza, `alumniOf` zgodnie z opisem O mnie, **`knowsLanguage` (języki konsultacji lekarza)**, opisy usług (zgodne z zatwierdzonymi tekstami), forma płatności z Kontaktu jeśli ma się pojawić w `paymentAccepted`, nazwy usług EN. Są to dane opcjonalne dla uruchomienia strony: niezatwierdzone pomijamy (punkt 9.1).

## 10. Wiarygodność, autorstwo i treści medyczne
### 10.1 Zasady Google
**[POTWIERDZONE]** Treści o zdrowiu wymagają wysokiej dokładności i zgodności z konsensusem ekspertów. Czytelnik powinien łatwo zobaczyć, kto jest autorem. Wymyślanie autorów, zdjęć generowanych przez AI lub fałszywych kwalifikacji jest wprowadzaniem w błąd. Przy użyciu automatyzacji lub AI ujawniamy, jak powstała treść. Nie zmieniamy dat, by strona wyglądała na nowszą ([Google](https://developers.google.com/search/docs/fundamentals/creating-helpful-content)).
### 10.2 Wymagania projektu
Każdy tekst medyczny: autor lub osoba zatwierdzająca (DO ZATWIERDZENIA), data publikacji i rzeczywistej aktualizacji, źródła, informacja, że treść nie zastępuje konsultacji (sformułowanie DO ZATWIERDZENIA). Bez gwarancji skuteczności, porównań z innymi gabinetami, zdjęć „przed i po" bez zgody i podstawy prawnej, wymyślonych opinii i statystyk.
### 10.3 Polskie wymagania prawne: wymagają osobnej weryfikacji
Wskazuję **obszary do sprawdzenia**, a nie wnioski prawne: informowanie o świadczeniach i reklama działalności leczniczej (przepisy o działalności leczniczej, zasady etyki lekarskiej i dentystycznej), obowiązkowe informacje o podmiocie i lekarzu na stronie, tajemnica lekarska i RODO (opinie, wizerunek), usługi drogą elektroniczną, polityka prywatności i cookies, informowanie o cenach i promocjach, ocena użytych sformułowań na stronie głównej. **DO ZATWIERDZENIA:** osoba weryfikująca i termin przed publikacją treści.

## 11. Indeksowanie i widoczność w wyszukiwarkach AI (AEO/GEO)

### 11.1 Zasady
- AEO i GEO to zastosowanie podstaw SEO i dobrych treści dla nowych powierzchni wyszukiwania. **Nie gwarantują** wzmianki, cytowania ani rekomendacji. Odpowiedzi AI są niedeterministyczne.
- **Rozdzielamy cztery role:** (1) indeksowanie przez tradycyjne wyszukiwarki, (2) crawlery wyszukiwania asystentów AI, (3) crawlery treningowe, (4) pobieranie treści na żądanie użytkownika. **Nie zakładamy**, że blokada treningu blokuje wyszukiwanie. **Wyjątek `Google-Extended`**, który obejmuje trening i uziemianie w Gemini Apps (dopuszczony decyzją właściciela, punkt 11.2a). Nie przypisujemy platformie mechanizmu, którego dostawca oficjalnie nie opisał.
- Google AI Overviews i AI Mode oraz Gemini są osobnymi powierzchniami. Treść tworzymy dla pacjentów, nie „dla AI". Bez osobnych wersji pod AI i bez dzielenia treści.

### 11.2 Role mechanizmów i polityka (zatwierdzona zasada)
| Rola | Roboty | Polityka |
|---|---|---|
| 1. Tradycyjne wyszukiwarki | `Googlebot`, `Bingbot` | dopuszczone (grupa `*`) |
| 2. Wyszukiwanie asystentów AI | `OAI-SearchBot`, `PerplexityBot`, `Claude-SearchBot`, `Meta-WebIndexer` | dopuszczone (grupa `*`) |
| 3. Trening | `GPTBot`, `ClaudeBot`, `Meta-ExternalAgent` | ograniczone (`Disallow: /`) |
| 3a. Trening i uziemianie (Google) | `Google-Extended` | **dopuszczony** (jawna grupa; świadomy wyjątek) |
| 4. Na żądanie użytkownika | `ChatGPT-User`, `Perplexity-User`, `Claude-User`, `Meta-ExternalFetcher`, `Google-Agent`, `Google-GeminiNotebook` | dopuszczone (grupa `*`); część ignoruje `robots.txt` |

### 11.2a Wyjątek: Google-Extended
- **[POTWIERDZONE]** Token `Google-Extended` dotyczy łącznie: (1) zastosowań **treningowych** (trenowanie przyszłych generacji modeli Gemini w Gemini Apps i Vertex AI) oraz (2) **uziemiania** odpowiedzi (dostarczania modelowi treści indeksu Google Search w momencie zapytania w Gemini Apps i Grounding with Google Search w Vertex AI). Nie ma własnego user-agenta i nie wpływa na Google Search ([Google](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers)).
- **Sam `Google-Extended` nie rozdziela treningu i uziemiania.** Nie można więc dopuścić uziemiania w Gemini Apps i jednocześnie zabronić treningu tym tokenem.
- **Dopuszczenie jest świadomie zatwierdzonym wyjątkiem** od zasady „ograniczamy trening tam, gdzie można te mechanizmy rozdzielić". Celem jest zwiększenie widoczności gabinetu w Gemini Apps.
- **[POTWIERDZONE]** Google informuje, że witryny jawnie dopuszczające `Google-Extended` kwalifikują się do pojawiania się w odpowiedziach i otrzymywania kliknięć przez uziemianie w Gemini Apps ([blog Google, 30.10.2026](https://developers.google.com/search/blog/2026/10/ai-training-control)). **Dopuszczenie nie gwarantuje cytowania ani rekomendowania gabinetu.**

### 11.3 Platformy (stan na 13.11.2026)
- **Google AI Overviews i AI Mode.** **[POTWIERDZONE]** Brak dodatkowych wymagań poza indeksowaniem i kwalifikacją do fragmentu; nie są potrzebne nowe pliki dla AI ani specjalne schema; spełnienie wymagań nie gwarantuje wyświetlenia; sterowanie: `nosnippet`, `data-nosnippet`, `max-snippet`, `noindex`; ruch w Search Console (typ „Web"), bez osobnego raportu AI ([AI features](https://developers.google.com/search/docs/appearance/ai-features)). `Google-Extended` jest tam wymieniony dla „innych systemów Google". `llms.txt` nie jest używany przez Search i nie pomaga ani nie szkodzi ([przewodnik](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)). Google zaleca Profil Firmy dla firm lokalnych (tamże).
- **Gemini (aplikacja, osobno).** **[POTWIERDZONE]** Część odpowiedzi jest oparta na wynikach wyszukiwania ([Gemini Apps Privacy Hub](https://support.google.com/gemini/answer/13594961)). Zasady `Google-Extended`: punkt 11.2a. Fetchery `Google-Agent` i `Google-GeminiNotebook` zasadniczo ignorują `robots.txt`. Który fetcher obsługuje adres wklejony w aplikacji Gemini: nie opisano. Kontrole dla właścicieli stron poza `Google-Extended` w Privacy Hub nie są opisane.
- **ChatGPT Search.** **[POTWIERDZONE]** `OAI-SearchBot` odpowiada za wyszukiwanie ChatGPT (`robots.txt` obowiązuje, zmiany do około 24 godzin); strona z wyłączonym robotem nie pojawi się w odpowiedziach wyszukiwania, ale może wystąpić jako link nawigacyjny; `GPTBot` (trening) i `ChatGPT-User` (użytkownik, `robots.txt` może nie obowiązywać; nie decyduje o kwalifikacji do wyszukiwania); OpenAI publikuje zakresy IP (`openai.com/searchbot.json` i podobne) ([OpenAI](https://developers.openai.com/api/docs/bots)). **[ŹRÓDŁO POŚREDNIE]** FAQ dla wydawców (odczyt zwrócił 403) według podsumowania wyszukiwarki wskazuje na wymóg przepuszczenia zakresów IP przez zaporę hosta, zachowanie `noindex` w ChatGPT Atlas i parametr `utm_source=chatgpt.com`. Czy wyszukiwanie ChatGPT korzysta z indeksu Bing: brak oficjalnych informacji. Schema i `llms.txt`: brak oficjalnych informacji.
- **Microsoft Copilot.** **[POTWIERDZONE]** Microsoft Copilot i Copilot Chat (wersje biznesowe) wysyłają generowane zapytania do usługi wyszukiwania Bing ([Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-365/copilot/manage-public-web-access)); dla konsumenckiego Copilota to **[HIPOTEZA]**. Sitemapy i `lastmod` jako sygnały (punkt 5.3). `NOARCHIVE` wyklucza treść z odpowiedzi czatu i trenowania, `NOCACHE` ogranicza do adresu, tytułu i fragmentu ([Bing 2023](https://blogs.bing.com/webmaster/september-2023/Announcing-new-options-for-webmasters-to-control-usage-of-their-content-in-Bing-Chat)). Nowe preferencje: punkt 11.5. Dane strukturalne: **[ŹRÓDŁO POŚREDNIE]** (wspierają uziemianie, nie gwarantują widoczności). Bing Places: **[HIPOTEZA]**.
- **Perplexity.** **[POTWIERDZONE]** `PerplexityBot` (wyniki, nie trening; zalecane dopuszczenie w `robots.txt` oraz zakresów IP: `perplexitybot.json`, `perplexity-user.json`), `Perplexity-User` (na żądanie, zasadniczo ignoruje `robots.txt`); zmiany do 24 godzin; Cloudflare Bot Fight Mode nie jest omijany regułami WAF ([Perplexity](https://docs.perplexity.ai/docs/resources/perplexity-crawlers)). **Dokumentacja nie stwierdza wprost, że `PerplexityBot` stosuje się do `robots.txt`** (wskazuje tylko tagi `robots.txt` do zarządzania nim), więc nie zakładamy tego jako potwierdzonego faktu. Schema, sitemapy i `llms.txt`: niewspomniane jako sterowanie dla właścicieli stron.
- **Claude (Anthropic).** **[POTWIERDZONE]** Wyszukiwanie Claude korzysta z partnerów wyszukiwania, którzy indeksują treści i przekazują wyniki; `noindex` wyklucza treść z odpowiedzi z użyciem wyszukiwania ([Anthropic](https://support.claude.com/en/articles/10684638-blocking-and-removing-content-from-claude)). Boty: `ClaudeBot` (trening), `Claude-User` (blokada może zmniejszyć widoczność w wyszukiwaniu użytkownika), `Claude-SearchBot` (blokada może zmniejszyć widoczność); wszystkie respektują `robots.txt`; lista IP: `claude.com/crawling/bots.json`; blokowanie po IP nie jest zalecane ([Anthropic](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler)). Narzędzie wyszukiwania w API nie podaje dostawcy wyszukiwania ani zasad `robots.txt` ([dokumentacja](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-search-tool)). Schema i `llms.txt`: brak oficjalnych informacji.
- **Meta AI.** **[POTWIERDZONE]** `Meta-WebIndexer` (wyszukiwanie Meta AI; dopuszczenie „pomaga cytować i linkować"), `Meta-ExternalAgent`, `Meta-ExternalFetcher` ([Meta](https://developers.facebook.com/documentation/sharing/webmasters/web-crawlers)). Dostępność Meta AI w Polsce: nie sprawdzano. Audyt opcjonalny.
- **Grok.** **[POTWIERDZONE]** Narzędzie `web_search` w API xAI wyszukuje i przegląda strony ([xAI](https://docs.x.ai/developers/tools/web-search)). W przeczytanej dokumentacji **brak** nazwy crawlera, user-agenta i zasad `robots.txt`. Brak działań specyficznych poza ogólnym SEO.

### 11.4 `llms.txt`
Google: Search z niego nie korzysta. Dla pozostałych platform (OpenAI, Microsoft, Perplexity, Anthropic, Meta, xAI) **nie znaleziono oficjalnych informacji**, że z niego korzystają. Brak informacji nie jest potwierdzeniem wsparcia ani jego braku. Opcjonalny eksperyment, **domyślnie nie tworzymy**.

### 11.5 Terminy i nowe mechanizmy (stan na 13.11.2026; źródła odczytane bezpośrednio 13.11.2026)
- **Microsoft (blog z 30.10.2026, [źródło](https://blogs.bing.com/search/2026/10/your-content-your-choice-clearer-preferences-for-training-and-grounding/)) [POTWIERDZONE]:** preferencje „AI Training" (`robots.txt`: `User-Agent: __usage_ai-training`; na poziomie strony także `<meta name="Bingbot" content="ai-training:disallow">` lub nagłówek `X-Robots-Tag: Bingbot: ai-training:disallow`, z pierwszeństwem przed `robots.txt`) i „AI Grounding" (tylko na poziomie strony: `<meta name="Bingbot" content="ai-grounding:disallow">` lub nagłówek `X-Robots-Tag: Bingbot: ai-grounding:disallow`; wartości `allow` (domyślna), `disallowextended`, `disallow`; brak ustawienia grounding w `robots.txt`). Terminy: **15.12.2026** (tymczasowe preferencje w Bing Webmaster Tools dla witryn używających NoArchive/NoCache), **1.02.2027** (Microsoft uwzględnia nowe preferencje podczas crawlowania), **1.03.2027** (po tej dacie NoArchive i NoCache nie są czytane jako preferencje), **30.09.2027** (wygasają tymczasowe preferencje). Ustawienia nie zmieniają kwalifikacji do wyników Bing, a „Allow" nie zastępuje blokady Bingbota w `robots.txt`. Trening i uziemianie mają domyślnie wartość Allow. Dla nowej strony bez tagów NoArchive/NoCache nie ma preferencji do migracji. Nie odczytano bezpośrednio powiązanego szkicu IETF z tego wpisu ani FAQ Bing Webmaster Tools.
- **Anthropic [POTWIERDZONE]:** od 30.10.2026 rozpoznaje maszynowo czytelny sygnał „no AI training", oparty na szkicu IETF, wdrażany „stopniowo i globalnie" (bez opisu składni na stronie pomocy; nazwana reguła `ClaudeBot` ma pierwszeństwo) ([Anthropic](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler)).
- **Google [POTWIERDZONE jako zamiar, nie jako data wdrożenia]:** zamierza obsługiwać wspólny sygnał (token `__usage_ai-training`) w 2027; **blog Google podaje „w 2027", a strona crawlerów Google „early 2027"**. Istniejące kontrole działają obok niego. Termin traktujemy jako zamiar, a nie datę. Blog nie podaje składni tokenu (podaje ją strona crawlerów). OpenAI, Perplexity i Meta nie wspominają o AIPREF w odczytanej dokumentacji.
- **AIPREF: wdrożenie odroczone.** Zatwierdzona decyzja: token `__usage_ai-training` nie jest częścią produkcyjnego `robots.txt`, ze względu na niejednoznaczną relację z jawnym `Allow` dla `Google-Extended`. Stan dokumentów **[POTWIERDZONE]** (odczyt 13.11.2026): grupa robocza IETF `aipref` jest aktywna, a jej dokumenty są szkicami: słownik (`draft-ietf-aipref-vocab-08`, z ostrzeżeniem „contents DO NOT REFLECT CONSENSUS"; kategorie `train-ai`, `ai-use`, `search`) i dokument o przekazywaniu preferencji (`draft-ietf-aipref-attach-05`, dyrektywa `Content-Usage` w `robots.txt` i nagłówek HTTP). Osobny szkic indywidualny (`draft-kelley-aipref-training-preference-signal-00`, 30.10.2026, „not endorsed by the IETF") definiuje pseudo-token `__usage_ai-training`, który opisują Microsoft i Google. Szkice odsyłają do siebie w różnych wersjach (np. `attach-05` cytuje `vocab-07`), co potwierdza ich nieustabilizowany stan. Blog Google z 30.10.2026 mówi o celu wdrożenia w 2027 i o tym, że istniejące kontrole firmowe działają obok nowego sygnału oraz że przy zakazie treningu i niejawnym `Google-Extended` Google planuje traktować go jak zablokowany. Nie opisuje wprost przypadku „jawny Allow dla `Google-Extended` i zakaz w sygnale". Do tego czasu jedynym ograniczeniem treningu są nazwane crawlery (`GPTBot`, `ClaudeBot`, `meta-externalagent`). Bez tokenu preferencja Microsoftu „AI Training" pozostaje domyślnie Allow.
- **Ponowna weryfikacja AIPREF** po ustabilizowaniu specyfikacji i polityk dostawców (przegląd kwartalny, punkt 12.4). Kryteria: status dokumentów IETF, opublikowanie przez Google składni i relacji z `Google-Extended`, wdrożenie przez Microsoft (1.02.2027) i inne platformy.
- Terminy i nazwy crawlerów weryfikujemy przy każdym kwartalnym przeglądzie. Strony pomocy Bing Webmaster Tools nie dały się odczytać automatycznie, więc składnię przyjęto z bloga Microsoftu.

### 11.6 Hipotezy i praktyki
- **[HIPOTEZA]** Wzorce blokowe odpowiedzi (40–60 lub 130–170 słów), przewaga cytowań z początku strony, korelacja wzmianek o marce z cytowaniami, wpływ świeżości, rola Bing Places oraz wyniki typu „GEO Readiness Score" to korelacje i heurystyki firm SEO i autorów narzędzi. Google wprost odradza dzielenie treści pod AI. Nie stanowią podstawy żadnych wymagań.
- **[PRAKTYKA]** Rzeczowe odpowiedzi na pytania pacjentów w zwykłej strukturze nagłówków (zgodnie z zatwierdzonymi tekstami); jednoznaczna tożsamość gabinetu i lekarza (spójna nazwa, `Dentist` i `Person` z tym samym `@id`, `sameAs` do zatwierdzonych profili, spójne NAP); treść w statycznym HTML; autorstwo, daty i źródła tekstów medycznych. Asystenci mogą błędnie podawać dane, więc NAP, usługi i godziny muszą być jednoznaczne w jednym zatwierdzonym źródle.

### 11.7 Zakres audytu AI
Google AI Overviews, Google AI Mode, Gemini, ChatGPT Search, Claude, Perplexity, Microsoft Copilot. Opcjonalnie Meta AI i Grok.

### 11.8 Metodologia audytu (bez automatyzacji płatnymi API)
- Lista pytań (11.9) zatwierdzona przez właściciela i stała. **Punkt odniesienia przed publikacją.** Każde pytanie **3–5 razy** na platformę, w osobnych sesjach. Tryb z wyszukiwaniem sieciowym, wyłączona personalizacja, udokumentowana lokalizacja i język. Zakładanie kont lub płatne plany wymagają zgody. Bez danych pacjentów w pytaniach. **Nie przeprowadzamy audytu teraz.**
- **Zapisujemy:** datę, platformę, tryb i wersję modelu (jeśli widoczna), pytanie, numer próby; czy wymieniono gabinet i lekarza; czy zacytowano adres strony; inne cytowane źródła; zgodność podanych danych z zatwierdzonym NAP i zakresem usług; obietnice skuteczności lub nieprawdziwe informacje.
- **Wynik:** odsetek wystąpień z liczbą prób (np. „3 z 5, n=5"), osobno dla pytań z nazwą gabinetu i bez niej. Nie jest gwarancją. Błędne informacje: najpierw sprawdzamy spójność danych w źródłach, a zgłoszenia do platform wymagają zgody.
- **Logi serwera** (jeśli hosting je udostępnia): obecność żądań `OAI-SearchBot`, `PerplexityBot`, `Claude-SearchBot`, `meta-webindexer`, `Bingbot`, `Googlebot`, weryfikowana po opublikowanych zakresach IP (OpenAI, Perplexity, Anthropic). Obecność crawlera nie oznacza cytowania.
- **Automatyzacja przez płatne API nie jest planowana.** Częstotliwość: audyt podstawowy po publikacji i potem co miesiąc, pełny co kwartał (DO ZATWIERDZENIA, punkt 17.3).

### 11.9 Pytania audytu
**Audyt podstawowy (13 pytań, okresowo):** 1 Dentysta Reda. 2 Stomatolog Reda. 32 dr KASIA DENT Reda. 10 Gdzie w Redzie zrobić leczenie kanałowe pod mikroskopem? 12 Licówki porcelanowe lub kompozytowe w Redzie. 11 Gdzie w Redzie zrobić bonding zębów? 21 Stomatolog dziecięcy w Redzie. 15 Protetyka w Redzie: korony, mosty, protezy. 18 Higienizacja zębów w Redzie (skaling i piaskowanie). 19 RTG zębów w Redzie. 34 Jakie usługi oferuje gabinet dr KASIA DENT? 35 Gdzie znajduje się gabinet dr KASIA DENT i jak się umówić? 6 Dentysta Reda cennik (po zatwierdzeniu cennika).

**Audyt pełny (45 pytań, okresowo, np. kwartalnie):**
- **A. Lokalne ogólne:** 1 Dentysta Reda. 2 Stomatolog Reda. 3 Gabinet stomatologiczny w Redzie. 4 Prywatny gabinet stomatologiczny w Redzie. 5 Gdzie w Redzie jest dentysta przyjmujący prywatnie? 6 Dentysta Reda cennik. 7 Endodonta w Redzie lub okolicy. 8 Czy w Redzie jest dentysta przyjmujący pacjentów anglojęzycznych? (po potwierdzeniu faktów).
- **B. Usługi lokalne:** 9 Leczenie kanałowe pod mikroskopem w Redzie. 10 Gdzie w Redzie zrobić leczenie kanałowe pod mikroskopem? 11 Gdzie w Redzie zrobić bonding zębów? 12 Licówki porcelanowe lub kompozytowe w Redzie. 13 Wybielanie zębów w Redzie. 14 Gabinet w Redzie: protetyka i stomatologia estetyczna. 15 Protetyka w Redzie: korony, mosty, protezy. 16 Protezy zębowe w Redzie. 17 Leczenie próchnicy w Redzie. 18 Higienizacja zębów w Redzie (skaling i piaskowanie). 19 RTG zębów w Redzie. 20 Czy w Redzie można zrobić RTG zęba na miejscu u dentysty?
- **C. Dzieci:** 21 Stomatolog dziecięcy w Redzie. 22 Dentysta dziecięcy w Redzie. 23 Dentysta dla dzieci w Redzie: od jakiego wieku zacząć wizyty? 24 Wizyta adaptacyjna dziecka u dentysty w Redzie.
- **D. Wiedza (czy treści są cytowane):** 25 Czym jest endodoncja mikroskopowa i kiedy się ją stosuje? 26 Czy leczenie kanałowe pod mikroskopem boli? 27 Jak wygląda pierwsza wizyta u dentysty? 28 Co obejmuje profilaktyka stomatologiczna? 29 Jakie są rodzaje uzupełnień protetycznych? 30 Czy RTG zębów jest bezpieczne? 31 Ile kosztuje leczenie kanałowe w Redzie? (test tego, co mówi AI).
- **E. Marka i dokładność (porównanie z zatwierdzonymi danymi):** 32 dr KASIA DENT Reda. 33 lek. dent. Katarzyna Dostatnia. 34 Jakie usługi oferuje gabinet dr KASIA DENT? 35 Gdzie znajduje się gabinet dr KASIA DENT i jak się umówić? 36 Jakie są godziny otwarcia gabinetu dr KASIA DENT? 37 Czy dr KASIA DENT w Redzie wykonuje leczenie kanałowe pod mikroskopem? 38 Czy dr KASIA DENT w Redzie wykonuje licówki i bonding? 39 Czy w gabinecie dr KASIA DENT przyjmują dzieci?
- **F. EN:** 40 Dentist in Reda, Poland. 41 Dental clinic dr KASIA DENT Reda. 42 Root canal treatment under a microscope near Reda, Poland. 43 Dental clinic in Reda: root canal under a microscope. 44 Veneers and bonding in Reda, Poland. 45 Dentist for children in Reda, Poland.

Pytania o ceny i godziny (6, 31, 36) wykonujemy po zatwierdzeniu cennika i godzin. Pytania nie zakładają obecności gabinetu w odpowiedziach.

## 12. Wydajność i audyt SEO

### 12.1 Core Web Vitals
- **[POTWIERDZONE]** Wartości „dobre" na 75. percentylu danych z rzeczywistych użytkowników, osobno dla telefonu i komputera: LCP ≤ 2,5 s, INP ≤ 200 ms, CLS ≤ 0,1 ([web.dev](https://web.dev/articles/vitals)).
- **[PRAKTYKA]** Nowa strona o małym ruchu może nie mieć danych terenowych. Do czasu ich pojawienia się korzystamy z pomiarów laboratoryjnych (Lighthouse, PageSpeed Insights) jako wskaźnika. Zgodnie z `CLAUDE.md` i `DESIGN.md`: statyczny HTML, minimum JS, brak zewnętrznych bibliotek i fontów, rezerwacja miejsca na obrazy, mobile-first.

### 12.2 Audyt przed publikacją
- **Domeny i przekierowania:** wszystkie przekierowania z punktu 3.2 działają jednym skokiem (301) i zachowują ścieżkę; certyfikaty poprawne dla czterech nazw; domena dodatkowa nie serwuje treści.
- **Środowisko i indeksowanie:** środowisko testowe chronione; `robots.txt` bez `Disallow: /`; canonical, hreflang i sitemapa wskazują `https://www.kasiadent.pl`; strona 404 zwraca 404; brak `noindex` z testów.
- **Treść i metadane:** treści i nagłówki identyczne z zatwierdzonymi; **ostateczne meta title i meta description zatwierdzone**, unikalne; jeden H1; dane NAP identyczne we wszystkich miejscach, rozbieżności z materiałów rozstrzygnięte; weryfikacja prawna zakończona.
- **Dane strukturalne i języki:** JSON-LD zgodny z widoczną treścią, **bez placeholderów i niezatwierdzonych właściwości**, walidacja; hreflang tylko dla opublikowanych par; tłumaczenia EN zatwierdzone przez gabinet (jeśli wersja EN jest publikowana).
- **Jakość:** WCAG 2.2 AA i klawiatura (`DESIGN.md`); Core Web Vitals; brak zewnętrznych fontów i skryptów; analityka i cookies zgodnie z decyzją (RODO), jeśli są używane.
- **Narzędzia bez instalacji:** inspekcja ręczna, Lighthouse w przeglądarce, PageSpeed Insights, Rich Results Test, Schema Markup Validator, zwykły klient HTTP do statusów i nagłówków (np. `curl -I`). Programy do crawlowania wymagają zgody.

### 12.3 Kontrole techniczne po uruchomieniu strony na `www.kasiadent.pl`
| # | Kontrola | Oczekiwany wynik |
|---|---|---|
| 1 | Siedem adresów z punktu 3.2 (oraz ścieżki, np. `/uslugi/protetyka`) | 301 jednym skokiem na `https://www.kasiadent.pl/...`, bez łańcucha i pętli |
| 2 | Adres nieistniejący na hoście aliasu (np. `https://drkasiadent.pl/nie-istnieje`) | wariant A: 404 na hoście aliasu; wariant B: jedno 301 na ten sam adres i końcowe 404; w żadnym wariancie przekierowanie na stronę główną |
| 3 | Certyfikat HTTPS dla `www.kasiadent.pl`, `kasiadent.pl`, `drkasiadent.pl`, `www.drkasiadent.pl` | poprawny, bez ostrzeżeń, ważny |
| 4 | `https://www.kasiadent.pl/robots.txt` | 200, treść zgodna z projektem (pięć grup), UTF-8; hosty przekierowujące kierują `/robots.txt` 301 na kanoniczny plik |
| 5 | `https://www.kasiadent.pl/sitemap.xml` | 200, poprawny XML bez placeholderów, tylko adresy kanoniczne `https://www.kasiadent.pl`, bez domeny dodatkowej i nieopublikowanych tłumaczeń |
| 6 | Canonical na każdej stronie | adres bezwzględny `https://www.kasiadent.pl/...`, własny; EN nie wskazuje PL |
| 7 | Hreflang | pary PL↔EN z odnośnikami zwrotnymi i do siebie; brak do nieopublikowanych stron; brak `x-default` |
| 8 | Statusy stron i strona 404 | 200 dla stron; nieistniejący adres zwraca 404 |
| 9 | Brak `noindex` na produkcji; brak indeksowania `drkasiadent.pl` | potwierdzone w Search Console i wynikach wyszukiwania |
| 10 | JSON-LD | walidacja w Schema Markup Validator i Rich Results Test; zgodność z widoczną treścią; brak placeholderów i niezatwierdzonych właściwości; zgodność BreadcrumbList z rzeczywistą nawigacją (jeśli użyty) |
| 11 | Wydajność i dostępność | Lighthouse i PageSpeed na telefonie; WCAG 2.2 AA; działanie bez JavaScriptu |
| 12 | Mieszana treść, Open Graph | brak zasobów HTTP; `og:url` i obrazy pod `https://www.kasiadent.pl` (jeśli Open Graph jest używany) |
| 13 | Search Console | domena zweryfikowana, `sitemap.xml` zgłoszony, inspekcja adresów kluczowych stron (**WYMAGA DZIAŁANIA WŁAŚCICIELA**) |
| 14 | Bing Webmaster Tools i Profil Firmy | konto, sitemapa, adres strony w profilu (**WYMAGA DZIAŁANIA WŁAŚCICIELA**) |
| 15 | Logi i boty | żądania botów z punktu 11.8 i brak błędów 5xx dla `robots.txt` |
| 16 | Punkt odniesienia audytu AI | wykonany (11.8) |
| 17 | Termin ważności domen | data wygaśnięcia domeny dodatkowej wpisana w kalendarz, przypomnienia 90/60/30 dni |
| 18 | HSTS (jeśli włączony) | działa po stabilnym HTTPS, bez błędów certyfikatu |

### 12.4 Po publikacji
Pierwsze dni (indeksowanie, błędy, adres kanoniczny wybrany przez Google, wersje językowe), po 2–4 tygodniach (pokrycie sitemapy, hreflang i schema w raportach, pierwsze zapytania, punkt odniesienia AI, logi), co miesiąc (Skuteczność, kanibalizacja, Core Web Vitals, aktualność treści i NAP), co kwartał (mapa fraz, ponowne badania Keyword Planner jako rekomendacja, audyt AI, **przegląd polityki crawlerów, terminów i dokumentacji dostawców, w tym ponowna weryfikacja AIPREF**, termin ważności domen). **Raport z audytu:** wykonane kontrole, wyniki, problemy i ryzyka, elementy do decyzji właściciela. Zmiany treści i metadanych wynikające z danych tylko przez rejestr propozycji (8.2) i zatwierdzenie. Merge i publikacja zawsze wymagają osobnej zgody (`CLAUDE.md`, punkt 5).

## 13. Pomiar i monitorowanie
### 13.1 Google Search Console (obowiązkowy)
- **WYMAGA DZIAŁANIA WŁAŚCICIELA** (konto Google, DNS): weryfikacja własności domeny **[POTWIERDZONE]** rekordem TXT w DNS (wartość zaczyna się od `google-site-verification=`; rekord pozostaje po weryfikacji; propagacja do 2–3 dni; [pomoc](https://support.google.com/webmasters/answer/9008080)); dodanie użytkowników. Claude Code i ChatGPT nie otrzymują dostępu do konta, a pracują na wyeksportowanych danych. Opcjonalnie właściwość dla `drkasiadent.pl` wyłącznie do monitorowania (bez sitemapy).
- Zgłoszenie `sitemap.xml` po publikacji; kontrola indeksowania (inspekcja adresów dla Startu, siedmiu usług, Cennika, Pierwszej wizyty, Kontaktu; wersje PL i EN; adres kanoniczny).
- Analiza zapytań, kliknięć, wyświetleń, CTR i średniej pozycji w podziale na strony, w tym osobne zestawienie dla każdej usługi (fraza główna z mapy 8.4, jej wyświetlenia, kliknięcia, CTR, pozycja). Średnia pozycja jest wartością uśrednioną i nie zastępuje ręcznej kontroli wyników (**[PRAKTYKA]**). Raport Core Web Vitals (może być początkowo pusty). Wykrywanie kanibalizacji (dwie strony z tą samą główną intencją).
- **Aktualizacja mapy fraz na podstawie rzeczywistych danych:** zapytania z wysoką liczbą wyświetleń i niskim CTR trafiają do przeglądu metadanych, zapytania na niewłaściwej stronie do korekty linkowania, nowe zapytania do planu Bloga. Każda zmiana treści lub metadanych przechodzi przez rejestr propozycji (8.2) i wymaga zatwierdzenia.
### 13.2 Bing Webmaster Tools i Profil Firmy
Konto i weryfikacja (WYMAGA DZIAŁANIA WŁAŚCICIELA), sitemapa, raport indeksowania. Profil Firmy: poprawność danych, statystyki, odpowiedzi na opinie bez ujawniania danych pacjentów.
### 13.3 Keyword Planner
Rejestr badań i rekomendowane ponowne badania zgodnie z punktem 8.8. Oryginalne eksporty poza publicznym repozytorium.
### 13.4 Analityka i cookies
Brak decyzji. Weryfikacja domeny w Search Console i Bing nie wymaga skryptów analitycznych na stronie. Narzędzie analityczne i zgody (RODO, polityka prywatności, `CLAUDE.md` punkt 6) wymagają decyzji właściciela i nie są warunkiem uruchomienia strony (punkt 17.2).

## 14. Harmonogram i kolejność prac
Każdy etap to osobne zadanie z planem (`D-001`). Merge i publikacja zawsze wymagają osobnej zgody.

| Nr | Etap | Wykonawca | Zależności | Oznaczenie |
|---|---|---|---|---|
| 1 | Mapa fraz i architektura SEO (ten dokument, rozdziały 4 i 8) | Claude Code (propozycje), ChatGPT (przegląd), właściciel (decyzje) | zatwierdzone treści usług | – |
| 2 | Google Ads i Keyword Planner | właściciel | etap 1 | **wykonany** (badanie z 13.11.2026); dobadanie rekomendowane, nie warunek |
| 3 | Analiza danych i zatwierdzenie docelowych fraz | Claude Code, ChatGPT, właściciel | dane z 13.11.2026 wystarczają | – |
| 4 | Końcowe meta title i meta description (zbiorczo) | Claude Code (propozycja), właściciel | zatwierdzone treści, adresy i mapa fraz; weryfikacja prawna | – |
| 5 | Implementacja technicznego SEO (adresy, canonical, hreflang, `robots.txt`, `sitemap.xml`, JSON-LD) | Claude Code | etapy 1–4, hosting i DNS, decyzja o rozpoczęciu implementacji strony | – |
| 6 | Publikacja i konfiguracja Google Search Console oraz Bing Webmaster Tools; przekierowania domen | właściciel | zatwierdzona publikacja, kontrole 12.3 | **WYMAGA DZIAŁANIA WŁAŚCICIELA** |
| 7 | Monitorowanie Google i wyszukiwarek AI | właściciel (dostęp), Claude Code i ChatGPT (analiza) | etap 6 | – |

## 15. Źródła (stan na 13.11.2026)
**A. Wymagania i opisy potwierdzone przez dostawców (odczytane bezpośrednio)**

*Google*
- [Funkcje AI w Google Search](https://developers.google.com/search/docs/appearance/ai-features) i [przewodnik optymalizacji pod AI](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)
- [Specyfikacja robots.txt](https://developers.google.com/search/docs/crawling-indexing/robots/robots_txt) i [wprowadzenie](https://developers.google.com/search/docs/crawling-indexing/robots/intro)
- [Przekierowania 301](https://developers.google.com/search/docs/crawling-indexing/301-redirects), [canonical](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls), [sitemapy](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap), [wersje lokalne (hreflang)](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Title link](https://developers.google.com/search/docs/appearance/title-link), [snippet](https://developers.google.com/search/docs/appearance/snippet)
- [Galeria danych strukturalnych](https://developers.google.com/search/docs/appearance/structured-data/search-gallery), [wytyczne ogólne danych strukturalnych](https://developers.google.com/search/docs/appearance/structured-data/sd-policies), [Local business](https://developers.google.com/search/docs/appearance/structured-data/local-business), [Organization](https://developers.google.com/search/docs/appearance/structured-data/organization), [Article](https://developers.google.com/search/docs/appearance/structured-data/article), [Breadcrumb](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb)
- [Tworzenie pomocnych treści](https://developers.google.com/search/docs/fundamentals/creating-helpful-content), [Core Web Vitals (web.dev)](https://web.dev/articles/vitals)
- [Wytyczne Profilu Firmy](https://support.google.com/business/answer/3038177)
- [Crawlery Google (Google-Extended)](https://developers.google.com/crawling/docs/crawlers-fetchers/google-common-crawlers), [fetchery użytkownika](https://developers.google.com/crawling/docs/crawlers-fetchers/google-user-triggered-fetchers), [blog Google o kontroli treningu AI (30.10.2026)](https://developers.google.com/search/blog/2026/10/ai-training-control), [Gemini Apps Privacy Hub](https://support.google.com/gemini/answer/13594961)
- [Keyword Planner](https://support.google.com/google-ads/answer/7337243), [weryfikacja własności w Search Console](https://support.google.com/webmasters/answer/9008080)

*OpenAI, Anthropic, Perplexity, Meta, xAI*
- OpenAI: [boty (crawlery)](https://developers.openai.com/api/docs/bots)
- Anthropic: [crawlery](https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler), [usuwanie treści z wyszukiwania Claude](https://support.claude.com/en/articles/10684638-blocking-and-removing-content-from-claude), [narzędzie wyszukiwania w API](https://platform.claude.com/docs/en/agents-and-tools/tool-use/web-search-tool)
- Perplexity: [crawlery](https://docs.perplexity.ai/docs/resources/perplexity-crawlers)
- Meta: [web crawlers](https://developers.facebook.com/documentation/sharing/webmasters/web-crawlers)
- xAI: [narzędzie wyszukiwania](https://docs.x.ai/developers/tools/web-search)

*Microsoft*
- [Blog Bing: preferencje AI Training i AI Grounding (30.10.2026)](https://blogs.bing.com/search/2026/10/your-content-your-choice-clearer-preferences-for-training-and-grounding/)
- [Blog Bing: NoArchive i NoCache (2023)](https://blogs.bing.com/webmaster/september-2023/Announcing-new-options-for-webmasters-to-control-usage-of-their-content-in-Bing-Chat)
- [Blog Bing: sitemapy w wyszukiwaniu AI (2025)](https://blogs.bing.com/webmaster/2025/7/Keeping-Content-Discoverable-with-Sitemaps-in-AI-Powered-Search/)
- [Microsoft Learn: wyszukiwanie w sieci w Copilot](https://learn.microsoft.com/en-us/microsoft-365/copilot/manage-public-web-access)

*Schema.org, IETF i inne*
- Schema.org (wersja 30.1): [Dentist](https://schema.org/Dentist), [Person](https://schema.org/Person), [Service](https://schema.org/Service), [WebSite](https://schema.org/WebSite), [WebPage](https://schema.org/WebPage), [CreativeWork](https://schema.org/CreativeWork), [inLanguage](https://schema.org/inLanguage), [BreadcrumbList](https://schema.org/BreadcrumbList), [ListItem](https://schema.org/ListItem), [BlogPosting](https://schema.org/BlogPosting)
- IETF AIPREF: [grupa robocza](https://datatracker.ietf.org/wg/aipref/about/), [draft-ietf-aipref-vocab](https://datatracker.ietf.org/doc/draft-ietf-aipref-vocab/), [draft-ietf-aipref-attach](https://datatracker.ietf.org/doc/draft-ietf-aipref-attach/), [draft-kelley-aipref-training-preference-signal](https://datatracker.ietf.org/doc/draft-kelley-aipref-training-preference-signal/) (szkice, nie standardy)
- [IndexNow](https://www.indexnow.org/documentation) (opis protokołu; wdrożenie odłożone)

**B. Źródła pośrednie lub niezweryfikowane (nie traktować jako potwierdzone)**
- [OpenAI: FAQ dla wydawców](https://help.openai.com/en/articles/12627856) (odczyt zwrócił 403; wiedza z podsumowania wyszukiwarki: `noindex` w ChatGPT Atlas, wymóg zakresów IP, `utm_source=chatgpt.com`).
- Strony pomocy Bing Webmaster Tools: [roboty Bing](https://www.bing.com/webmasters/help/which-crawlers-does-bing-use-8c184ec0), [nowe preferencje AI](https://www.bing.com/webmasters/help/new-ai-preferences-2t1cc16d), [wytyczne](https://www.bing.com/webmasters/help/webmaster-guidelines-30fba23a), [meta robots](https://www.bing.com/webmasters/help/robots-meta-tags-and-attributes-that-bing-supports-5198d240) (zwracają tylko tytuł).
- Rola danych strukturalnych w Bing (podsumowanie wytycznych i wpisów Bing), konsumencki Copilot, Bing Places.
- Pomoc Google Ads: definicja kolumny „Konkurencja" (strony pomocy z 2020–2022).
- Twierdzenie, że `PerplexityBot` stosuje się do `robots.txt` (dokumentacja tylko wskazuje tagi `robots.txt`), oraz terminy wdrożenia wspólnego sygnału AIPREF przez Google (zamiar: „w 2027" / „early 2027").

**C. Dobre praktyki SEO** (nie są wymaganiami wyszukiwarek): punkty oznaczone **[PRAKTYKA]** w tym dokumencie.

**D. Hipotezy i eksperymenty GEO/AEO:** badania i raporty firm SEO (m.in. Ahrefs, SE Ranking, Whitespark, Seer Interactive) przywoływane w skillach SEO, **nieodczytane bezpośrednio** i niestanowiące podstawy żadnych wymagań; `llms.txt` poza Google; rola Bing Places; wzorce bloków odpowiedzi.

## 16. Potencjalne konflikty z dokumentacją projektu
**`CLAUDE.md`**
- Punkt 3 (bez kroku budowania i bez nowych narzędzi bez zgody): utrzymanie `sitemap.xml` skryptem, narzędzia do crawlowania i walidacji, konfiguracja przekierowań po stronie hostingu i DNS wymagają zgody jako narzędzia lub operacje zewnętrzne. W samym HTML mieszczą się: `canonical`, `hreflang`, JSON-LD, Open Graph.
- Punkt 1 i 7: SEO nie upoważnia do zmiany zatwierdzonych treści, H1 ani metadanych. Opisy w JSON-LD i Open Graph muszą pochodzić z zatwierdzonych tekstów.
- Punkt 5: publikacja, merge, konfiguracja domen i DNS zawsze wymagają osobnej zgody.
- Punkt 6: repozytorium jest publiczne. Eksporty Keyword Planner i dane konta poza nim. Pliki treści z danymi kontaktowymi (w tym adresem e-mail) są dziś poza repozytorium, więc ich dodanie wymaga decyzji o ujawnieniu.
**`DESIGN.md`**
- „Bez nieuzgodnionych zewnętrznych fontów, skryptów, zdjęć i integracji": osadzona mapa Google, analityka, obrazy Open Graph i zewnętrzne narzędzia wymagają decyzji. Weryfikacja Search Console przez DNS nie dodaje skryptów.
- Przełącznik języka PL/EN i widoczne okruszki nie są wymienione w liście komponentów `DESIGN.md`, więc wymagają decyzji o wyglądzie. BreadcrumbList stosujemy tylko wtedy, gdy odpowiada rzeczywistej nawigacji (widoczny komponent nie jest wymogiem Google).
- Rezerwacja online IQDental: nie implementować, więc bez `potentialAction` w schema.
- Zakaz fikcyjnych zdjęć lekarza, personelu i gabinetu: schema `image`, `logo` i Open Graph tylko z zatwierdzonych plików.
**`docs/DECISIONS.md`**
- Zawiera tylko `D-001`. Decyzje z punktu 1 (domena, host, język, crawlery, Google-Extended, AIPREF, IndexNow, metadane, schema, okruszki) wymagają zapisu jako kolejne wpisy po zatwierdzeniu dokumentu.
**Zatwierdzone treści i materiały**
- `WYMAGANIA_DLA_CLAUDE.md` mówi o „projekcie strony w Astro", a `CLAUDE.md` o wersji początkowej w czystym HTML/CSS/JS z możliwością późniejszej migracji do Astro. **DO ZATWIERDZENIA**: wpływa na sposób generowania `sitemap.xml` i przekierowań.
- Fraza „dentysta" nie występuje w zatwierdzonych treściach (punkt 8.2). Frazy z mapy są analizą, a zmiany tekstów wymagają osobnych zgód.
- Rozbieżny e-mail (Kontakt a Pierwsza wizyta) i godziny bez dni tygodnia blokują kompletne dane `Dentist`.
- Strony `/uslugi`, O mnie i Blog nie mają zatwierdzonych adresów. Pozycja „Usługi" w menu wymaga celu.
- Wersje EN są roboczymi tłumaczeniami wymagającymi przeglądu gabinetu (README materiałów). Zdanie o konsultacjach po polsku i angielsku w zatwierdzonym tekście O mnie nie rozstrzyga `knowsLanguage`, które pozostaje do potwierdzenia.
- Cennik ma charakter orientacyjny, więc bez `Offer` i cen w schema.
- Sformułowania marketingowe na stronie głównej (np. o doświadczeniu i nowoczesnych metodach) podlegają weryfikacji prawnej (punkt 10.3).

## 17. Lista decyzji DO ZATWIERDZENIA
Zatwierdzone i niepowtarzane tutaj: domena główna, host kanoniczny, domena dodatkowa, wariant A (architektura PL `/` i EN `/en/`), polityka crawlerów (pięć grup), Google-Extended, odroczenie AIPREF i IndexNow, mapa intencji i priorytety P1/P2/P3, przypisanie „licówki Reda", model `WebSite`/`WebPage`, 45 i 13 pytań audytu, Keyword Planner jako rekomendacja, brak zmian zatwierdzonych treści.

**Opcjonalne właściwości Schema.org, analityka i Open Graph nie są warunkiem uruchomienia strony.** Strona może zostać uruchomiona bez nich, a niezatwierdzone właściwości pomijamy (punkt 9.1).

### 17.1 Decyzje rzeczywiście blokujące publikację strony
**Hosting, DNS i adresy**
- [ ] Wybór hostingu (wymagania z punktu 3.4).
- [ ] Dostawca DNS i techniczny sposób konfiguracji przekierowań. **WYMAGA DZIAŁANIA WŁAŚCICIELA.**
- [ ] Wariant obsługi nieistniejących ścieżek (A lub B), zależny od hostingu.
- [ ] Konwencja adresów (bez `.html` i bez końcowego ukośnika) i obsługa wariantów, zależna od hostingu.
- [ ] Adresy polskich stron bez zatwierdzonych ścieżek: O mnie, Blog. Formalne potwierdzenie `/cennik`, `/pierwsza-wizyta`, `/kontakt`.
- [ ] Cel pozycji „Usługi" w menu (czy `/uslugi` istnieje jako strona, czy menu rozwija listę usług).
- [ ] Data wygaśnięcia, rejestrator i autoodnawianie obu domen oraz sprawdzenie, czy domeny miały wcześniej treści w indeksie. **WYMAGA DZIAŁANIA WŁAŚCICIELA.**

**Treści i dane wyświetlane na stronie**
- [ ] Rozbieżny e-mail i brak dni tygodnia przy godzinach otwarcia (NAP na stronie Kontakt i w stopce).
- [ ] **Ostateczne meta title i meta description** (zbiorczo, po zatwierdzeniu treści, adresów i mapy fraz).
- [ ] Weryfikacja prawna (punkt 10.3) i polityka opinii.
- [ ] Rozstrzygnięcie niezgodności: Astro (`WYMAGANIA_DLA_CLAUDE.md`) a czysty HTML/CSS/JS (`CLAUDE.md`).
- [ ] Zatwierdzenie `robots.txt` w ostatecznej formie przy wdrożeniu oraz kontrola, czy środowisko testowe nie przenosi `Disallow: /` na produkcję.

**Konta wymagane do zarejestrowania strony w wyszukiwarkach**
- [ ] Konto Search Console (weryfikacja DNS). **WYMAGA DZIAŁANIA WŁAŚCICIELA.** Może nastąpić po uruchomieniu strony.

### 17.2 Decyzje potrzebne tylko do wdrożenia określonych funkcji
**Wersja angielska (przed publikacją EN)**
- [ ] Pełna mapa adresów EN (poza zatwierdzoną architekturą `/en/`; `/en/services/prosthetics` jest przykładem) i wybór wariantów slugów.
- [ ] Publikacja angielskich tłumaczeń (przegląd gabinetu i termin).
- [ ] Przełącznik języka PL/EN (wygląd, `DESIGN.md`).
- [ ] Zatwierdzone angielskie nazwy usług (jeśli mają trafić do JSON-LD).

**Okruszki (przed wdrożeniem okruszków)**
- [ ] Wariant okruszków (1, 2 lub 3) i wygląd komponentu, przy zatwierdzaniu struktury i projektu. Do tego czasu obowiązuje wariant 3.
- [ ] Zatwierdzenie strony `/uslugi` i `/en/services` (tylko dla wariantu 1).

**Dane w znacznikach JSON-LD (przed użyciem danego pola; niezatwierdzone pomijamy)**
- [ ] Dane z punktu 9.6, w tym `knowsLanguage`, współrzędne, logo, zdjęcia, `sameAs`, honorific, stanowisko i `alumniOf` lekarza, opisy usług, `areaServed`, `paymentAccepted`.
- [ ] Pełna nazwa prawna, profile społecznościowe, adres Profilu Firmy.
- [ ] Wartość `url` w węźle `Dentist` na stronie EN.

**Integracje i narzędzia (przed wdrożeniem danej funkcji)**
- [ ] Analityka i polityka cookies (RODO), jeśli analityka ma być użyta.
- [ ] Osadzenie mapy Google (domyślnie odnośnik).
- [ ] Open Graph (obrazy i teksty), jeśli używany.
- [ ] Metoda utrzymania `sitemap.xml` bez kroku budowania (ręcznie czy skrypt).
- [ ] Konto Bing Webmaster Tools i użytkownicy Search Console. **WYMAGA DZIAŁANIA WŁAŚCICIELA.**
- [ ] Profil Firmy Google: czy istnieje, kto go prowadzi, kategorie, zdjęcia.
- [ ] Wpisy w `docs/DECISIONS.md` dla zatwierdzonych decyzji SEO (osobne zadanie).

### 17.3 Opcjonalne ulepszenia i decyzje, które można podjąć później
- [ ] Czy `Organization` jest potrzebny obok `Dentist`.
- [ ] HSTS (opcjonalnie, po stabilnym HTTPS).
- [ ] Zakresy IP botów (OpenAI, Perplexity, Anthropic) w zaporze lub CDN hostingu, jeśli hosting to oferuje.
- [ ] Czy ujmować inne crawlery treningowe (m.in. Common Crawl, Applebot-Extended, ByteDance), po ich weryfikacji. Domyślnie nie.
- [ ] Zakres platform audytu AI (Meta AI i Grok opcjonalnie), konta i plany do audytu, harmonogram audytów, dostęp do logów serwera, procedura reagowania na błędne informacje o gabinecie (punkt odniesienia zalecany przed publikacją).
- [ ] Miejsce przechowywania eksportów Keyword Plannera poza repozytorium, zasady dostępu (każdorazowa zgoda, tylko odczyt) i zabezpieczenie `.gitignore`.
- [ ] Obszar obsługi i miejscowości w okolicy Redy (wymagane przed użyciem w treści lub `areaServed`).
- [ ] Pozycje z Cennika bez opisu na stronach usług (np. powtórne leczenie kanałowe, lapisowanie, inlay/onlay): czy mają dostać treści.
- [ ] Decyzja o przedłużeniu domeny dodatkowej (po 2 latach).
- [ ] Dobadanie fraz w Keyword Plannerze (punkt 8.8).

### 17.4 Zadania i wartości domyślne (nie są decyzjami)
- Ponowna weryfikacja AIPREF po ustabilizowaniu specyfikacji i polityk dostawców (przegląd kwartalny).
- Bezpośredni odczyt źródeł pośrednich: FAQ OpenAI dla wydawców, strony pomocy Bing, FAQ Bing Webmaster Tools, konsumencki Copilot.
- `llms.txt`: domyślnie nie tworzymy. IndexNow: odłożony.
