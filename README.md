<div align="center">

# 👋 Hi, I'm Satish Kumar Jaiswal

### 🤖 Aspiring AI Product Manager | Generative AI | LLMs | RAG | AI Agents

**Building AI-powered products • Exploring GenAI • Solving real-world problems with AI**

[![GitHub](https://img.shields.io/badge/GitHub-SatishJ12-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SatishJ12)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/satish-kumar-jaiswal-a5139648/)

</div>

---

## 🚀 About Me

I'm an **AI Product Management aspirant** focused on building practical products using **Generative AI, Large Language Models, RAG and AI Agents**.

I'm particularly interested in the intersection of:

**🤖 AI + 📦 Product + 👤 Customer Experience**

My GitHub is where I document my journey of moving from **AI concepts to working prototypes and product thinking**.

I'm currently building and experimenting with AI solutions that explore how emerging AI capabilities can solve real-world business and customer problems.

---

## 🎯 My AI Product Management Focus

```text
                    AI PRODUCT MANAGEMENT
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
      Discovery          Strategy          Delivery
          │                 │                 │
     User Problems      AI Use Cases        MVP
     Pain Points        Prioritization       Experiments
     Requirements      Roadmaps             Metrics
     User Stories      Trade-offs           Iteration
          │                 │                 │
          └─────────────────┼─────────────────┘
                            │
                      AI CAPABILITIES
                            │
             ┌──────────────┼──────────────┐
             │              │              │
            LLMs           RAG        AI Agents
             │              │              │
         Prompting      Retrieval      Tools
         Evaluation     Embeddings    Guardrails
         Context        Vector DB     Human-in-loop
```

---

# 🤖 Featured AI Projects

## ⚖️ AtliQ Contract Risk Analyzer — Capstone Project (Codebasics AI PM)

**An AI copilot that reviews a contract before the CEO signs it**

**The problem.** AtliQ Technologies is an IT services firm (India + USA entities) with **no legal team**. The CEO signs every client MSA, SOW, NDA, HIPAA BAA and freelancer agreement himself, often late at night under deadline pressure. The real risks were not in any one contract but *between* them: a non-compete signed two years ago that a new deal would breach, an uncapped liability clause buried on page 11, the wrong AtliQ entity on the signature block, a healthcare deal with no BAA, an EU deal with no DPA, and negotiation history that lived only in the CEO's memory.

**What I did as the PM.** User research → AI opportunity map → AI PRD → cost model → two working prototypes → stakeholder deck.

* **North Star:** *Safe Signature Rate*, the share of contracts signed with every High-risk finding resolved or consciously accepted (target 90% by month 3)
* **Design principle:** the AI never says a contract is "safe". It flags, quotes the exact clause, and escalates to counsel; the human decides and the decision is logged
* **Hybrid by design:** deterministic rules (the CEO's own checklist as code) + a register of commitments from 17 signed contracts + an LLM layer on top, so the tool still works when the AI is down or wrong
* **Evaluated on golden cases:** 13 hand-labelled contract scenarios (hidden non-competes, missing sub-BAA, pay-when-paid, fake "mutual" NDA, MFN clash) plus clean controls that must *not* be flagged
* **Unit economics:** ~$0.30 per contract, ~$330 / year in Year 1

I built **two prototypes** of the same product so stakeholders could choose with evidence instead of opinions.

| | **v1 — Streamlit** | **v2 — React + FastAPI + LLM-as-Judge** |
|---|---|---|
| **Stack** | Python + Streamlit | React (Vite, TypeScript, Tailwind) + FastAPI |
| **AI approach** | Rules + register, then **one** LLM review pass (Claude); quotes string-matched against the contract | Rules + register, then a **two-stage pipeline** on Groq: a small model extracts risky clauses, a larger model **judges** each finding (confirm / escalate / dismiss); any disagreement or unverified quote → *Needs Human Review* |
| **Deploy** | GitHub Pages via **stlite** (Python in the browser, no server) | GitHub Pages frontend (offline demo mode) + **Render** backend for live AI |
| **Guardrails** | No "safe" state, decision log per High finding, counsel-escalation rules | All of v1, plus access token, rate limits, daily LLM cap, prompt-injection test |
| **Tests** | 13 golden cases | 13 golden + 50 backend + 12 frontend |

### ✅ Pros / ⚠️ Cons

**v1 — Streamlit**
* ✅ Fastest to ship; one Python codebase
* ✅ No server: runs entirely in the browser, works offline, $0 hosting
* ✅ Simple to explain and demo
* ⚠️ Single LLM pass: no second opinion on what the model flags
* ⚠️ The browser build runs rules + register only; the AI review needs the Python app run with an API key
* ⚠️ Basic UI, harder to evolve into a real product

**v2 — React + LLM-as-Judge**
* ✅ Product-grade UI: review queue, commitment register, finding cards, review brief
* ✅ Second model checks the first, cutting false alarms and surfacing uncertainty to the human
* ✅ Live AI backend with auth and spend limits
* ⚠️ More moving parts: two deploys, env vars, a token to manage
* ⚠️ Two model calls → slower (est. ~14–18 s vs ~8–12 s) and slightly more expensive (~$0.33 vs ~$0.30 per contract)
* ⚠️ Free-tier LLM token limits block most live reviews, so a real rollout needs a paid tier

### 🧭 Why two versions?

Prototype progression and stakeholder choice. v1 proved the core value quickly: rules + memory of past commitments catch most of the dangerous clauses. v2 tests the next AI PM question: **is a second "judge" model worth the extra latency, cost and complexity in exchange for fewer false alarms and clearer escalation?** Stakeholders get both side by side with SWOT, cost and latency. My recommendation: ship v1 now, grow into v2 once the judge earns its cost.

### Product Focus

`Legal AI` `LLM-as-Judge` `Hybrid Rules + LLM` `Evaluation` `Human-in-the-Loop` `Guardrails` `Prototype Comparison`

🔗 **v1 Repository:** https://github.com/SatishJ12/atliq-contract-analyzer  
🌐 **v1 Live demo:** https://satishj12.github.io/atliq-contract-analyzer/  
🔗 **v2 Repository:** https://github.com/SatishJ12/atliq-contract-analyzer-v2  
🌐 **v2 Live demo:** https://satishj12.github.io/atliq-contract-analyzer-v2/

---

## 🔎 RAG Chatbot

**Telecom Customer Support Assistant powered by RAG**

A telecom-focused chatbot that uses **Retrieval-Augmented Generation** to answer customer questions using telecom guides, resolved helpdesk tickets and FAQ documents.

The project explores how an AI assistant can combine enterprise knowledge with an LLM to provide more contextual and grounded customer responses.

### Product Focus

`Generative AI` `RAG` `LLM` `Customer Support` `Knowledge Retrieval`

### Product Questions I'm Exploring

* How can AI reduce customer support effort?
* How can we improve answer relevance?
* How do we reduce hallucinations?
* When should conversations be escalated to humans?
* How do we measure AI-powered support quality?

🔗 **Repository:**
https://github.com/SatishJ12/rag-chatbot

---

## 🤖 AI Agent for Recharge Refunds

**AI-powered investigation and refund workflow**

An AI Agent designed to investigate customer refund requests and determine the appropriate next step while keeping financial actions behind controlled business rules.

> **The AI can investigate and recommend — but it should not independently move money.**

### Product Focus

`AI Agents` `LLMs` `Tool Calling` `Guardrails` `Human-in-the-Loop` `AI Safety`

### Product Thinking

This project explores an important AI PM question:

**How much autonomy should we give an AI agent when it is operating in a financially sensitive workflow?**

The solution focuses on balancing:

**Automation ↔ Control ↔ Customer Experience ↔ Risk**

---

## 🛒 ShopMate — AI Shopping Agent

**Conversational shopping assistant with tool-calling, photo search and memory**

A pantry-store shopping agent that lets a shopper describe what they want in plain language, or upload a photo, and get back a scannable product list with live ratings — then place an order once they explicitly confirm. Built with the same product instincts as **rag-chatbot** — grounded answers, explicit guardrails, a human confirmation before anything irreversible — applied to an agentic, tool-calling shape instead of a retrieval one.

### Product Focus

`AI Agents` `LLM Tool Calling` `Vision` `Conversational Commerce` `Guardrails` `Personalization`

### Product Questions I'm Exploring

* How do you keep an LLM's output format reliable enough to be testable?
* Where should guardrails live — prompt, code, or both?
* How much should an agent remember across sessions, and where should that state live?
* What does "the agent is working" look like as a set of product and AI-quality metrics?
* What does a shopping agent cost per conversation, and does that change the design?

🔗 **Repository:**
https://github.com/SatishJ12/shopping-agent

---

# 🧪 Also Building: Engineering & Automation Tooling

## 🧩 Web Page to Markdown Converter — Chrome Extension

**Turn any web page into clean, LLM-ready Markdown in one click**

A Manifest V3 Chrome extension that extracts the real content of a page — stripping ads, navbars, sidebars and cookie banners with a readability-style algorithm — and converts it into clean Markdown for **ChatGPT / Claude prompts, Obsidian, Notion and GitHub**. Code blocks keep their language tags, HTML tables become GitHub-style tables, and a live token counter shows what will fit in a prompt. Everything runs **100% locally** — no servers, no tracking, no remote code — in a **~50 KB** package built with vanilla JavaScript and zero dependencies.

### Product Focus

`Chrome Extension` `Manifest V3` `Vanilla JS` `LLM Context Prep` `Privacy by Design` `Developer Tools`

### Product Decisions I Made

* **Least-privilege permissions** — `activeTab` + `scripting` instead of access to all sites, so users trust it and Web Store review passes faster
* **Local-only processing** — works on paywalled and internal pages without any data leaving the browser
* **Built for LLM workflows** — compact output + token estimate, because context windows cost money
* **Three modes (Article / Full page / Selection)** — a fallback whenever automatic extraction is wrong
* **Tiny footprint** — no frameworks; the whole extension is smaller than most single images

🔗 **Repository:** https://github.com/SatishJ12/web-page-to-markdown    
🌐 **Support site:** https://satishj12.github.io/web-page-to-markdown/        
🧩 **Chrome Web Store:** https://chromewebstore.google.com/detail/fmbinlegholbmghcdbibjkdcbkcnolip

---

## 🖥️ Website E2E Tester

**PowerShell + Selenium end-to-end testing automation**

A traditional (non-AI) automation framework that logs into websites, validates page content against CSS selectors, and captures screenshots at every step — producing Excel and Word test reports. Configurable per site via CSV, with encrypted credential storage (DPAPI) and Windows Task Scheduler integration for unattended, scheduled runs.

### Focus

`PowerShell` `Selenium` `Browser Automation` `QA Engineering` `Test Reporting`

🔗 **Repository:**
https://github.com/SatishJ12/website-e2e-tester

---

# 🧩 My AI Product Philosophy

> **Start with the problem, not the model.**

My approach to AI products:

```text
Customer Problem
       ↓
User / Persona
       ↓
Pain Point
       ↓
AI Opportunity
       ↓
Use Case
       ↓
MVP
       ↓
AI Architecture
       ↓
Evaluation
       ↓
Guardrails
       ↓
Product Metrics
       ↓
Experiment
       ↓
Iterate
```

For every AI product, I try to ask:

* 🎯 What problem are we solving?
* 👤 Who is the user?
* 🤖 Does AI genuinely improve the experience?
* 💡 Why use AI instead of traditional software?
* 📊 How will we measure success?
* 🧪 How do we evaluate AI quality?
* 🛡️ What happens when AI is wrong?
* 👨‍💼 Where should humans remain in control?
* 💰 What is the cost of the AI interaction?
* ⚡ What latency is acceptable?
* 🔐 What are the privacy and safety implications?

---

# 🛠️ AI & Technology Stack

### 🤖 Generative AI

<p>
<img src="https://skillicons.dev/icons?i=python,pytorch,tensorflow" />
</p>

`LLMs` `Generative AI` `RAG` `AI Agents` `Prompt Engineering`

### 🔎 AI Application Development

`Python` `APIs` `Embeddings` `Vector Search` `RAG Pipelines`

`LangChain` `LLM APIs` `Tool Calling` `Agentic Workflows` `Chrome Extensions`

### 📦 Product Management

`Product Discovery` `User Stories` `Requirements` `PRDs`

`Product Roadmaps` `Prioritization` `Agile` `Scrum`

`Experimentation` `Product Metrics` `Customer Experience`

---

# 📊 AI Product Metrics I'm Interested In

| Product Metrics          | AI Metrics               |
| ------------------------ | ------------------------ |
| 👥 User Adoption         | 🎯 Response Accuracy     |
| ✅ Task Completion        | 🔎 Groundedness          |
| 😊 Customer Satisfaction | ⚠️ Hallucination Rate    |
| 📈 Retention             | 🔍 Retrieval Quality     |
| 🎫 Resolution Rate       | 🤖 Agent Success Rate    |
| ⏱️ Time Saved            | 👨‍💼 Human Escalation   |
| 💰 Cost / User           | ⚡ Latency                |
| 🔄 Repeat Usage          | 💵 Cost / AI Interaction |

---

# 🌱 Currently Exploring

```text
🤖 AI Agents & Agentic Workflows

🧠 Generative AI & LLM Applications

🔎 RAG Optimization

🧪 LLM Evaluation

📊 AI Product Analytics

👤 Human-AI Interaction

🎨 AI UX

🛡️ Responsible AI

🔐 AI Safety & Guardrails

📦 AI Product Strategy

🚀 AI Product Discovery
```

---

# 📈 GitHub Activity

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=SatishJ12&show_icons=true&hide_border=true&rank_icon=github&include_all_commits=true" height="165"/>

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=SatishJ12&layout=compact&hide_border=true" height="165"/>

</div>

<br>

<div align="center">

<img src="https://streak-stats.demolab.com?user=SatishJ12&hide_border=true" />

</div>

---

# 🏆 What You'll Find in My Repositories

| Area                 | Focus                              |
| -------------------- | ---------------------------------- |
| 🤖 AI Agents         | AI-powered workflows & automation  |
| 🧠 GenAI             | LLM-powered applications           |
| 🔎 RAG               | Grounded knowledge assistants      |
| 💬 Conversational AI | Intelligent customer experiences   |
| 🧪 AI Experiments    | Product prototypes & experiments   |
| 📊 Evaluation        | AI quality & product metrics       |
| 🛡️ Responsible AI   | Guardrails & human oversight       |
| 📋 Product           | AI product thinking & requirements |

---

# 🎯 Career Goal

I'm working toward **AI Product Manager / GenAI Product Manager** opportunities where I can combine:

### Product Thinking + Business Understanding + AI Technology + Customer Problem Solving

My goal is to help organizations identify meaningful AI opportunities and transform them into **valuable, scalable and responsible AI-powered products**.

---

# 🤝 Let's Connect

I'm interested in conversations around:

**AI Products • Generative AI • AI Agents • RAG • LLMs • Product Management • AI Strategy • Responsible AI**

<p align="center">

<a href="https://www.linkedin.com/in/satish-kumar-jaiswal-a5139648/">
<img src="https://img.shields.io/badge/Connect%20with%20me%20on-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

</p>

---

<div align="center">

### 💡 Building at the intersection of AI × Product × Customer Experience

⭐ **Explore my repositories and follow my AI product journey.**

</div>
