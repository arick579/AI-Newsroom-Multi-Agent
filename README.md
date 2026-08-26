# AI Newsroom: Multi-Agent Stateful Workflow

An autonomous web application engineered with **Flask** and **Backboard API** in a Linux (Ubuntu) environment. The system orchestrates 3 specialized AI agents (*Researcher*, *Writer*, *Editor*) operating in a closed-loop review and revision relay.

Tech Stack
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
