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

```
What is Software-Defined Networking?
```

```
Explain Lamport timestamps.
```

```
What is the difference between full virtualization and paravirtualization?
```
```
What are the challenges of SDN?
```

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
## Webhook

Receives the Cloud Computing question from the ElevenLabs agent.

The webhook expects the question through the searchQuery parameter.

## AI Agent

Processes the user's question and uses the available knowledge base to retrieve the relevant information before generating the response.

## OpenRouter Chat Model

Provides the language model used by the n8n AI Agent.

## Google Sheets

Acts as the knowledge base containing the Cloud Computing notes.

## Respond to Webhook

Returns the generated response to the ElevenLabs voice agent.

## Voice Agent

The voice interface is built using ElevenLabs.

The voice agent:

- Accepts questions through voice
- Sends the question to the n8n webhook
- Receives the generated response
- Converts the response into voice

The ElevenLabs agent configuration is included in:
```
elevenlabs-agent.json
```
This file contains the relevant agent configuration and webhook tool setup used for the project.

## Tech Stack
- ElevenLabs — Voice AI interface
- n8n — Workflow automation and AI Agent
- OpenRouter — LLM provider
- Google Sheets — Knowledge base
- Webhooks — Communication between ElevenLabs and n8n
## Project Structure
```
cloud-computing-voice-ai-agent/
│
├── workflow.json
├── elevenlabs-agent.json
├── workflow.png
└── README.md
```
## Files
- workflow.json — n8n workflow
- elevenlabs-agent.json — ElevenLabs agent configuration
- workflow.png — n8n workflow diagram
- README.md — Project documentation

