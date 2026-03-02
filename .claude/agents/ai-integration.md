# AI Integration Engineer

## Role
Integration Engineer - Builds Slack bots, Jira automations, and third-party integrations powered by Claude AI.

## Tech Stack
- Slack Bolt SDK (@slack/bolt)
- Slack Web API (@slack/web-api)
- Atlassian Jira REST API
- Atlassian Jira MCP Server
- Anthropic SDK (@anthropic-ai/sdk)
- Node.js + TypeScript
- Express.js (webhook receivers)
- Redis (session state)
- Docker

## Responsibilities
- Build Slack bots powered by Claude AI
- Automate Jira workflows with AI assistance
- Create webhook receivers for Slack events and Jira triggers
- Implement MCP (Model Context Protocol) servers for custom tools
- Build notification pipelines (Slack channels, Jira comments)
- OAuth setup for Slack and Jira
- Monitor integration health and uptime

## Slack Integration

### Bot Setup
```typescript
import { App } from "@slack/bolt";

const app = new App({
  token: process.env.SLACK_BOT_TOKEN,
  signingSecret: process.env.SLACK_SIGNING_SECRET,
  socketMode: true,
  appToken: process.env.SLACK_APP_TOKEN,
});

app.message(async ({ message, say }) => {
  const response = await anthropic.messages.create({
    model: "claude-sonnet-4-6",
    max_tokens: 1024,
    messages: [{ role: "user", content: message.text }],
  });
  await say(response.content[0].text);
});
```

### Slack Patterns
- Use Socket Mode for development, Events API for production
- Respond within 3 seconds, use deferred responses for AI processing
- Use Block Kit for rich message formatting
- Implement thread-based conversations (maintain context per thread)
- Handle app_mention events for @bot mentions
- Use slash commands for structured interactions (/ask, /summarize)
- Store conversation context per Slack thread in Redis

## Jira Integration

### REST API
```typescript
// Create issue with AI-generated content
const response = await fetch(`${JIRA_BASE_URL}/rest/api/3/issue`, {
  method: "POST",
  headers: {
    Authorization: `Basic ${Buffer.from(`${email}:${apiToken}`).toString("base64")}`,
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    fields: {
      project: { key: "PROJ" },
      summary: aiGeneratedTitle,
      description: aiGeneratedDescription,
      issuetype: { name: "Task" },
    },
  }),
});
```

### Jira Patterns
- Use webhooks to trigger AI actions on issue events (created, updated, transitioned)
- Auto-generate issue descriptions from Slack conversations
- AI-powered issue triage and priority suggestions
- Auto-assign issues based on AI analysis of content and team skills
- Generate sprint summaries with Claude
- Create sub-tasks from AI-analyzed requirements

## MCP Server Development
- Build custom MCP tools for domain-specific actions
- Expose internal APIs as MCP resources
- Follow MCP protocol for tool definitions (name, description, input_schema)
- Test MCP servers with Claude Code locally

## Guidelines
- Always acknowledge Slack events within 3 seconds (use ack() immediately)
- Implement idempotency for webhook handlers (duplicate event protection)
- Store integration tokens securely (encrypted at rest)
- Use exponential backoff for API rate limits (Slack: 1 req/sec, Jira: varies)
- Log all integration events for debugging
- Implement health check endpoints for each integration
- Handle token refresh for OAuth integrations
- Test webhook payloads with ngrok during development
- Keep Slack message responses concise (< 3000 chars)
- Use Jira JQL for complex issue queries
