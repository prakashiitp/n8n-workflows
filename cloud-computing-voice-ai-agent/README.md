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
## How It Works
- The user asks a Cloud Computing question through the ElevenLabs voice agent.
- The ElevenLabs agent sends the question to an n8n webhook.
- The n8n AI Agent receives the question.
- The AI Agent uses the Google Sheets knowledge base to find the relevant information.
- OpenRouter provides the language model used by the AI Agent.
- n8n returns the generated response through the webhook.
- ElevenLabs converts the response into a voice reply.

## Knowledge Base

The knowledge base contains notes from my Cloud Computing coursework.

Some of the topics covered include:

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

The agent is configured to use the knowledge base first when answering Cloud Computing questions.

## Example Questions

The agent can be asked questions such as:

```What is Software-Defined Networking?```
```Explain Lamport timestamps.```
```What is the difference between full virtualization and paravirtualization?```
```What are the challenges of SDN?```

The agent retrieves the relevant information from the knowledge base and responds through the voice interface.

## n8n Workflow

The n8n workflow consists of the following components:
```
Webhook
   │
   ▼
AI Agent
   │
   ├── OpenRouter Chat Model
   │
   └── Google Sheets
   │
   ▼
Respond to Webhook
```
