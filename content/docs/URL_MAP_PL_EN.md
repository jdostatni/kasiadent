# Zatwierdzona mapa adresów URL PL/EN

**Status:** zatwierdzona przez właściciela 2026-11-15. Obie wersje językowe mają zostać uruchomione jednocześnie. Adresy są docelowymi trasami do wdrożenia; ten katalog zawiera Markdown, nie gotowe pliki HTML.

| Podstrona | PL | EN |
|---|---|---|
| Strona główna | `/` | `/en/` |
| O mnie | `/o-mnie` | `/en/about` |
| Usługi — indeks | `/uslugi` | `/en/services` |
| Cennik | `/cennik` | `/en/pricing` |
| Pierwsza wizyta | `/pierwsza-wizyta` | `/en/first-visit` |
| Blog — indeks | `/blog` | `/en/blog` |
| Kontakt | `/kontakt` | `/en/contact` |
| Stomatologia zachowawcza | `/uslugi/stomatologia-zachowawcza` | `/en/services/general-dentistry` |
| Endodoncja mikroskopowa | `/uslugi/leczenie-kanalowe-pod-mikroskopem` | `/en/services/root-canal-treatment` |
| Protetyka | `/uslugi/protetyka` | `/en/services/prosthodontics` |
| Stomatologia estetyczna | `/uslugi/stomatologia-estetyczna` | `/en/services/cosmetic-dentistry` |
| Profilaktyka | `/uslugi/profilaktyka` | `/en/services/preventive-dentistry` |
| Stomatologia dziecięca | `/uslugi/stomatologia-dziecieca` | `/en/services/childrens-dentistry` |
| Diagnostyka RTG | `/uslugi/diagnostyka-rtg` | `/en/services/dental-x-rays` |
| Artykuł — mycie zębów | `/blog/jak-prawidlowo-myc-zeby` | `/en/blog/how-to-brush-your-teeth-properly` |
| Artykuł — leczenie kanałowe | `/blog/leczenie-kanalowe-czego-sie-spodziewac` | `/en/blog/what-to-expect-from-root-canal-treatment` |
| Artykuł — licówki | `/blog/licowki-porcelanowe-czy-kompozytowe` | `/en/blog/porcelain-vs-composite-veneers` |
| Polityka prywatności i cookies | `/polityka-prywatnosci` | `/en/privacy-policy` |

## Zasady

- Przełącznik PL/EN zachowuje odpowiednią stronę; fallback do homepage języka docelowego tylko jeśli brak odpowiednika.
- Linki wewnętrzne w treściach EN kierują do tras `/en/...`.
- Przy wdrażaniu HTML/CSS/JS należy skonfigurować routing, canonical, hreflang, breadcrumbs, menu i sitemap zgodnie z mapą.
- Nie publikować nieistniejących tras bez odpowiadających im stron.
