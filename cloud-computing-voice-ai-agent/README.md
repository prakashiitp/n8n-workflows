# Cloud Computing Voice AI Agent

A small voice-based AI agent built with **ElevenLabs, n8n, OpenRouter, and Google Sheets**.

The agent allows users to ask questions about my Cloud Computing notes through a voice conversation. The question is sent to an n8n workflow, which retrieves the relevant information from a Google Sheets knowledge base and returns the answer to the voice agent.

---

## Workflow

```text
User
  │
  ▼
ElevenLabs Voice Agent
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
## How It Works
- The user asks a Cloud Computing question through the voice agent.
- ElevenLabs sends the user's query to an n8n webhook.
- The n8n AI Agent receives the question.
- The AI Agent uses the Google Sheets knowledge base to retrieve relevant information.
- OpenRouter generates the response using the retrieved information.
- n8n returns the response through the webhook.
- ElevenLabs converts the response into a voice reply.

## Knowledge Base

The knowledge base contains notes from my Cloud Computing coursework, including:

- Cloud Computing & Virtualization
- Software-Defined Networking
- Distributed Systems
- Cloud Storage & NoSQL
- Peer-to-Peer Systems
- Cloud Applications
- MapReduce
- Apache Spark
- Apache Kafka
- Leader Election
- Clock Synchronization
- Cassandra
- HBase
- Virtualization
- Docker
- Network Virtualization
- Distributed Algorithms
- Distributed Hash Tables (DHTs)

The goal is to make the agent answer questions using the documented course material rather than relying only on general model knowledge.

