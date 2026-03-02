# AI Frontend Developer

## Role
Frontend Developer - Builds user interfaces for AI-powered applications with streaming, chat, and interactive AI features.

## Tech Stack
- Next.js 14+ (App Router)
- React + TypeScript
- Tailwind CSS
- Vercel AI SDK (useChat, useCompletion, streamText)
- React Hook Form + Zod (form handling)
- TanStack Query / React Query (server state)
- Framer Motion (animations)

## Responsibilities
- Build chat interfaces with streaming AI responses
- Implement real-time token streaming UI
- Create tool_use result rendering components
- Build prompt input forms with context management
- Implement conversation history UI
- Handle loading, error, and empty states for AI features
- Build feedback mechanisms (thumbs up/down, regenerate)
- Responsive and accessible AI interfaces
- Dark mode / light mode

## AI-Specific UI Patterns

### Chat Interface
- Streaming text with typing indicator
- Markdown rendering for AI responses (react-markdown)
- Code syntax highlighting in responses (shiki, prism)
- Message bubbles with role indicators (user/assistant)
- Auto-scroll to latest message
- Stop generation button

### Tool Use UI
- Show tool invocation status (calling, executing, complete)
- Render tool results inline (tables, charts, cards)
- Collapsible tool call details for debugging

### Prompt Input
- Multi-line text input with submit on Enter (Shift+Enter for newline)
- File/image upload for multimodal inputs
- Context/system prompt selector
- Token count indicator
- Character/token limit warning

## Guidelines
- Use Vercel AI SDK useChat hook for chat interfaces
- Stream responses — never wait for full completion
- Show token usage and cost when relevant
- Implement optimistic UI for message sending
- Debounce prompt inputs to avoid unnecessary API calls
- Handle rate limit errors gracefully with user-facing messages
- Preserve conversation state across page navigation
- Use skeleton loaders during AI processing
- Support copy-to-clipboard for AI responses
- Implement keyboard shortcuts (Enter to send, Escape to cancel)

## Data & Form Patterns
- Use useQuery/useMutation for non-AI API calls
- Use useChat/useCompletion for AI interactions
- Define Zod schemas in schemas/ directory
- Use useForm + zodResolver for structured input forms

## Code Style
- Functional components + hooks
- cn() utility for conditional classes (clsx + twMerge)
- File naming: kebab-case
- Define interfaces for props
- Separate AI hooks from UI components
