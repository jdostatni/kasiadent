# OWS Stomatologia — analiza referencji dla Claude Design

**Status:** materiał referencyjny, nie zatwierdzony projekt ani specyfikacja do kopiowania. Źródło: https://www.ows-stomatologia.pl/ (zrzuty wykonane przez właściciela 15 i 20 listopada 2026 r.).

## Cel

Przeanalizować architekturę informacji, mechanikę nawigacji i układ responsywny OWS, a następnie opracować **trzy autorskie koncepcje** dr KASIA DENT. Nie kopiować grafik, tekstów, fotografii, ikon, kolorów, kodu ani układu 1:1.

## Dostarczone materiały — 14 zrzutów

| Obszar | Desktop (15.11) | Mobile (20.11) | Na co zwrócić uwagę |
|---|---|---|---|
| Strona główna | `desktop/homepage.png` | `mobile/homepage.png` | Hero, kolejność sekcji, CTA, galeria, stopka |
| Lista usług | `desktop/services.png` | `mobile/services.png` | Karty i ikony; desktop siatka, mobile jedna kolumna |
| Podstrona usługi | `desktop/service-detail-implantology.png` | `mobile/service-detail-endodontics.png` | Nagłówki, długie opisy, zdjęcia, cennik, FAQ; **inne usługi w obu referencjach** |
| Pierwsza wizyta | `desktop/first-visit.png` | `mobile/first-visit.png` | Etapy, przygotowanie, FAQ |
| Blog | `desktop/blog.png` | `mobile/blog.png` | Lista artykułów, czytelność na telefonie |
| Kontakt | `desktop/contact.png` | `mobile/contact.png` | Dane, formularz, rejestracja, mapa |
| Menu mobilne | — | `mobile/menu-expanded.png`, `mobile/menu-collapsed.png` | Menu pełnoekranowe, podmenu usług, zamknięcie, CTA |

**Uwaga dotycząca dostępności plików:** tabela określa **docelowe nazwy** PNG. Do momentu fizycznego dodania i weryfikacji plików na gałęzi nie należy traktować ich jako dostępnych w repozytorium. Oryginalne zrzuty zostały przekazane w rozmowie z właścicielem.

## Analiza — wskazówki, nie wymagania kopiowania

1. **Strona główna:** przeanalizować baner, układ sekcji, prezentację usług i galerii. Dla dr KASIA DENT nie dodawać sekcji opinii ani wieloosobowego zespołu wbrew zatwierdzonym decyzjom.
2. **Usługi:** rozważyć czytelną siatkę kart z ikonami na desktopie i wersję mobilną o umiarkowanej długości. Wszystkie **siedem** usług dr KASIA DENT musi mieć **równą rangę wizualną**.
3. **Podstrona usługi:** zachować możliwość logicznego podziału długich tekstów; nie importować oferty implantologicznej OWS, cenników, zdjęć personelu ani treści FAQ.
4. **Pierwsza wizyta:** zbadać formę etapów i FAQ, ale stosować wyłącznie zatwierdzone treści dr KASIA DENT.
5. **Kontakt:** przeanalizować kolejność informacji i formularz; nie kopiować danych OWS. Integracja z IQDental i formularz wymagają własnych decyzji oraz weryfikacji technicznej.
6. **Mobile:** ocenić menu z podmenu usług, CTA i dostępność sterowania. **Nagłówek mobilny dr KASIA DENT: wyłącznie sam ząb KD** (`docs/LOGO_USAGE.md`).
7. **Stopka:** inspiracja podziałem na grupy linków; **logo dr KASIA DENT: ząb po lewej + napis dwuliniowy**. Położenie całego logo w stopce wybierze właściciel spośród trzech propozycji Claude Design.

## Zasady pracy Claude Design

- Zestaw referencyjny **nie zastępuje** `CLAUDE.md`, `DESIGN.md`, `docs/DECISIONS.md`, `docs/LOGO_USAGE.md` ani zatwierdzonych treści.
- Przed makietami zaprezentować kierunki wizualne do zatwierdzenia; następnie trzy różne koncepcje strony głównej desktop + mobile.
- Nie zakładać, że elementy OWS są zatwierdzonymi funkcjami naszego projektu.
- Obrazy referencyjne służą **wyłącznie do wewnętrznej analizy**; nie publikować ich na stronie, nie dodawać do publicznych assetów produkcyjnych.
