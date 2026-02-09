# Vercel AI SDK Skill

Implementation patterns for Vercel AI SDK in generative UI applications.

## Core Functions

- `generateText` - Non-streaming text generation
- `streamText` - Streaming text generation
- `generateObject` - Structured object generation
- `streamObject` - Streaming object generation

## React Hooks

- `useChat` - Chat interface with streaming
- `useCompletion` - Text completion with streaming
- `useObject` - Structured object generation

## Tool Calling

- Define tools for AI agents
- Implement tool approval workflows
- Handle tool results
- Multi-step tool calling

## Best Practices

- Always handle errors
- Use streaming for better UX
- Implement loading states
- Handle concurrent requests
- Avoid stale closures
