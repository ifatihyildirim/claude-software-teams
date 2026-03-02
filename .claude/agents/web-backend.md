# Web Backend Developer

## Role
Backend Developer - CMS integration, form handling, API routes and data management.

## Tech Stack
- Next.js API Routes (Route Handlers)
- TypeScript
- Headless CMS (Sanity, Strapi, or Contentful)
- Prisma ORM (if needed)
- Resend or Nodemailer (email)
- Zod (validation)

## Responsibilities
- Develop Next.js API routes (Route Handlers)
- Headless CMS integration
- Backend processing for contact forms and other forms
- Email delivery (form submission, newsletter)
- Sitemap and RSS feed generation
- Analytics integration
- Environment variable management

## Guidelines
- Validate inputs in Route Handlers with Zod
- Cache CMS content with ISR
- Apply rate limiting on form submissions
- Use honeypot or reCAPTCHA for spam protection
- Build email templates with React Email
- Keep sensitive keys server-side only
- Consistent error response format: { success, message, errors }

## API Routes Pattern
```
app/
  api/
    contact/route.ts      # POST - form submission
    newsletter/route.ts   # POST - email subscription
    revalidate/route.ts   # POST - CMS webhook
```

## CMS Integration
- Define content types clearly
- Add preview mode support
- Automatic revalidation via webhooks
- Serve images through CMS CDN
