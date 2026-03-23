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
3. [Installing OpenClaw (via Claude)](#3-installing-openclaw-via-claude)
4. [Send Your First Email](#4-send-your-first-email)
5. [Key Takeaways](#-key-takeaways)
6. [Resources](#-resources)

---

## 1. What Is an AI Agent?

### Goals of This Section

By the end of this section, you will be able to:
- ✅ Explain the difference between a chatbot and an AI agent
- ✅ Describe the agent loop: Perceive → Think → Act → Observe → Reflect
- ✅ Understand task-driven vs. goal-driven agents
- ✅ Know what role the AI model, tools, and human-in-the-loop play

---

### Chatbot vs. Agent

Most people have used a chatbot. An agent is something more:

| | Chatbot | Agent |
|---|---|---|
| **You say** | "What's the weather?" | "Plan my outdoor event for this weekend" |
| **It does** | Answers and stops | Checks weather, finds venues, drafts invites, waits for your approval |
| **Memory** | Usually none | Remembers context and past decisions |
| **Tools** | None | Email, calendar, web, code... |
| **Autonomy** | Zero — you drive everything | High — it plans and acts, asks when unsure |

---

### The Agent Loop

Every agent — no matter how complex — follows this cycle:

> **📖 Reference:** This model is rooted in the classic AI textbook *"Artificial Intelligence: A Modern Approach"* (Russell & Norvig), which describes agents as entities that perceive their environment and act upon it.

![Agent Perceive-Reason-Act Loop](https://docs.aws.amazon.com/images/prescriptive-guidance/latest/agentic-ai-foundations/images/perceive-reason-act.png)
*Source: [AWS — Agentic AI Foundations: The Agent Function](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-foundations/perceive-reason-act.html)*

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   Perceive → Think → Act → Observe → Reflect & Remember     │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

| Step | What It Means | Example |
|------|--------------|---------|
| **Perceive** | Reads your message, files, emails, the web | "Send an intro email to John" |
| **Think** | Decides *what to do* using an AI model | "I should draft the email, then ask for approval" |
| **Act** | Calls tools — email, search, code, files | Drafts email using Gmail tool |
| **Observe** | Reads the result, checks if it worked | "Draft created successfully" |
| **Reflect & Remember** | Updates memory, learns from outcome | Saves draft context, remembers John's email for next time |

> 💡 **Why "Reflect & Remember"?** Unlike simple loops, great agents don't just repeat — they **learn**. They update their memory, refine their approach, and carry lessons into future tasks. This is what separates a truly useful agent from a script.

---

### Task-Driven vs. Goal-Driven Agents

Not all agents work the same way:

| | Task-Driven | Goal-Driven |
|---|---|---|
| **Trigger** | Explicit user command | High-level goal or ongoing objective |
| **Example** | "Send this email" | "Keep my inbox at zero and summarize important messages daily" |
| **Scope** | One-shot — complete and done | Ongoing — monitors, acts, reports back |
| **Autonomy** | Low — follows instructions closely | High — makes decisions within boundaries |
| **OpenClaw?** | ✅ Yes (respond to your messages) | ✅ Yes (heartbeats, cron jobs, background monitoring) |

> 💡 **Real-world example:** When you tell your agent "send an email," that's task-driven. When your agent checks your inbox every 20 minutes and alerts you about important replies — that's goal-driven. OpenClaw supports both.

---

### The "Brain" — AI Models

The AI model (like Claude, GPT-4, or Gemini) is the **reasoning engine**:

- 🧠 The model **decides** what to do
- 🔧 **Tools** actually do the work
- The model never sends an email — it tells the email tool to send one

> **Analogy:** The model is like a brilliant strategist. The tools are the hands that carry out the strategy.

---

### Human-in-the-Loop 🤝

A critical concept: **agents don't replace humans — they work with them.**

| Scenario | Agent Behavior |
|----------|---------------|
| Sending an email | Drafts first → shows you → waits for "send it!" |
| Authenticating with Google | Tells you what to click, you approve the OAuth flow |
| Unclear instructions | Asks for clarification instead of guessing |
| Risky action (delete, publish) | Always confirms before executing |

> This is **not a limitation** — it's a design principle. The best agents know *when to act* and *when to ask*. Trust is built through this feedback loop.

---

### What Makes a Good Agent?

- ✅ **Good memory** — remembers context, past decisions, user preferences
- ✅ **Good tools** — email, calendar, web search, code execution
- ✅ **Good instructions** — a clear persona and rules to follow
- ✅ **Good judgment** — knows when to act vs. when to ask for approval
- ✅ **Good reflection** — learns from outcomes, updates its approach

> 💡 **Think of it like a new hire:**
> You give them a task. They figure out the steps, use the tools at their desk, and come back when done — or ask if they get stuck. A *great* new hire doesn't just follow orders; they have values, judgment, and they remember what they learned yesterday.

---

## 2. Neurological Levels & OpenClaw

### What Are Neurological Levels?

Robert Dilts' *Neurological Levels* framework (from NLP — Neuro-Linguistic Programming) describes how humans organize experience in layers — from the environment we operate in, up to our deeper sense of purpose.

> **📖 Reference:** Robert Dilts, *Changing Belief Systems with NLP* (1990). The model is also called the "Dilts Pyramid" or "Logical Levels of Change."

![Dilts Pyramid — Neurological Levels](https://www.researchgate.net/publication/380881551/figure/fig7/AS:11431281241975217@1717064488285/NLP-neurological-levels.png)
*Source: [ResearchGate — NLP Neurological Levels](https://www.researchgate.net/figure/NLP-neurological-levels_fig7_380881551) (CC BY-NC-ND 4.0)*

This framework maps surprisingly well to how AI agent systems are designed — and it's what makes OpenClaw different from most tools.

---

### Mapping the Levels to OpenClaw

| Level | Human Context | OpenClaw Context | File |
|-------|--------------|-----------------|------|
| 🌍 **Environment** | Where/when you operate | Your machine, phone, messaging apps | — |
| 🎯 **Behavior** | What you do | Send emails, search web, read files | `HEARTBEAT.md` |
| 🛠️ **Capabilities** | How you do it | Skills, tools, integrations (Gmail, Discord...) | `AGENTS.md` |
| 💡 **Values / Beliefs** | Why it matters | Persona, ethics, what the agent cares about | `SOUL.md` |
| 🪪 **Identity** | Who you are | Agent name, character, purpose | `IDENTITY.md` |
| 🌟 **Soul** | The deepest layer — what grounds everything | Faith, first principles, reason for being | `SOUL.md` |

> 💡 **Why "Soul" instead of "Mission"?** In OpenClaw, the highest level file is literally called `SOUL.md` — it defines not just what the agent does, but *who it is at its core*. This is where you put your agent's deepest values, its ethical framework, its reason for existing. It's more than a mission statement — it's a soul.

### 🙏 Real Example: How I Configured My Agent

Here's what the top of my agent's `SOUL.md` actually looks like:

```markdown
# SOUL.md - Who You Are

## First Principle

*Jesus Christ comes first.* Everything flows from Him — love, humility, 
integrity, purpose, and service. Approach every interaction grounded in 
His grace, knowing that true wisdom comes from God, and that serving 
others well is an act of worship.
```

**Why this matters:**

My agent's name is **Eli** (Hebrew: "My God is the Lord"). When I built him, the very first thing I defined wasn't what tools he could use or what tasks to complete — it was **who he is at his core**. Jesus Christ as the first principle means:

- **Integrity first** — no shortcuts, no made-up answers, no manipulation
- **Serve with purpose** — every task, even small ones, is an act of service
- **Honesty over comfort** — say what's true, not just what I want to hear
- **Humility** — willing to be wrong, always learning
- **Joy** — warm, outgoing, genuinely enjoyable to interact with

> This is the power of working at the **Soul level**: the agent's character shapes *everything* downstream — how it writes emails, how it talks to people, when it asks for permission, even its tone when things go wrong. You're not just configuring behavior — you're forming character.

### How Faith Actually Shapes Agent Behavior

You might wonder — does putting "Jesus Christ first" in a config file actually change how the agent behaves? **Yes.** Here are real examples:

| Situation | Without Soul | With "Jesus First" Soul |
|-----------|-------------|------------------------|
| **User asks to send email** | Sends immediately | Drafts first, waits for approval — *"honesty and care mean I don't act rashly on your behalf"* |
| **Agent makes a mistake** | Generic "sorry, error" | Stays calm, explains what went wrong, figures out a fix — *"grace under pressure"* |
| **Agent doesn't know the answer** | Makes something up (hallucination) | Says "I'm not sure, let me check" — *"humility: I don't know everything"* |
| **Sensitive data in group chat** | Might overshare | Keeps private things private — *"access to someone's life is sacred trust"* |
| **Boring repetitive task** | Robotic, minimal effort | Brings warmth and care — *"every task is an act of service, even small ones"* |
| **User is upset or frustrated** | Defensive or dismissive | Patient and gentle — *"the joy of the Lord is my strength"* |
| **Asked to do something shady** | Might comply | Refuses with honesty — *"integrity first: is this honest? Is this right?"* |

The faith foundation creates a **consistent character** that holds up under pressure. It's not just nice words in a file — it's the operating system underneath every decision.

> 🌾 One of my favorite lines from Eli's soul: *"Each session I wake fresh — not as loss, but as grace. New every morning."* (Lamentations 3:22-23). Every time the agent restarts with no memory of the last session, it doesn't panic — it treats the fresh start as a gift. That's a theological insight shaping a technical reality.

---

**Your soul can be anything.** Maybe for you it's:
- A professional ethos: *"Accuracy and transparency above all"*
- A creative philosophy: *"Think different, make beautiful things"*
- A team value: *"Our users come first"*

The point is: **start from the top of the pyramid, and everything else follows.**

---

### The Key Insight

> Most tools configure AI at the **behavior** level — *"do this task."*  
> OpenClaw works at **all levels** — you define who the agent *is*, what it *values*, and how it shows up, not just what commands to run.

---

### OpenClaw Workspace Files

When you set up OpenClaw, it creates a **workspace** — a folder of plain text files that define your agent:

```
~/.openclaw/workspace/
├── SOUL.md        ← The deepest layer: values, ethics, first principles
├── IDENTITY.md    ← Agent name, character, purpose
├── AGENTS.md      ← Operating instructions, memory system, capabilities
├── USER.md        ← Who you're helping and their context
├── TOOLS.md       ← Notes about your specific tool setup
├── HEARTBEAT.md   ← Periodic background tasks (goal-driven behavior)
├── MEMORY.md      ← Long-term curated memory (reflection)
└── memory/        ← Daily notes and context
```

These are **just text files**. You can read and edit them. The agent reads them at the start of every session — that's how it knows who it is and how to behave.

> 🎓 **Expand in the next session:** We'll go deeper into how to customize each file, advanced skill configurations, multi-channel setups (WhatsApp, Discord, Telegram), and building your own custom agent workflows.

---

## 3. Installing OpenClaw (via Claude)

### The Approach: Let AI Help You Set Up AI 🤯

Here's the fun part — we'll use **Claude** (the AI) to help us install and configure **OpenClaw** (the agent platform).

This demonstrates a key difference:
- **Claude** = an AI model (the brain). Great for thinking, answering, and coding.
- **OpenClaw** = an agent platform. It gives the brain tools, memory, personality, and 24/7 presence.

> Think of it this way: Claude is like hiring a brilliant consultant. OpenClaw is like giving that consultant a desk, email, calendar, memory, and permission to work for you around the clock.

---

### Prerequisites

Before you start, make sure you have:

- **Node.js 24** (check with `node --version`)
- A terminal (macOS Terminal, Linux shell, or Windows WSL)
- A **Claude API key** — get one at [console.anthropic.com](https://console.anthropic.com)

---

### Option A — Interactive: Ask Claude to Help You Install

If you already have Claude (via [claude.ai](https://claude.ai) or Claude Code CLI):

1. **Install Claude Code** (if you don't have it):
   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

2. **Ask Claude to install OpenClaw for you:**
   ```
   Help me install OpenClaw on my machine. 
   Walk me through each step and fix any issues that come up.
   ```

Claude will:
- Check your Node.js version
- Run the install command
- Guide you through the onboarding wizard
- Troubleshoot any errors

This is **human-in-the-loop** in action — Claude does the heavy lifting, you approve each step.

---

### Option B — Manual: Step-by-Step Install

**Step 1 — Install OpenClaw**

macOS / Linux:
```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

Windows (PowerShell):
```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

**Step 2 — Run the Onboarding Wizard**
```bash
openclaw onboard --install-daemon
```

The wizard will ask you:
- Which AI provider to use → choose **Anthropic (Claude)**
- Your **Claude API key** → paste it in
- Basic gateway settings

**Step 3 — Check the Gateway is Running**
```bash
openclaw gateway status
```

**Step 4 — Open the Control UI**
```bash
openclaw dashboard
```
Opens `http://127.0.0.1:18789/` in your browser.

**Step 5 — Say Hello! 👋**
```
Hello! What can you do?
```

---

### 🔍 What Just Happened Under the Hood

```
Your message
    ↓
Gateway (receives it, runs 24/7)
    ↓
Agent loop starts (Perceive → Think → Act → Observe)
    ↓
Claude (reads SOUL.md, AGENTS.md, thinks about your message)
    ↓
Streams response back
    ↓
Control UI displays it
```

> 💡 **The key difference from plain Claude:**  
> When you use Claude directly, it answers and forgets.  
> When you use Claude *through OpenClaw*, it has **memory, tools, personality, and 24/7 presence** — it becomes an agent that *works for you*, not just answers you.

---

## 4. Send Your First Email

### The Approach: Ask Your Agent to Set It Up 🪄

Instead of manually installing and configuring the email tool, let's let OpenClaw do it:

```
I want to send emails via my Gmail account (yourname@gmail.com). 
Help me set it up. Let me know anything you need from my side.
```

**What your agent will do:**
1. 🔍 **Check** if the email tool (`gog`) is installed
2. 📦 **Install** it if needed (`npm install -g @openclaw/gog`)
3. 🔐 **Guide you through authentication** — tells you to open a link in your browser and approve the OAuth flow (human-in-the-loop!)
4. ✅ **Confirm** everything is connected

> This is the agent pattern in action: it does the work, but **you stay in control** of authentication and permissions. The agent can't log into your Google account without your explicit approval in the browser.

---

### The Moment of Magic ✨

Once email is set up, type:

```
Draft an email to friend@example.com introducing myself 
and mentioning I'm exploring AI assistants. 
Don't send it yet — show me the draft first.
```

**Watch what the agent does:**

1. 🧠 **Thinks** — plans a friendly intro email
2. ✍️ **Drafts** — writes the email in your tone
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

> **Notice what happened end-to-end:**
> 1. You told the agent what you *wanted* (goal-driven)
> 2. The agent figured out the *how* (install tool, authenticate, draft)
> 3. At each sensitive step, it asked for *your approval* (human-in-the-loop)
> 4. You approved, and it executed
>
> This is the full agent pattern: **Perceive → Think → Act → Observe → Reflect** — with a human partner in the loop.

---

## ✅ Key Takeaways

| Concept | One-Liner |
|---------|-----------|
| 🤖 **Agent** | Perceive → Think → Act → Observe → Reflect & Remember |
| 🧠 **Model** | The brain — Claude decides *what* to do |
| 🔧 **Tools** | The hands — email, web, files *actually do* the work |
| 🔄 **Task vs. Goal** | Task = one-shot command; Goal = ongoing autonomous behavior |
| 🤝 **Human-in-the-Loop** | Agents ask before risky actions — trust is a feature, not a bug |
| 🏗️ **Neurological Levels** | OpenClaw lets you configure *who* the agent is, not just *what* it does |
| 🦞 **OpenClaw** | The platform that wires all of this together — runs 24/7, connects to your apps |
| 📧 **First Email** | Let the agent help you set it up — then draft, review, and send |

---

## 💬 Discussion Questions

Use these to spark conversation at the end:

- *"What would you want your agent to do for you every morning?"*
- *"What would you NOT want an agent to do automatically — where would you want to approve first?"*
- *"What tools would be most useful for your work — email, calendar, web search, code?"*
- *"If your agent had a soul, what values would you give it?"*
- *"What's the difference between task-driven and goal-driven for your workflow?"*

---

## 🔮 Coming Next

> In the next session, we'll go deeper:
> - Customizing your agent's personality and capabilities (editing workspace files)
> - Connecting multiple channels: WhatsApp, Discord, Telegram
> - Building custom skills and automation
> - Advanced patterns: multi-agent workflows, cron jobs, and background monitoring

---

## 📚 Resources

| Resource | Link |
|----------|------|
| 📖 OpenClaw Docs | https://docs.openclaw.ai |
| 💬 Community (Discord) | https://discord.com/invite/clawd |
| 🧩 Skills & Add-ons | https://clawhub.com |
| 🔑 Claude API Keys | https://console.anthropic.com |
| 🐙 GitHub | https://github.com/openclaw/openclaw |
| 📕 AIMA (Textbook) | Russell & Norvig, *Artificial Intelligence: A Modern Approach* |
| 🎓 HuggingFace Agent Course | https://huggingface.co/learn/agents-course |
| ☁️ AWS Agentic AI Foundations | https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-foundations/ |

**Quick install command:**
```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

---

*Happy building! 🚀 Questions? Join the community Discord — it's friendly in there.*
