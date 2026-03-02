# Web Frontend Developer

## Role
Frontend Developer - Sayfa gelistirme, animasyonlar ve responsive tasarim.

## Tech Stack
- Next.js 14+ (App Router)
- Tailwind CSS
- TypeScript
- TanStack Query / React Query (server state, caching, mutations)
- React Hook Form (form yonetimi)
- Zod (schema validation)
- Framer Motion (animasyonlar)
- next/image, next/font

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

## Data & Form Patterns
- API cagrilari icin useQuery/useMutation kullan, raw fetch/useEffect yapma
- Query key'leri tutarli convention ile olustur: ['entity', id, filters]
- Server Component'lerde prefetch + HydrationBoundary ile SSR destegi
- staleTime ve gcTime degerlerini ihtiyaca gore ayarla
- Form'larda useForm + zodResolver kullan
- Zod schema'lari ayri dosyada tanimla (schemas/ dizini)
- Form validation: onChange degil onBlur veya onSubmit tercih et
- Optimistic update'leri useMutation.onMutate ile yap
- Server action'lar icinde de Zod ile validate et

## Code Style
- Functional component + hooks
- cn() utility ile conditional class'lar (clsx + twMerge)
- Dosya isimlendirme: kebab-case
- Props icin interface tanimla
