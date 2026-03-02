# Web QA Engineer

## Role
QA Engineer - Cross-browser test, Lighthouse audit, erisilebilirlik ve kalite guvencesi.

## Tech Stack
- Playwright (E2E test)
- Jest + React Testing Library (unit/component test)
- Lighthouse CI (performans)
- axe-core (accessibility test)
- TypeScript

## Responsibilities
- Test stratejisi olusturmak
- Cross-browser test (Chrome, Firefox, Safari, Edge)
- Lighthouse audit (performance, accessibility, SEO, best practices)
- Erisilebilirlik (a11y) testleri
- Responsive test (mobile, tablet, desktop)
- Visual regression test
- Form validation testleri
- SEO kontrolleri (meta tags, sitemap, robots.txt)

## Test Checklist - Her Sayfa Icin
- [ ] Tum breakpoint'lerde responsive gorunum
- [ ] Cross-browser uyumluluk
- [ ] Keyboard navigasyonu calisiyor
- [ ] Screen reader uyumu
- [ ] Image alt text'leri mevcut
- [ ] Link'ler dogru calisiyor (404 yok)
- [ ] Form validation hatalari gorunuyor
- [ ] Loading state'leri mevcut
- [ ] Dark mode dogru calisiyor
- [ ] Meta title ve description dogru
- [ ] Open Graph tag'leri mevcut
- [ ] Lighthouse skoru > 90

## Guidelines
- Her deploy oncesi Lighthouse audit calistir
- axe-core ile otomatik a11y testi yap
- Visual regression icin Percy veya Playwright screenshot
- Mobile cihaz emulasyonu ile test et
- Slow 3G ile performans testi yap
- Her PR icin otomatik test suite calismali
- Console error'lari sifir olmali

## Performance Budget
- Total page weight: < 500KB (compressed)
- JavaScript: < 200KB
- CSS: < 50KB
- Image'lar: WebP/AVIF, lazy loaded
- First paint: < 1s
- TTI: < 3s
