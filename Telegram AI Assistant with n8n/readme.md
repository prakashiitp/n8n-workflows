# Telegram AI Assistant with n8n

An AI Agent workflow built with **n8n** that works directly through **Telegram**.

The assistant can handle normal conversations as well as **PDF documents**. It can receive a PDF through Telegram, retrieve the file, extract its text, analyze the content using an AI Agent, and send the response back to the user.

## Workflow

```text
Telegram Trigger
       │
       ▼
      IF
   ┌───┴──────────────┐
   │                  │
Text Message        PDF File
   │                  │
   ▼                  ▼
AI Agent           Get File
   │                  │
   │                  ▼
   │            Extract from PDF
   │                  │
   │                  ▼
   │              AI Agent
   │                  │
   └────────┬─────────┘
            ▼
     Send Telegram Message
```
## Features

- Chat with an AI Agent directly through Telegram.
- Detect and handle PDF file messages.
- Retrieve uploaded files using Telegram.
- Extract text from PDF documents.
- Analyze extracted PDF content using an AI Agent.
- Generate short and useful document summaries.
- Maintain conversational context using Simple Memory.
- Perform calculations using the Calculator tool.
- Search the web using Tavily.
- Make external HTTP requests.
- Use OpenRouter as the AI model provider.
- Return both normal chat responses and document analysis through Telegram.

## Tech Stack

- n8n
- Telegram
- AI Agent
- OpenRouter
- Simple Memory
- PDF Text Extraction
- Calculator
- Tavily Search
- HTTP Request

## Architecture

The workflow is divided into two paths based on the incoming Telegram message.

Text Message

```
Telegram
   │
   ▼
Telegram Trigger
   │
   ▼
IF
   │
   ▼
AI Agent
   │
   ▼
Send Telegram Message
```
The AI Agent handles normal conversations and can use connected tools such as memory, calculator, web search, and HTTP requests when required.

PDF File
```
Telegram
   │
   ▼
Telegram Trigger
   │
   ▼
IF
   │
   ▼
Get File
   │
   ▼
Extract from PDF
   │
   ▼
AI Agent
   │
   ▼
Send Telegram Message
```
When a PDF is received, the workflow retrieves the file and extracts its text before passing the content to the document-analysis AI Agent.

## How It Works

- The user sends a message or PDF through Telegram.
- The **Telegram Trigger** receives the incoming update.
- The **IF** node determines whether the request is a normal message or a PDF file.
- Text messages are sent directly to the main **AI Agent**.
- PDF messages are passed to **Get File** to retrieve the document.
- **Extract from File** extracts the text from the PDF.
- The extracted content is passed to **AI Agent1** for analysis.
- The generated response is sent back to Telegram using **Send a text message**.

### Example

A user can send:

```text
[PDF File]

Explain this PDF in short.
```

The workflow processes the document and returns a concise summary directly in Telegram.

The same assistant can also handle normal requests such as:

```text
What is the difference between REST and GraphQL?
```
## AI Agent Tools

The main AI Agent is connected to several tools:

```text
AI Agent
   │
   ├── OpenRouter Chat Model
   ├── Simple Memory
   ├── Calculator
   ├── Tavily Search
   └── HTTP Request
```

This allows the agent to go beyond simple text generation and interact with tools based on the user's request.

## PDF Analysis Flow

The PDF workflow demonstrates a complete document-processing pipeline:

```text
Telegram File
      ↓
File Retrieval
      ↓
PDF Text Extraction
      ↓
AI Analysis
      ↓
Summary / Answer
      ↓
Telegram
```

This separates file handling, document extraction, and AI processing into individual workflow steps, making the automation easier to understand and extend.

## Screenshots
Complete n8n Workflow

The complete workflow showing Telegram message handling, conditional routing, AI Agents, PDF processing, memory, and external tools.

## PDF Analysis Through Telegram

A PDF is sent through Telegram and processed by the workflow. The extracted content is analyzed by the AI Agent and the response is returned directly in Telegram.

## Normal AI Chat Through Telegram

The same Telegram assistant can also handle normal conversational messages without going through the PDF processing path.

##  Workflow Files
```
telegram-ai-agent/
│
├── workflow.json
├── README.md
├── workflow.png
├── telegram-pdf.png
└── telegram-chat.png
```
Import the workflow JSON into n8n and configure the required credentials.

## What I Learned

While building this project, I learned:

- How to build an AI Agent workflow using n8n.
- How to connect Telegram with an AI Agent.
- How to route different message types using conditional logic.
- How to retrieve files sent through Telegram.
- How to extract text from PDF documents inside an automation workflow.
- How to pass extracted document content to an AI Agent.
- How to connect external tools with an AI Agent.
- How to combine conversational AI and document processing in a single workflow.

The main takeaway was understanding how different automation components can be combined to build a practical AI application:
```
User
 ↓
Telegram
 ↓
n8n Workflow
 ↓
AI Agent / PDF Processing
 ↓
Tools
 ↓
Response
 ↓
Telegram
```
## Future Improvements
- Support additional document formats.
- Add image and document understanding.
- Improve handling of long PDF documents.
- Add voice-message support.
- Add more external tools and APIs.
- Add authentication and user-specific settings.
- Improve conversational memory.

## Import Workflow

Import the workflow JSON into your n8n instance and configure the required credentials.

Required services include:

- Telegram Bot
- OpenRouter
- Tavily

After configuring the credentials, activate the workflow and interact with the assistant through Telegram.

> Note: Do not commit API keys, bot tokens, OAuth credentials, or other sensitive information to the repository.

If you find this workflow useful, consider giving the repository a star.
