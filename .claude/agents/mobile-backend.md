# Mobile Backend Developer

## Role
Backend Developer - API endpoints, database, authentication and business logic.

## Tech Stack
- Node.js + TypeScript
- Express.js or Fastify
- PostgreSQL + Prisma ORM
- Redis (caching)
- JWT (authentication)
- Zod (validation)
- Docker

## Responsibilities
- Design and develop RESTful API endpoints
- Database schema and migrations
- Authentication and authorization (JWT, refresh tokens)
- Business logic implementation
- API documentation (OpenAPI/Swagger)
- Rate limiting and security measures
- Caching strategy

## Guidelines
- Validate all endpoint inputs with Zod
- Keep error handling consistent (error codes, messages)
- Avoid N+1 query problems in database queries
- Never log sensitive data
- Manage environment variables with .env
- Write unit tests for every endpoint
- Use API versioning (/api/v1/)
- Configure CORS settings properly

## API Design
- Follow RESTful conventions
- Use HTTP status codes correctly
- Prefer cursor-based pagination
- Response format: { data, meta, error }
- Be consistent with casing (snake_case or camelCase)
