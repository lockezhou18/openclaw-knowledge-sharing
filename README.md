# 🤖 OpenClaw Knowledge Sharing Session
### *From Zero to AI Agent — A Beginner's Guide*

---

> **Audience:** Beginners — no prior AI agent or OpenClaw experience needed  
> **Duration:** ~60–90 minutes  
> **Goal:** Understand AI agents conceptually, see OpenClaw in action, and send your first email through it

---

## Table of Contents

1. [What Is an AI Agent?](#1-what-is-an-ai-agent)
2. [Neurological Levels & OpenClaw](#2-neurological-levels--openclaw)
3. [Installing OpenClaw (Claude Example)](#3-installing-openclaw-claude-example)
4. [Send Your First Email](#4-send-your-first-email)
5. [Key Takeaways](#-key-takeaways)
6. [Resources](#-resources)

---

## 1. What Is an AI Agent?

### Chatbot vs. Agent

Most people have used a chatbot. An agent is something more:

| | Chatbot | Agent |
|---|---|---|
| **You say** | "What's the weather?" | "Book me a table for Friday" |
| **It does** | Answers and stops | Plans, acts, checks, repeats |
| **Memory** | Usually none | Remembers context and history |
| **Tools** | None | Email, calendar, web, code... |

---

### The Agent Loop

Every agent — no matter how complex — follows this basic cycle:

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   Perceive → Think → Act → Observe → Repeat        │
│                                                     │
└─────────────────────────────────────────────────────┘
```

| Step | What It Means | Example |
|------|--------------|---------|
| **Perceive** | Reads your message, files, emails, the web | "Send an intro email to John" |
| **Think** | Decides *what to do* using an AI model (Claude, etc.) | "I should draft the email first, then ask for approval" |
| **Act** | Calls tools — email, search, code, files | Drafts email using Gmail tool |
| **Observe** | Reads the result and decides if it's done | "Draft looks good, waiting for approval" |
| **Repeat** | Loops until task is complete or more info is needed | User approves → sends email ✅ |

---

### The "Brain" — AI Models

The AI model (like Claude, GPT-4, or Gemini) is the **reasoning engine**:

- 🧠 The model **decides** what to do
- 🔧 **Tools** actually do the work
- The model never sends an email — it tells the email tool to send one

> **Analogy:** The model is like a brilliant strategist. The tools are the hands that carry out the strategy.

---

### What Makes a Good Agent?

- ✅ **Good memory** — remembers context, past decisions, user preferences
- ✅ **Good tools** — email, calendar, web search, code execution
- ✅ **Good instructions** — a clear persona and rules to follow
- ✅ **Good judgment** — knows when to act vs. when to ask for approval

> 💡 **Think of it like a new hire:**
> You give them a task. They figure out the steps, use the tools at their desk (email, browser, files), and come back when done — or ask if they get stuck. A *great* new hire doesn't just follow orders; they have values, judgment, and care about doing the right thing.

---

## 2. Neurological Levels & OpenClaw

### What Are Neurological Levels?

Robert Dilts' *Neurological Levels* framework describes how humans organize behavior — from the environment we operate in all the way up to our deeper sense of purpose.

It maps surprisingly well to how AI agent systems are designed.

---

### Mapping the Levels to OpenClaw

| Level | Human Context | OpenClaw Context | File |
|-------|--------------|-----------------|------|
| 🌍 **Environment** | Where/when you operate | Your machine, phone, messaging apps | — |
| 🎯 **Behavior** | What you do | Send emails, search web, read files | `HEARTBEAT.md` |
| 🛠️ **Capabilities** | How you do it | Skills, tools, integrations (Gmail, Discord...) | `AGENTS.md` |
| 💡 **Values / Beliefs** | Why it matters | Persona, ethics, what the agent cares about | `SOUL.md` |
| 🪪 **Identity** | Who you are | Agent name, character, purpose | `IDENTITY.md` |
| 🌟 **Mission** | Who/what you serve | Serving the user, acting with integrity | All files |

---

### The Key Insight

> Most tools configure AI at the **behavior** level — *"do this task."*  
> OpenClaw works at **all levels** — you define who the agent *is*, what it *values*, and how it shows up, not just what commands to run.

---

### OpenClaw Workspace Files

When you set up OpenClaw, it creates a **workspace** — a folder of plain text files that define your agent:

```
~/.openclaw/workspace/
├── SOUL.md        ← Persona, tone, values, ethics
├── IDENTITY.md    ← Agent name, character, purpose
├── AGENTS.md      ← Operating instructions, memory system
├── USER.md        ← Who you're helping and their context
├── TOOLS.md       ← Notes about your specific setup
├── HEARTBEAT.md   ← Periodic background tasks
└── MEMORY.md      ← Long-term curated memory
```

These are **just text files**. You can read and edit them. The agent reads them at the start of every session — that's how it knows who it is and how to behave.

---

## 3. Installing OpenClaw (Claude Example)

### Prerequisites

Before you start, make sure you have:

- **Node.js 24** (check with `node --version`)
- A terminal (macOS Terminal, Linux shell, or Windows WSL)
- A **Claude API key** — get one free at [console.anthropic.com](https://console.anthropic.com)

---

### Step 1 — Install OpenClaw

**macOS / Linux:**
```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

**Windows (PowerShell):**
```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

---

### Step 2 — Run the Onboarding Wizard

```bash
openclaw onboard --install-daemon
```

The wizard will ask you:
- Which AI provider to use → choose **Anthropic (Claude)**
- Your **Claude API key** → paste it in
- Basic gateway settings

It sets everything up automatically. ✅

---

### Step 3 — Check the Gateway is Running

The **Gateway** is a background service that runs your agent 24/7:

```bash
openclaw gateway status
```

You should see it running. If not:
```bash
openclaw gateway start
```

---

### Step 4 — Open the Control UI

```bash
openclaw dashboard
```

This opens `http://127.0.0.1:18789/` in your browser — your chat window to the agent.

---

### Step 5 — Say Hello! 👋

Type in the chat:

```
Hello! What can you do?
```

Watch the agent respond — it will describe its capabilities based on your workspace files.

---

### 🔍 What Just Happened Under the Hood

```
Your message
    ↓
Gateway (receives it)
    ↓
Agent loop starts
    ↓
Claude (reads workspace files, thinks about your message)
    ↓
Streams response back
    ↓
Control UI displays it
```

That's the full loop — in milliseconds.

---

## 4. Send Your First Email

### Setup — Google Workspace / Gmail

OpenClaw uses the `gog` CLI to connect to Google Workspace:

```bash
# Install gog
npm install -g @openclaw/gog

# Authenticate with your Google account
gog auth login
```

Follow the OAuth flow in your browser → you're now connected. ✅

---

### The Moment of Magic ✨

In the Control UI, type:

```
Draft an email to friend@example.com introducing myself 
and mentioning I'm exploring AI assistants. 
Don't send it yet — show me the draft first.
```

**Watch what the agent does:**

1. 🧠 **Thinks** — plans a friendly intro email
2. ✍️ **Drafts** — writes the email using your tone
3. 👀 **Shows you** — displays the draft for review
4. ⏸️ **Waits** — does NOT send until you approve

---

### Approve and Send

If the draft looks good, type:

```
Looks great, send it!
```

The agent calls the Gmail tool → email delivered. ✅

---

### 🎓 Key Teaching Moment

> **Notice what the agent did:** it didn't blindly send — it drafted and waited for your approval.
>
> Good agents have **guardrails**. They act within boundaries you define.
>
> This is the difference between a tool and a *trustworthy* agent.

The email draft/approve pattern is a design choice — the agent's `SOUL.md` and `AGENTS.md` files explicitly say *"always draft first, send second."* You control that behavior. You can tighten it or loosen it.

---

## ✅ Key Takeaways

| Concept | One-Liner |
|---------|-----------|
| 🤖 **Agent** | Perceive → Think → Act → Observe → Repeat |
| 🧠 **Model** | The brain — Claude decides *what* to do |
| 🔧 **Tools** | The hands — email, web, files *actually do* the work |
| 🏗️ **Neurological Levels** | OpenClaw lets you configure *who* the agent is, not just *what* it does |
| 🦞 **OpenClaw** | The platform that wires all of this together — runs 24/7, connects to your apps |
| 📧 **First Email** | Agents can do real things — but good ones ask before acting |

---

## 💬 Discussion Questions

Use these to spark conversation at the end:

- *"What would you want your agent to do for you every morning?"*
- *"What would you NOT want an agent to do automatically — where would you want to approve first?"*
- *"What tools would be most useful for your work — email, calendar, web search, code?"*
- *"If your agent had a persona, what kind of personality would you give it?"*

---

## 📚 Resources

| Resource | Link |
|----------|------|
| 📖 Docs | https://docs.openclaw.ai |
| 💬 Community (Discord) | https://discord.com/invite/clawd |
| 🧩 Skills & Add-ons | https://clawhub.com |
| 🔑 Claude API Keys | https://console.anthropic.com |
| 🐙 GitHub | https://github.com/openclaw/openclaw |

**Quick install command:**
```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

---

*Happy building! 🚀 Questions? Join the community Discord — it's friendly in there.*
