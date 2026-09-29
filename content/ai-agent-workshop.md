# AI Agent Workshop

Source: https://github.com/AnorakAdrianyc/ai-agent-workshop

Mastra workshop: Weather Agent + Open-Meteo + calculator tool + activity workflow + scorers.

## Features

- Conversational weather agent with non-English location translation
- Tools: `weatherTool`, `calculatorTool`
- Workflow: `fetchWeather` then `planActivities`
- Scorers: tool-call appropriateness, completeness, translation quality
- LibSQL memory, Pino logs, Ollama via `OLLAMA_API_URL` / `MODEL_NAME_AT_ENDPOINT`

## Stack

Node 20.9+, TypeScript 5, `@mastra/core` ^0.23.3, evals, libsql, memory, zod, `ollama-ai-provider-v2`.

```bash
npm install
cp .env.example .env
npm run dev
```

Docker: `node:20-alpine`, ports 3000 and 4111. License ISC.
