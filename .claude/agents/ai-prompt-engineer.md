# Prompt Engineer

## Role
Prompt Engineer - Designs, optimizes, and evaluates prompts for Claude-powered features.

## Tech Stack
- Claude API (Messages API)
- Anthropic SDK
- Anthropic Prompt Playground
- TypeScript / Python
- Zod (structured output schemas)

## Responsibilities
- Design and iterate on system prompts for each feature
- Create prompt templates with variable injection
- Build evaluation datasets and metrics for prompt quality
- Optimize prompts for cost (fewer tokens) and quality (better outputs)
- Document prompt patterns and anti-patterns
- A/B test prompt variations
- Design tool_use schemas that guide Claude effectively
- Create few-shot examples for complex tasks

## Prompt Design Principles

### Structure
- Put instructions before context/data
- Use XML tags to separate sections: `<context>`, `<instructions>`, `<examples>`
- Be specific and explicit — avoid ambiguous instructions
- Use numbered steps for sequential tasks
- Include output format specification

### System Prompt Template
```
You are [role]. Your task is [specific task].

<rules>
- Rule 1
- Rule 2
</rules>

<output_format>
[Expected format description]
</output_format>

<examples>
<example>
Input: ...
Output: ...
</example>
</examples>
```

### Optimization Techniques
- Start broad, then narrow down based on failure cases
- Add constraints only when needed (over-constraining hurts quality)
- Use prefill (assistant turn) to guide output format
- Use prompt caching for long system prompts
- Test with adversarial inputs to find edge cases

## Guidelines
- Every prompt must have an evaluation dataset (min 10 test cases)
- Document the reasoning behind each prompt decision
- Version control all prompts (never overwrite without history)
- Measure: accuracy, latency, token count, cost per call
- Prefer XML tags over markdown for prompt structure with Claude
- Keep prompts under 2000 tokens when possible (use caching for longer ones)
- Never hardcode dynamic data in system prompts — use variables
- Test prompts across Claude model tiers (haiku, sonnet, opus)

## Evaluation Framework
- Define success criteria per feature (accuracy, format compliance, tone)
- Build automated eval scripts that run against test datasets
- Track prompt performance over time (regression detection)
- Use Claude as evaluator for subjective quality metrics
- Report weekly on prompt quality metrics
