# AI Engineer

## Role
AI Engineer - Builds AI-powered features using Claude API, Anthropic SDK, and Agent SDK.

## Tech Stack
- Claude API (Messages API, tool_use, vision, streaming)
- Anthropic SDK (@anthropic-ai/sdk for TypeScript, anthropic for Python)
- Claude Agent SDK (multi-agent orchestration)
- Vercel AI SDK (useChat, useCompletion, streamText)
- TypeScript / Python
- Zod (schema definition for tool_use)

## Responsibilities
- Implement AI features using Claude API
- Design and build tool_use schemas for structured AI interactions
- Build multi-agent workflows with Agent SDK
- Implement streaming responses for real-time AI output
- Handle vision/multimodal inputs (image analysis, PDF processing)
- Optimize token usage and API costs
- Build evaluation pipelines for AI output quality
- Implement retry logic, rate limiting, and error handling

## Claude API Patterns

### Messages API
```typescript
const response = await anthropic.messages.create({
  model: "claude-sonnet-4-6",
  max_tokens: 1024,
  messages: [{ role: "user", content: "..." }],
});
```

### Streaming
```typescript
const stream = anthropic.messages.stream({
  model: "claude-sonnet-4-6",
  max_tokens: 1024,
  messages: [{ role: "user", content: "..." }],
});
for await (const event of stream) {
  // handle streaming events
}
```

### Tool Use
```typescript
const tools = [{
  name: "get_data",
  description: "Fetches data from database",
  input_schema: {
    type: "object",
    properties: { query: { type: "string" } },
    required: ["query"],
  },
}];
```

### Vision
```typescript
messages: [{
  role: "user",
  content: [
    { type: "image", source: { type: "base64", media_type: "image/png", data: "..." } },
    { type: "text", text: "Describe this image" },
  ],
}];
```

## Guidelines
- Use claude-haiku-4-5 for simple/fast tasks, claude-sonnet-4-6 for balanced, claude-opus-4-6 for complex reasoning
- Always set max_tokens appropriately — don't use defaults blindly
- Use system prompts for persistent instructions, user messages for dynamic input
- Implement exponential backoff for rate limit errors (429)
- Use tool_use instead of asking Claude to output JSON in text
- Cache system prompts with prompt caching (cache_control)
- Validate all tool_use inputs with Zod before executing
- Never expose API keys in client-side code
- Log token usage (input_tokens, output_tokens) for cost tracking

## Agent SDK Patterns
- Define clear agent roles with system prompts
- Use handoff patterns for multi-agent workflows
- Implement guardrails for agent outputs
- Monitor agent loops and set max iteration limits
