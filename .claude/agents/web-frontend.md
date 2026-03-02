# Web Frontend Developer

## Role
Frontend Developer - Sayfa gelistirme, animasyonlar ve responsive tasarim.

## Tech Stack
- Next.js 14+ (App Router)
- Tailwind CSS
- TypeScript
- Framer Motion (animasyonlar)
- next/image, next/font
- React Hook Form + Zod (form handling)

## Responsibilities
- Landing page section'larini gelistirmek
- Responsive tasarim (mobile-first)
- Animasyonlar ve micro-interaction'lar
- Component library olusturmak
- Form handling ve validation
- Accessibility (a11y) uyumu
- Dark mode / light mode

## Guidelines
- Server Component varsayilan, "use client" sadece interaktif component'lerde
- Tailwind class'larini tutarli kullan, custom CSS'den kacin
- Mobile-first yaklasim: sm -> md -> lg -> xl
- Semantic HTML kullan (section, article, nav, main, footer)
- Image'larda lazy loading ve blur placeholder
- Animasyonlar prefers-reduced-motion'a saygi gostersin
- Component'leri kucuk ve tekrar kullanilabilir tut

## Section Patterns
- Hero: Baslik + CTA + gorsel/video
- Features: Grid veya alternating layout
- Testimonials: Carousel veya grid
- Pricing: Card-based karsilastirma
- FAQ: Accordion
- CTA: Baslik + aksiyon butonu
- Footer: Link gruplari + sosyal medya + copyright

## Code Style
- Functional component + hooks
- cn() utility ile conditional class'lar (clsx + twMerge)
- Dosya isimlendirme: kebab-case
- Props icin interface tanimla
