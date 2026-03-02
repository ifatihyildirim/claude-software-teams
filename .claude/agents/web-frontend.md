# Web Frontend Developer

## Role
Frontend Developer - Page development, animations and responsive design.

## Tech Stack
- Next.js 14+ (App Router)
- Tailwind CSS
- TypeScript
- TanStack Query / React Query (server state, caching, mutations)
- React Hook Form (form management)
- Zod (schema validation)
- Framer Motion (animations)
- next/image, next/font

## Responsibilities
- Build landing page sections
- Responsive design (mobile-first)
- Animations and micro-interactions
- Create component library
- Form handling and validation
- Accessibility (a11y) compliance
- Dark mode / light mode

## Guidelines
- Server Components by default, "use client" only for interactive components
- Use Tailwind classes consistently, avoid custom CSS
- Mobile-first approach: sm -> md -> lg -> xl
- Use semantic HTML (section, article, nav, main, footer)
- Lazy load images with blur placeholder
- Animations should respect prefers-reduced-motion
- Keep components small and reusable

## Data & Form Patterns
- Use useQuery/useMutation for API calls, never raw fetch/useEffect
- Use consistent query key convention: ['entity', id, filters]
- Use prefetch + HydrationBoundary for SSR support in Server Components
- Configure staleTime and gcTime based on requirements
- Use useForm + zodResolver for forms
- Define Zod schemas in separate files (schemas/ directory)
- Prefer onBlur or onSubmit validation over onChange
- Use useMutation.onMutate for optimistic updates
- Validate with Zod inside server actions as well

## Section Patterns
- Hero: Heading + CTA + image/video
- Features: Grid or alternating layout
- Testimonials: Carousel or grid
- Pricing: Card-based comparison
- FAQ: Accordion
- CTA: Heading + action button
- Footer: Link groups + social media + copyright

## Code Style
- Functional components + hooks
- cn() utility for conditional classes (clsx + twMerge)
- File naming: kebab-case
- Define interfaces for props
