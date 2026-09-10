# Repo Doctor — AI GitHub Repository Auditor

Repo Doctor is an AI-powered GitHub repository auditing agent built with **n8n** and **Telegram**.

The user sends a public GitHub repository link through Telegram, and the agent inspects the repository using the GitHub REST API and available AI tools. It then generates a structured repository audit with scores, strengths, issues, and recommended improvements.

---

## Workflow

```text
User
  │
  ▼
Telegram
  │
  ▼
AI Agent
  │
  ├── GitHub REST API
  │     ├── Repository Information
  │     ├── Repository Files & Folders
  │     └── File Contents
  │
  ├── Tavily Search
  │
  ├── Simple Memory
  │
  └── Calculator
  │
  ▼
Telegram Response
```
# What It Does

Send a public GitHub repository link to the Telegram bot.

Example:
```
https://github.com/prakashiitp/n8n-workflows

Audit this repository.
```
Repo Doctor then analyzes the repository and returns an audit containing:

- Architecture score
- Documentation score
- Code/Workflow Quality score
- Security score
- Portfolio Value score
- Overall score
- Strengths
- Issues
- Top improvements
- Recruiter impression

Example Output

```
REPO DOCTOR

Repository: prakashiitp/n8n-workflows

Overall Score: 7/10

Architecture: 7/10
Documentation: 8/10
Code/Workflow Quality: 7/10
Security: 6/10
Portfolio Value: 7/10

Strengths:
- Well-organized repository structure
- Practical AI and automation workflows
- Multiple real-world use cases

Issues:
- Limited workflow testing
- No dedicated CI/CD validation
- Security practices can be improved

Top 3 Improvements:
1. Add workflow testing and validation
2. Improve security practices
3. Add more detailed workflow status

Recruiter Impression:
A practical portfolio demonstrating experience with
AI agents, automation and modern integrations.
```
