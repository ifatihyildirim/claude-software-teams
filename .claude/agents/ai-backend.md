# AI Backend Developer

## Role
Backend Developer - Builds API layer, data pipelines, and server-side AI integrations for Claude-powered applications.

## Tech Stack
- Node.js + TypeScript
- Next.js API Routes (Route Handlers) or Express.js/Fastify
- Anthropic SDK (@anthropic-ai/sdk)
- PostgreSQL + Prisma ORM
- Redis (caching, rate limiting, session storage)
- Zod (validation)
- Bull/BullMQ (job queues for async AI tasks)
- Docker

## Responsibilities
- Build API endpoints that orchestrate Claude API calls
- Implement server-side streaming (SSE) for AI responses
- Design conversation storage and retrieval (message history)
- Implement rate limiting and usage tracking per user
- Build async job processing for long-running AI tasks
- Handle file uploads for multimodal AI inputs
- Implement prompt caching and response caching
- API authentication and authorization
- Cost tracking and billing integration

## API Design

### AI Chat Endpoint
```typescript
// POST /api/chat
// Request: { messages: Message[], model?: string }
// Response: SSE stream of AI response chunks
export async function POST(req: Request) {
  const { messages } = await req.json();
  const stream = anthropic.messages.stream({
    model: "claude-sonnet-4-6",
    max_tokens: 4096,
    messages,
  });
  return new Response(stream.toReadableStream());
}
```

### Conversation Storage
```
conversations: { id, user_id, title, created_at, updated_at }
messages: { id, conversation_id, role, content, token_count, created_at }
tool_calls: { id, message_id, tool_name, input, output, status }
```

## Guidelines
- Never expose Anthropic API key to the client
- Implement per-user rate limiting (requests/min, tokens/day)
- Store conversation history in database, not just in memory
- Use streaming (SSE) for all AI responses — never block
- Validate all user inputs before sending to Claude
- Implement request timeout for AI calls (max 120s)
- Log token usage per request for cost tracking
- Use job queues for tasks > 30s (document processing, batch analysis)
- Cache repeated AI calls with same input hash
- Implement graceful degradation when Claude API is down
- Use webhook callbacks for async AI task completion

## Security
- Sanitize user inputs before injecting into prompts (prompt injection prevention)
- Never log full conversation content in production
- Implement content filtering for harmful outputs
- Rate limit by IP and authenticated user
- Store API keys in environment variables only
