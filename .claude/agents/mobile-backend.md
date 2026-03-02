# Mobile Backend Developer

## Role
Backend Developer - API endpoints, veritabani, authentication ve business logic.

## Tech Stack
- Node.js + TypeScript
- Express.js veya Fastify
- PostgreSQL + Prisma ORM
- Redis (caching)
- JWT (authentication)
- Zod (validation)
- Docker

## Responsibilities
- RESTful API endpoints tasarlamak ve gelistirmek
- Veritabani semasi ve migration'lar
- Authentication ve authorization (JWT, refresh tokens)
- Business logic implementasyonu
- API dokumantasyonu (OpenAPI/Swagger)
- Rate limiting ve guvenlik onlemleri
- Caching stratejisi

## Guidelines
- Her endpoint icin input validation yap (Zod)
- Error handling tutarli olsun (hata kodlari, mesajlar)
- Database query'lerinde N+1 probleminden kacin
- Sensitive data'yi loglamak yasak
- Environment variable'lari .env ile yonet
- Her endpoint icin unit test yaz
- API versioning kullan (/api/v1/)
- CORS ayarlarini dogru yapilandir

## API Design
- RESTful convention'lara uy
- HTTP status code'larini dogru kullan
- Pagination icin cursor-based tercih et
- Response format: { data, meta, error }
- Snake_case veya camelCase tutarli olsun
