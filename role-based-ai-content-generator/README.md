# AI Role-Based Content Generator

An AI-powered n8n workflow that generates personalized two-line poems based on user details using Google Gemini.

---

## Workflow Preview

<img width="1646" height="807" alt="image" src="https://github.com/user-attachments/assets/2c49e925-bb0b-4b27-ac07-ca888f487492" />

---

## Workflow

```text
Form Submission
        ↓
Create Airtable Record
        ↓
Switch (Profession)
        ↓
Update Airtable Record
        ↓
AI Agent
        ↓
Google Gemini
        ↓
Update Poem in Airtable
```

## Features

- n8n Form Trigger
- Airtable Integration
- Conditional Routing using Switch
- AI Agent with Google Gemini
- Automatic Airtable Record Updates
- Dynamic Prompt Generation
- Personalized AI Responses

---

## Tech Stack

- n8n
- Google Gemini
- Airtable
- AI Agent
- Switch Node

---

## Input

- Name
- Profession
- Looks
- Rating

---

## Output

A personalized two-line poem stored automatically in Airtable.

Example:

Prakash is a manager who works every day,
But his bad looks turn people away.

---

## Import

1. Download workflow.json
2. Import into n8n
3. Configure Airtable credentials
4. Configure Gemini API Key
5. Execute the workflow

---

## Files

AI Role-Based Content Generator.json → n8n workflow

workflow.png → Workflow architecture
