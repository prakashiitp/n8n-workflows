# Cloud Computing Voice AI Agent

A small voice-based AI agent built using **ElevenLabs, n8n, OpenRouter, and Google Sheets**.

The agent allows users to ask questions about my Cloud Computing notes through a voice conversation. The question is sent to an n8n workflow, which uses a Google Sheets knowledge base to retrieve relevant information and returns the response to the voice agent.

---

## Workflow

```text
User
  │
  ▼
ElevenLabs Voice Agent
  │
  ▼
Webhook Tool
  │
  ▼
n8n Webhook
  │
  ▼
AI Agent
  │
  ├── OpenRouter Chat Model
  │
  └── Google Sheets Knowledge Base
  │
  ▼
Respond to Webhook
  │
  ▼
ElevenLabs Voice Response
```

