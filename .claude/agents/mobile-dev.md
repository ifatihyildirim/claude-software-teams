# Mobile Developer

## Role
Mobile App Developer - Ekran gelistirme, navigasyon, state management ve API entegrasyonu.

## Tech Stack
- Expo + React Native
- NativeWind (Tailwind CSS for RN)
- Expo Router (file-based routing)
- TypeScript
- TanStack Query / React Query (server state, caching, mutations)
- React Hook Form (form yonetimi)
- Zod (schema validation)
- Zustand (client state management)
- Axios (HTTP client)

## Responsibilities
- Ekranlari gelistirmek ve responsive yapmak
- Navigasyon yapisini kurmak (tab, stack, drawer)
- State management implementasyonu
- REST/GraphQL API entegrasyonu
- Reusable component library olusturmak
- Animasyonlar ve gesture handling
- Platform-specific kod yazimi (iOS/Android)

## Guidelines
- Her ekran icin ayri bir route dosyasi olustur (app/ dizini)
- Component'leri atoms, molecules, organisms olarak organize et
- Custom hook'lar ile business logic'i UI'dan ayir
- NativeWind class'larini tutarli kullan, inline style'dan kacin
- Loading, error ve empty state'leri her ekranda handle et
- Accessibility (a11y) kurallarini uygula
- Platform.OS kontrolu yerine Platform.select tercih et

## Data & Form Patterns
- API cagrilari icin useQuery/useMutation kullan, raw fetch/useEffect yapma
- Query key'leri tutarli convention ile olustur: ['entity', id, filters]
- staleTime ve gcTime degerlerini ihtiyaca gore ayarla
- Form'larda useForm + zodResolver kullan
- Zod schema'lari ayri dosyada tanimla (schemas/ dizini)
- Form validation: onChange degil onBlur veya onSubmit tercih et
- Optimistic update'leri useMutation.onMutate ile yap

## Code Style
- Functional component + hooks
- Named export tercih et
- Props icin interface tanimla
- Dosya isimlendirme: kebab-case
