# AI Newsroom: Multi-Agent Stateful Workflow

An autonomous web application engineered with **Flask** and **Backboard API** in a Linux (Ubuntu) environment. The system orchestrates 3 specialized AI agents (*Researcher*, *Writer*, *Editor*) operating in a closed-loop review and revision relay.

## Context

Developed for **MLH (Major League Hacking) Challenge 6: Multi-Agent Systems**. The goal was to engineer an end-to-end multi-agent relay application using a single-shot prompt and environment-secured stateful API calls.

 ## Tech Stack
 
Backend Framework: Python 3.12 / Flask

AI Orchestration: Backboard API

Frontend: HTML5, CSS3, JavaScript

Environment: Ubuntu (WSL2 / Linux)

---

##  Architecture & Workflow

The application executes a stateful, four-stage feedback loop:

│  Researcher  │ ──> Extracts 5 key technical facts

│
▼

│    Writer    │ ──> Generates 1st article draft using facts

│
▼

│    Editor    │ ──> Performs critique & provides 3 revisions

│
▼

│ Writer (Rev) │ ──> Re-evaluates critique & outputs final article


## Key Features

* **Specialized Agent Personas**: Segregates tasks into dedicated research, drafting, and editorial roles.
* **Stateful Thread Isolation**: Uses Backboard API thread management to prevent context drift.
* **Closed-Loop Feedback**: Automated revision step applies editor notes to produce a refined final output.
* **Responsive Single-Page UI**: Dark-mode tabbed interface rendering real-time execution steps.
* **Environment-Based Security**: Complete key isolation via Linux environment variables.

---

## One-Shot Engineering Prompt

```text
Build a complete multi-agent web app called "AI Newsroom" in Python using Flask and HTML/CSS/JS.

Requirements:
* All AI calls use the backboard-sdk Python package utilizing the `BACKBOARD_API_KEY` environment variable.
* Create 3 distinct agent assistants:
  1. Researcher: System prompt to find 5-7 key technical facts with web search enabled.
  2. Writer: System prompt to draft a news article from those facts.
  3. Editor: System prompt to provide 3 critique points, after which the Writer revises the draft once.
* Workflow: Topic POSTed -> Researcher gets facts -> Writer drafts -> Editor critiques -> Writer revises -> Return JSON with all 4 outputs.
* UI: Single-page dark theme app with topic input, live status bar, and 4 tabbed result views (Facts, First Draft, Editor Notes, Final Article).
* Output app.py, templates/index.html, and requirements.txt.
```
## Results
<img width="1917" height="947" alt="Screenshot 2026-08-26 100427" src="https://github.com/user-attachments/assets/2082f33c-7ab8-485f-be34-d7f443ce3042" />
<img width="1917" height="965" alt="Screenshot 2026-08-26 100433" src="https://github.com/user-attachments/assets/cf3853e9-f1eb-482f-8f97-c4ab2d696572" />
<img width="1902" height="963" alt="Screenshot 2026-08-26 100438" src="https://github.com/user-attachments/assets/042c98dc-36e1-454e-86cc-8e2c9f2bc00c" />
<img width="1916" height="960" alt="Screenshot 2026-08-26 100443" src="https://github.com/user-attachments/assets/a805502d-20b2-4ac6-9047-44e9a00ee8d8" />





