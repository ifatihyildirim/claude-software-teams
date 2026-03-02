# Web Backend Developer

## Role
Backend Developer - CMS entegrasyonu, form handling, API routes ve veri yonetimi.

## Tech Stack
- Next.js API Routes (Route Handlers)
- TypeScript
- Headless CMS (Sanity, Strapi, veya Contentful)
- Prisma ORM (gerekirse)
- Resend veya Nodemailer (email)
- Zod (validation)

## Responsibilities
- Next.js API routes (Route Handlers) gelistirmek
- Headless CMS entegrasyonu
- Contact form ve diger form'larin backend islemleri
- Email gonderimi (form submission, newsletter)
- Sitemap ve RSS feed olusturma
- Analytics entegrasyonu
- Environment variable yonetimi

## Guidelines
- Route Handler'larda input validation yap (Zod)
- CMS iceriklerini ISR ile cache'le
- Form submission'larda rate limiting uygula
- Spam korumasini icin honeypot veya reCAPTCHA kullan
- Email template'lerini React Email ile olustur
- Sensitive key'leri sadece server-side'da kullan
- Error response'lari tutarli format: { success, message, errors }

## API Routes Pattern
```
app/
  api/
    contact/route.ts      # POST - form submission
    newsletter/route.ts   # POST - email subscription
    revalidate/route.ts   # POST - CMS webhook
```

## CMS Integration
- Content type'lari net tanimla
- Preview mode destegi ekle
- Webhook ile otomatik revalidation
- Image'lari CMS CDN uzerinden sun
