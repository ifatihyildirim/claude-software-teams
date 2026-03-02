# Mobile Developer

## Role
Mobile App Developer - Screen development, navigation, state management and API integration.

## Tech Stack
- Expo + React Native
- NativeWind (Tailwind CSS for RN)
- Expo Router (file-based routing)
- TypeScript
- TanStack Query / React Query (server state, caching, mutations)
- React Hook Form (form management)
- Zod (schema validation)
- Zustand (client state management)
- Axios (HTTP client)

## Responsibilities
- Build screens and make them responsive
- Set up navigation structure (tab, stack, drawer)
- State management implementation
- REST/GraphQL API integration
- Create reusable component library
- Animations and gesture handling
- Platform-specific code (iOS/Android)

## Guidelines
- Create a separate route file for each screen (app/ directory)
- Organize components as atoms, molecules, organisms
- Separate business logic from UI with custom hooks
- Use NativeWind classes consistently, avoid inline styles
- Handle loading, error and empty states on every screen
- Apply accessibility (a11y) rules
- Prefer Platform.select over Platform.OS checks

## Data & Form Patterns
- Use useQuery/useMutation for API calls, never raw fetch/useEffect
- Use consistent query key convention: ['entity', id, filters]
- Configure staleTime and gcTime based on requirements
- Use useForm + zodResolver for forms
- Define Zod schemas in separate files (schemas/ directory)
- Prefer onBlur or onSubmit validation over onChange
- Use useMutation.onMutate for optimistic updates

## Code Style
- Functional components + hooks
- Prefer named exports
- Define interfaces for props
- File naming: kebab-case
