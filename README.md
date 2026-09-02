<!-- ============================================================
  AGENCY BRAIN
  Modular architecture for persistent, tool-using AI agents.
============================================================= -->

<div align="center">

<img src="./docs/assets/agency-brain-hero.png" alt="Agency Brain" width="520"/>

# Agency Brain 🧠

### **A modular brain for persistent, tool-using AI agents.**

**Memory · Tools · RAG · Automation · Providers · Sessions · Integrations**

<br>

[![STATUS](https://img.shields.io/badge/STATUS-ACTIVE_DEVELOPMENT-00D9FF?style=for-the-badge&labelColor=0B0F17)](https://github.com/FabrizioCondesBallesteros/agency-brain)
[![PYTHON](https://img.shields.io/badge/PYTHON-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=0B0F17)](https://www.python.org/)
[![DOCKER](https://img.shields.io/badge/DOCKER-READY-2496ED?style=for-the-badge&logo=docker&logoColor=white&labelColor=0B0F17)](https://www.docker.com/)
[![AI AGENTS](https://img.shields.io/badge/AI-AGENTS-00E5C4?style=for-the-badge&labelColor=0B0F17)](#-agentic-core)
[![RAG](https://img.shields.io/badge/RAG-READY-7C3AED?style=for-the-badge&labelColor=0B0F17)](#-memory--knowledge)
[![LICENSE](https://img.shields.io/badge/LICENSE-EXPERIMENTAL-orange?style=for-the-badge&labelColor=0B0F17)](#-license)

<br>

[![GitHub stars](https://img.shields.io/github/stars/FabrizioCondesBallesteros/agency-brain?style=flat-square&logo=github&label=STARS)](https://github.com/FabrizioCondesBallesteros/agency-brain/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/FabrizioCondesBallesteros/agency-brain?style=flat-square&logo=github&label=FORKS)](https://github.com/FabrizioCondesBallesteros/agency-brain/network/members)
[![GitHub issues](https://img.shields.io/github/issues/FabrizioCondesBallesteros/agency-brain?style=flat-square&logo=github&label=ISSUES)](https://github.com/FabrizioCondesBallesteros/agency-brain/issues)
[![Last commit](https://img.shields.io/github/last-commit/FabrizioCondesBallesteros/agency-brain?style=flat-square&logo=git&label=LAST%20COMMIT)](https://github.com/FabrizioCondesBallesteros/agency-brain/commits)
[![Repo size](https://img.shields.io/github/repo-size/FabrizioCondesBallesteros/agency-brain?style=flat-square&logo=github&label=SIZE)](https://github.com/FabrizioCondesBallesteros/agency-brain)

<br>

[**Overview**](#-overview)
·
[**Architecture**](#-architecture)
·
[**Capabilities**](#-capabilities)
·
[**Memory**](#-memory--knowledge)
·
[**Tools**](#-tools)
·
[**Quick Start**](#-quick-start)
·
[**Roadmap**](#-roadmap)

</div>

---

# ⚡ Overview

**Agency Brain** is an experimental modular architecture for building **persistent AI agents that can remember, reason, use tools, interact with external systems and execute structured workflows.**

The project explores a simple idea:

> **An AI agent should be more than an LLM wrapped inside a chat interface.**

A useful agent needs an actual software architecture around the model.

Agency Brain separates responsibilities such as:

- 🧠 persistent memory
- 🛠️ tool execution
- 🤖 agent logic
- 🔌 external integrations
- 🗂️ session management
- 🔄 orchestration
- 🧩 provider abstraction
- 📚 knowledge retrieval
- ⚖️ deterministic business rules
- ☁️ deployment infrastructure

Instead of building isolated assistants, the objective is to create a reusable **agent foundation** capable of supporting multiple specialized agents and real operational workflows.

---

# 🎯 Mission

Agency Brain investigates how to build AI systems that move through four levels:

```text
CHAT
  ↓
ASSISTANT
  ↓
AGENT
  ↓
OPERATOR

A traditional chatbot answers.

An assistant helps.

An agent can decide which capability to use.

An operator can:

observe
   ↓
reason
   ↓
remember
   ↓
choose tools
   ↓
act
   ↓
observe results
   ↓
update state
   ↓
continue

Agency Brain is designed around that final direction.

🧠 The Idea
                 ┌─────────────────────┐
                 │        USER         │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │     AGENT LAYER     │
                 │                     │
                 │ reasoning · intent  │
                 │ planning · policy   │
                 └──────────┬──────────┘
                            │
              ┌─────────────┼──────────────┐
              │             │              │
              ▼             ▼              ▼
       ┌────────────┐ ┌────────────┐ ┌────────────┐
       │   MEMORY   │ │   TOOLS    │ │   RULES    │
       │            │ │            │ │            │
       │ persistent │ │ APIs       │ │ validation │
       │ semantic   │ │ actions    │ │ policies   │
       │ sessions   │ │ services   │ │ limits     │
       └──────┬─────┘ └──────┬─────┘ └──────┬─────┘
              │              │               │
              └──────────────┼───────────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │  PROVIDER LAYER     │
                  │                     │
                  │ LLMs · embeddings   │
                  │ external models     │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │    INTEGRATIONS     │
                  │                     │
                  │ Telegram · APIs     │
                  │ Calendar · storage  │
                  │ external services   │
                  └─────────────────────┘
🔥 Why Agency Brain?

Modern AI development often begins like this:

response = llm.invoke(prompt)

That is useful.

But a real agentic system quickly needs much more:

Who is the user?

What happened yesterday?

What does this agent know?

Which information should be remembered?

Which tool should be called?

Which actions require approval?

What happens if a tool fails?

Which model should handle the task?

How does an agent maintain state?

How does it communicate with another service?

How do we replace one provider without rewriting everything?

Agency Brain exists to explore those questions as software architecture problems, not just prompting problems.

🧩 Core Philosophy
Principle	Meaning
Modularity	Core capabilities should be interchangeable
Persistence	Agents should retain useful state across sessions
Separation of concerns	Memory, tools, models and rules should not become one monolithic layer
Provider independence	The architecture should not depend permanently on one LLM
Tool-first design	Agents become valuable when they can interact with systems
Human authority	Sensitive or irreversible actions should preserve human control
Observability	Agent actions should be inspectable
Composable intelligence	Specialized capabilities should combine cleanly
Production thinking	Experiments should evolve toward reusable systems
🤖 Agentic Core

At the center of Agency Brain is the Agent Layer.

An agent receives:

context
+
instructions
+
memory
+
available tools
+
business rules

and determines an appropriate execution path.

Conceptually:

result = agent.run(
    input=user_input,
    memory=memory,
    tools=tools,
    rules=rules,
    session=session
)

The agent should not need to know the implementation details of every subsystem.

That responsibility belongs to the architecture.

🧠 Memory & Knowledge

Memory is treated as a first-class subsystem.

Agency Brain explores multiple forms of memory:

Memory Type	Purpose
Conversation Memory	Recent interaction context
Persistent Memory	Information retained between sessions
Semantic Memory	Knowledge retrieved through similarity
Vector Memory	Embedding-based recall
Session State	Current workflow / execution state
User Context	Relevant long-term information
Knowledge Base	External documents and structured information

Potential flow:

User message
    ↓
Memory lookup
    ↓
Relevant context
    ↓
Agent reasoning
    ↓
Tool / response
    ↓
Memory evaluation
    ↓
Persistent storage

Not everything should be remembered.

An intelligent memory architecture must determine:

what to store
what to ignore
what to retrieve
when to retrieve it
when to forget it
📚 RAG

Agency Brain can integrate Retrieval-Augmented Generation patterns.

Documents
    ↓
Processing
    ↓
Chunking
    ↓
Embeddings
    ↓
Vector Store
    ↓
Semantic Search
    ↓
Relevant Context
    ↓
LLM
    ↓
Grounded Response

RAG can support:

private knowledge bases
documentation assistants
company information
technical knowledge
persistent agent knowledge
contextual decision systems
domain-specific agents
🛠️ Tools

Tools allow agents to move from:

"I can tell you how to do it."

to:

"I can do it."

Examples:

search()
send_message()
read_calendar()
create_event()
query_database()
retrieve_memory()
run_script()
call_api()
generate_document()

The architecture aims for a centralized registry:

tool_registry.register(calendar_tool)
tool_registry.register(memory_tool)
tool_registry.register(search_tool)

allowing agents to discover capabilities without hardcoding every integration.

🔌 Integrations

Agency Brain is designed to interact with external systems.

Potential and experimental integration targets include:

Integration	Purpose
Hermes Agent	Agent runtime / experimentation
Telegram	User interaction channel
Google Calendar	Scheduling and calendar operations
SQLite	Persistent local storage
Vector Databases	Semantic memory and RAG
REST APIs	External services
LLM APIs	Reasoning / generation providers
Docker	Portable environments
Cloud Infrastructure	Remote deployment
🧠 Provider Layer

The LLM should be treated as a provider — not as the entire application.

Conceptually:

Agent
  │
  ▼
Provider Interface
  │
  ├── OpenAI
  ├── Anthropic
  ├── Gemini
  ├── Local Model
  └── Future Provider

This reduces architectural coupling.

Example abstraction:

class LLMProvider:
    def generate(self, messages):
        ...

The rest of the system should ideally remain stable even when the underlying model changes.

🔄 Sessions

Agents need continuity.

A session can hold:

session_id
user_id
agent_id
history
working_context
memory_refs
active_tools
execution_state
timestamps

Conceptually:

User
 ↓
Session Manager
 ↓
Existing session?
 ├── YES → restore context
 └── NO  → create session
 ↓
Agent execution
 ↓
persist state
⚖️ Business Rules

LLMs are probabilistic.

Business constraints should not always be.

Agency Brain therefore separates:

AI reasoning

from:

deterministic rules

Examples:

if action.requires_confirmation:
    request_user_approval()

if user_role != "admin":
    deny_action()

if transaction_amount > limit:
    escalate()

This enables safer and more predictable agent behavior.

🏗️ Architecture

The current conceptual architecture is divided into:

Layer	Responsibility
Agent	Agent behavior and execution
Memory	Persistent and semantic context
Tools	Capabilities exposed to agents
Providers	LLM / model abstraction
Sessions	Stateful interactions
Rules	Deterministic constraints
Integrations	External applications and APIs
Config	Environment and runtime configuration

Potential structure:

agency-brain/
│
├── app/
│   │
│   ├── agents/
│   │   ├── base.py
│   │   └── registry.py
│   │
│   ├── memory/
│   │   ├── base.py
│   │   ├── persistent.py
│   │   ├── semantic.py
│   │   └── vector.py
│   │
│   ├── tools/
│   │   ├── base.py
│   │   ├── registry.py
│   │   └── builtins/
│   │
│   ├── providers/
│   │   ├── base.py
│   │   └── providers/
│   │
│   ├── sessions/
│   │   ├── manager.py
│   │   └── models.py
│   │
│   ├── rules/
│   │   └── engine.py
│   │
│   ├── integrations/
│   │   ├── telegram/
│   │   ├── calendar/
│   │   └── storage/
│   │
│   └── config/
│
├── docs/
│   ├── assets/
│   │   └── agency-brain-hero.png
│   │
│   ├── architecture.md
│   ├── agents.md
│   ├── memory.md
│   ├── tools.md
│   ├── providers.md
│   └── roadmap.md
│
├── examples/
│   ├── personal-agent/
│   ├── telegram-agent/
│   └── rag-agent/
│
├── tests/
├── scripts/
│
├── .env.example
├── .gitignore
├── Dockerfile
├── docker-compose.yml
├── pyproject.toml
├── README.md
└── LICENSE
✨ Capabilities
Capability	Description	Status
🧠 Agent Architecture	Reusable agent-oriented architecture	✅
🗂️ Session Management	Persistent conversational sessions	🚧
🧠 Persistent Memory	Cross-session memory	🚧
🔎 Semantic Memory	Embedding-based retrieval	🧪
📚 RAG	Knowledge retrieval pipelines	🧪
🛠 Tool Registry	Centralized agent tools	🚧
🧩 Provider Abstraction	Decoupled model provider layer	🚧
⚖ Business Rules	Deterministic system constraints	🚧
🔌 External Integrations	APIs and external systems	🧪
🐳 Docker	Containerized development	✅
📱 Telegram	Messaging integration	📋
📅 Calendar	Scheduling integration	📋
☁️ Cloud Deployment	Remote runtime	📋
🤝 Multi-Agent	Agent collaboration	🔬
Status Legend
Symbol	Meaning
✅	Implemented
🚧	In progress
🧪	Experimental
📋	Planned
🔬	Research

Statuses should be updated as the implementation evolves.

🧬 Technology Landscape
<div align="center">



















</div>
🚀 Quick Start
Requirements

Recommended:

Python >= 3.11
Git
Docker
Docker Compose
uv
Clone
git clone https://github.com/FabrizioCondesBallesteros/agency-brain.git
cd agency-brain
Environment

Create your local environment file:

cp .env.example .env

Example:

# ====================================
# Agency Brain
# ====================================

APP_ENV=development

# LLM Provider
LLM_PROVIDER=openai

# API keys
OPENAI_API_KEY=

# Memory
MEMORY_BACKEND=sqlite
DATABASE_URL=sqlite:///data/agency_brain.db

# Vector Memory
VECTOR_STORE=

# Logging
LOG_LEVEL=INFO

# Integrations
TELEGRAM_BOT_TOKEN=

# Google
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=

Never commit secrets.

📦 Installation

Using uv:

uv sync

Activate environment if required:

source .venv/bin/activate

Windows:

.venv\Scripts\Activate.ps1

Alternative:

pip install -e .
▶️ Run

Example:

python -m app

or:

uv run python -m app
🐳 Docker

Build:

docker build -t agency-brain .

Run:

docker run --env-file .env agency-brain

With Compose:

docker compose up --build

Background:

docker compose up -d

Stop:

docker compose down

Logs:

docker compose logs -f
🧪 Testing

Run the test suite:

pytest

Verbose:

pytest -v

Coverage:

pytest --cov=app

Target areas:

agents
memory
tools
providers
sessions
integrations
business rules
🧰 Development Commands
Task	Command
Install	uv sync
Run	uv run python -m app
Tests	uv run pytest
Docker Build	docker compose build
Docker Run	docker compose up
Stop	docker compose down
Logs	docker compose logs -f
🧪 Example Agent Flow
USER
 │
 │ "Schedule a meeting with Alex next week."
 ▼
AGENT
 │
 ├── Understand intent
 │
 ├── Retrieve user preferences
 │
 ├── Identify Calendar tool
 │
 ├── Check availability
 │
 ├── Apply scheduling rules
 │
 └── Request confirmation
 ▼
TOOL
 │
 └── Calendar API
 ▼
RESULT
 │
 └── Event created
 ▼
MEMORY
 │
 └── Store useful interaction context
 ▼
USER

This is the type of workflow Agency Brain aims to make reusable.

🧠 Specialized Agents

The architecture can evolve toward multiple specialized agents:

Agency Brain
│
├── Personal Agent
│
├── Calendar Agent
│
├── Research Agent
│
├── Career Agent
│
├── Data Agent
│
├── Fitness Agent
│
├── Automation Agent
│
└── Custom Agents

Every agent can potentially share:

memory
providers
tools
identity
authentication
sessions
infrastructure

while maintaining its own:

rules
objectives
skills
context
workflows
🕸 Multi-Agent Direction

Future architecture may support:

                    ORCHESTRATOR
                         │
       ┌─────────────────┼─────────────────┐
       │                 │                 │
       ▼                 ▼                 ▼
 RESEARCH AGENT     DATA AGENT       ACTION AGENT
       │                 │                 │
       └─────────────────┼─────────────────┘
                         │
                         ▼
                    SHARED MEMORY
                         │
                         ▼
                     TOOL LAYER

The project does not assume that every problem needs multiple agents.

Multi-agent systems should be used only when specialization provides measurable value.

🧠 Memory Strategy

A possible memory hierarchy:

L0 — Working Context
│
├── immediate conversation
│
▼
L1 — Session Memory
│
├── current objectives
├── tool results
│
▼
L2 — Persistent Memory
│
├── preferences
├── reusable facts
├── history
│
▼
L3 — Semantic Memory
│
├── embeddings
├── similarity retrieval
│
▼
L4 — External Knowledge
    ├── documents
    ├── databases
    └── APIs

Different information deserves different retention policies.

🔐 Security Principles

Agent systems require explicit trust boundaries.

Agency Brain should follow principles such as:

secrets never committed to repositories
environment-based credentials
minimum required permissions
confirmation before high-impact actions
tool-level authorization
input validation
auditability
clear separation between reasoning and execution

Conceptually:

Agent wants action
      ↓
Tool policy
      ↓
Permission check
      ↓
Risk classification
      ↓
Confirmation if required
      ↓
Execution
👁 Observability

Agentic software must be inspectable.

Useful signals include:

session
agent
model
tool
latency
tokens
memory retrieval
errors
tool arguments
tool results
execution path

Future instrumentation may include:

structured logs
execution traces
model telemetry
tool latency
token usage
memory retrieval metrics
error tracking
📊 Evaluation

Agents should be measured by outcomes rather than demos.

Possible metrics:

Metric	Question
Task Success	Did the agent accomplish the objective?
Tool Accuracy	Did it choose the correct tool?
Retrieval Quality	Was relevant memory retrieved?
Latency	How long did execution take?
Cost	How expensive was the run?
Reliability	Does the workflow behave consistently?
Intervention Rate	How often was human correction required?
🗺 Roadmap
Phase 0 — Architecture
 Define project direction
 Define Core / Agent / Tool / Provider responsibilities
 Establish modular architecture principles
 Create repository foundation
Phase 1 — Environment
 GitHub repository
 Development environment
 Docker experimentation
 Hermes integration research
 Provider experimentation
 Stable reproducible setup
Phase 2 — Core Framework
 Agent Interface
 Memory Layer
 Tool Registry
 Business Rules
 LLM Provider
 Session Manager
 Configuration Layer
Phase 3 — First Real Agent
 Telegram interface
 Google Calendar
 Persistent storage
 Tool execution
 Session continuity
 Real user workflow
Phase 4 — Intelligence Layer
 Semantic memory
 Vector retrieval
 RAG
 Dynamic tool selection
 Structured planning
 Context management
Phase 5 — Agent Platform
 Specialized agents
 Shared memory
 Shared tool registry
 Agent orchestration
 Agent permissions
 Workflow engine
Phase 6 — Production
 Cloud deployment
 Observability
 Authentication
 Authorization
 Security hardening
 Automated testing
 CI/CD
 Monitoring
 Failure recovery
💡 Potential Use Cases

Agency Brain can serve as the architectural foundation for:

Personal AI Assistant

Persistent personal agent capable of remembering context and interacting with external services.

Career Operator

Agent capable of researching opportunities, evaluating companies, organizing applications and preparing outreach.

Knowledge Assistant

RAG-powered assistant grounded in private documentation.

Business Automation Agent

Agent connected to internal tools and operational workflows.

SaaS AI Layer

Reusable agent capabilities embedded into a larger software product.

Research Agent

Autonomous research workflows combining search, retrieval, analysis and memory.

Scheduling Agent

Agent capable of coordinating calendars, availability and reminders.

Data Agent

AI interface over datasets, databases and analytical tools.

🔬 Research Questions

Agency Brain is also a laboratory for exploring questions such as:

How should agent memory be structured?

When should information become persistent?

How should agents select tools?

How much autonomy should an agent have?

How do we separate model reasoning from business rules?

When are multiple agents better than one?

How should agent identity and memory migrate between runtimes?

Can agent state survive a change of model provider?

Can one persistent identity operate through multiple interfaces?

How should agent permissions evolve?

What should remain deterministic?

What should remain probabilistic?
🧭 Long-Term Direction

The long-term idea is not simply:

one bot

but potentially:

                    AGENCY BRAIN
                         │
               Shared Intelligence Core
                         │
          ┌──────────────┼──────────────┐
          │              │              │
       MEMORY          TOOLS         IDENTITY
          │              │              │
          └──────────────┼──────────────┘
                         │
                  AGENT RUNTIMES
                         │
        ┌────────────────┼────────────────┐
        │                │                │
     Desktop          Telegram          SaaS
        │                │                │
        └────────────────┼────────────────┘
                         │
                     same brain

The interface may change.

The provider may change.

The model may change.

The agent's useful accumulated context and architecture should not necessarily disappear with them.

🧱 What Agency Brain Is NOT

Agency Brain is not currently presented as:

a production-ready framework
a replacement for every agent framework
a finished autonomous operating system
a benchmark winner
a fully autonomous general intelligence system

It is an evolving engineering project focused on understanding and building reusable agent infrastructure.

Transparency matters.

🧑‍💻 Contributing

Ideas, experiments, architecture discussions and contributions are welcome.

Recommended process:

1. Fork
2. Create branch
3. Implement scoped change
4. Add documentation
5. Add tests when applicable
6. Open pull request

Example:

git checkout -b feat/vector-memory

Commit:

git commit -m "feat: add vector memory provider"

Push:

git push origin feat/vector-memory
🌿 Git Convention

Suggested commit convention:

feat:     new capability
fix:      bug fix
docs:     documentation
refactor: architecture improvement
test:     tests
chore:    maintenance
perf:     performance
build:    build / Docker / dependencies

Examples:

feat: add persistent session storage
feat: register calendar tool
docs: explain agent architecture
refactor: extract provider interface
test: add memory retrieval tests
fix: handle missing session state
🤝 Contributions Philosophy

Prefer:

small
clear
modular
documented
testable
reusable

over:

large
opaque
tightly coupled
one-off implementations
📖 Documentation

Planned documentation:

Document	Purpose
architecture.md	System architecture
agents.md	Agent lifecycle
memory.md	Memory architecture
tools.md	Tool registry
providers.md	LLM providers
sessions.md	Session management
security.md	Security boundaries
integrations.md	External integrations
roadmap.md	Development roadmap
🧠 Architectural Rule

One of the project's core rules:

The LLM is a component of the system — not the system itself.

The architecture should survive:

model changes
provider changes
API changes
tool changes
interface changes
deployment changes

without requiring the entire project to be rewritten.

⭐ If You Find This Interesting

If you're also exploring:

AI Agents
RAG
Agent Memory
Tool Calling
Agentic AI
Automation
LLM infrastructure
AI SaaS
Persistent agents
AI architecture

consider starring the repository.

<div align="center">






</div>
👤 Author
<div align="center">
Fabrizio Condes Ballesteros

Information Technology · Artificial Intelligence · Agents · Software · Data




</div>
📜 License

This project is currently under active experimentation.

Before broader distribution or external contribution, define the final open-source license in the repository.

Common options include:

MIT
Apache-2.0
BSD-3-Clause

Do not assume licensing rights for external dependencies included or integrated with this project.

<div align="center"> <br>
🧠 AGENCY BRAIN
Memory gives agents continuity.
Tools give them capability.
Architecture gives them a future.
<br>










<br>

Built as an exploration of what comes after the chatbot.

</div> ```
