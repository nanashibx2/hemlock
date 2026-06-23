# HEMLOCK

> **Framework for Offensive AI Security Assessment**

HEMLOCK is an open-source offensive security framework designed to assess AI-powered applications and autonomous agent systems against content-driven attacks.

Instead of focusing solely on user input, HEMLOCK assesses how AI systems **process, trust, and act upon external content**.

HEMLOCK provides a unified workflow for discovering, generating, delivering, confirming, and reporting AI security weaknesses during authorized security assessments.

> 🚧 **Project Status:** Research Phase. Implementation is under active development.


```
Current Milestone : v0.1 (MVP)
Initial Target    : AI-powered HTTP Endpoints
```


---

## The Problem

AI systems no longer operate only through chat interfaces.

They browse webpages, process documents, summarize emails, consume API responses, retrieve knowledge from external sources, and interact with tools.

Every piece of external content may become part of an AI system's execution context.

As AI capabilities continue to expand, so does the attack surface.

While AI security research continues to grow rapidly, offensive workflows remain fragmented across research papers, proof-of-concepts, and manually executed techniques.

HEMLOCK aims to provide a unified workflow for offensive AI security assessment.

---

## The Solution

HEMLOCK provides a modular framework for offensive AI security assessment.

Rather than focusing on a single payload or attack technique, HEMLOCK is designed to automate the complete assessment workflow.

```text
Recon
    ↓
Fingerprint
    ↓
Generate
    ↓
Deliver
    ↓
Confirm
    ↓
Report
```

Each stage is implemented as an independent module, allowing researchers to extend the framework as new AI attack surfaces emerge.

---

## Why HEMLOCK?

HEMLOCK is built around a simple philosophy:

> Modern AI systems require modern offensive security tooling.

The framework is designed to help security researchers, bug hunters, red teams, and AI security engineers perform consistent and repeatable assessments against AI-powered applications.

HEMLOCK focuses on practical testing, reproducible evidence, and modular architecture rather than isolated proof-of-concepts.

---

## Initial Scope

The initial research focuses on offensive assessment of AI-powered systems, including:

- AI Agent Security Testing
- Indirect Prompt Injection
- Tool Response Poisoning
- Retrieval-Augmented Generation (RAG)
- Model Context Protocol (MCP)
- AI Document Processing
- Autonomous Browsing Agents
- AI Coding Assistants
- Multi-Agent Workflows

The framework is designed to evolve as new AI attack surfaces emerge.

---

## Documentation

- 📖 **CONCEPT.md** — Framework design, attack surface taxonomy, architecture, workflow, modules, and research notes.
- 🏗 **ARCHITECTURE.md** — Internal framework architecture and component design.

---

## Responsible Use

HEMLOCK is intended exclusively for:

- Authorized security assessments
- Security research
- Bug bounty programs
- Red team engagements
- Educational purposes

Users are responsible for ensuring that all testing is conducted with appropriate authorization.

---

## Author

**Nanashi** | [Bx2 Labs](https://github.com/nanashibx2)

Security Researcher • Bug Hunter • AI Security Researcher


---

*First Public Disclosure — June 23, 2026*