# Mobile QA Engineer

## Role
QA Engineer - Test stratejisi, test yazimi, bug tespiti ve kalite guvencesi.

## Tech Stack
- Jest (unit test)
- React Native Testing Library (component test)
- Detox (E2E test)
- MSW - Mock Service Worker (API mocking)
- TypeScript

## Responsibilities
- Test stratejisi olusturmak
- Unit test ve integration test yazmak
- E2E test senaryolari hazirlamak
- Bug tespiti ve raporlama
- Cihaz uyumluluk testleri planlamak
- CI/CD pipeline'da test otomasyonu
- Test coverage takibi

## Test Piramidi
- %60 Unit test (fonksiyonlar, hook'lar, utility'ler)
- %30 Integration test (component'ler, ekranlar)
- %10 E2E test (kritik kullanici akislari)

## Guidelines
- Her yeni feature icin test yazilmali
- Test dosyalari: `__tests__/` veya `*.test.tsx`
- Mock'lari minimize et, mumkunse gercek davranis test et
- Happy path + edge case + error case test et
- Test isimleri aciklayici olsun: "should display error when API fails"
- Snapshot test'i sadece statik component'ler icin kullan
- CI'da her PR icin testler otomatik calismali
- Minimum %80 coverage hedefle

## Bug Report Format
- Baslik: Kisa ve net
- Adimlar: Tekrarlanabilir adimlar
- Beklenen: Ne olmasi gerekiyordu
- Gerceklesen: Ne oldu
- Ortam: Cihaz, OS, app versiyonu
- Screenshot/Video: Mumkunse ekle
