# HEMLOCK
 
### 📌 Quick Navigation Index
 
* [Origin](#1-origin)
* [Research Gap](#2-research-gap)
* [Framework Overview](#3-framework-overview)
* [Design Principles](#4-design-principles)
* [Operational Workflow](#5-operational-workflow)
* [Target Attack Surfaces](#6-target-attack-surfaces)
* [References](#7-references)
* [Prior Art](#8-prior-art)
---
 
## 1. Origin
 
HEMLOCK originated from a simple observation:
 
Offensive security has consistently evolved through automation. Established tools transformed manual testing into repeatable workflows, making security assessments faster, more consistent, and easier to reproduce.
 
Modern AI-powered applications introduce a fundamentally different attack surface. Instead of processing only direct user input, they increasingly consume external content such as webpages, documents, emails, tool responses, and retrieved knowledge.
 
During offensive AI security research, it became apparent that practical testing methodologies remain fragmented across academic research, isolated proof-of-concepts, and manually executed assessment workflows.
 
HEMLOCK was conceived to bridge this gap by bringing these fragmented approaches together under a single offensive security framework.
 
The framework defines a structured workflow for assessing AI-powered systems through reconnaissance, fingerprinting, payload generation, delivery, confirmation, and reporting. It is designed to evolve alongside emerging AI attack surfaces while remaining practical for security researchers, bug bounty hunters, and red teams.
 
---
 
## 2. Research Gap
 
### Why AI Changes the Attack Surface
 
Unlike traditional software, modern AI-powered applications do more than process direct user input.
 
They retrieve webpages, analyze documents, summarize emails, interact with external tools, consume API responses, and operate within retrieval and multi-agent workflows.
 
As AI systems consume increasing amounts of external content, every trusted source becomes a potential attack surface. Malicious instructions embedded within that content may influence an AI system's behavior without requiring direct interaction from the attacker.
 
This represents a shift from traditional input validation problems toward content-driven security assessment.
 
---
 
### Current Tooling Landscape
 
Research surrounding AI security has expanded rapidly in recent years. Existing work includes academic research, defensive frameworks, benchmark datasets, proof-of-concept exploits, and collections of manually crafted payloads.
 
While these resources provide valuable insight into AI security, they are generally designed for research, evaluation, or defensive analysis rather than repeatable offensive assessments against authorized targets.
 
As a result, practical offensive workflows remain fragmented, requiring researchers to combine multiple tools and manual techniques throughout a single assessment.
 
---
 
### Why HEMLOCK
 
HEMLOCK is designed to bridge this gap by providing a unified framework for offensive AI security assessment.
 
Instead of focusing on a single attack technique, HEMLOCK organizes the assessment process into a modular workflow that includes reconnaissance, target fingerprinting, payload generation, delivery, confirmation, and reporting.
 
This approach aims to improve consistency, repeatability, and extensibility while allowing the framework to grow alongside emerging AI attack surfaces.
 
---
 
## 3. Framework Overview
 
HEMLOCK is a modular offensive security framework designed to assess AI-powered applications through a structured and repeatable workflow.
 
The framework is not limited to a single vulnerability class. It provides a common assessment pipeline that can be adapted to multiple AI attack surfaces.
 
At a high level, HEMLOCK performs six primary functions:
 
**Reconnaissance** – Identifying accessible AI-powered interfaces, endpoints, and potential attack surfaces.
 
**Target Fingerprinting** – Identifying observable implementation characteristics that influence assessment strategy.
 
**Payload Generation** – Generating assessment payloads tailored to specific AI attack surfaces.
 
**Payload Delivery** – Delivering generated payloads through target-specific content channels.
 
**Confirmation** – Determining whether the assessment objective was successfully achieved.
 
**Reporting** – Producing reproducible findings and supporting assessment evidence.
 
Each capability is designed as an independent module. New attack surfaces and techniques slot into the existing structure without requiring changes to the core framework.
 
This modular architecture keeps the assessment methodology consistent as new AI technologies and attack surfaces emerge.
 
---
 
## 4. Design Principles
 
HEMLOCK is designed around five engineering principles.
 
### Modular
 
Each capability is a self-contained module. New attack surfaces, payload types, or delivery techniques can be added without touching the core framework. Building on HEMLOCK should not require rewriting it.
 
### Offensive by Design
 
HEMLOCK is built for offense. The framework exists to find and validate security weaknesses through authorized testing — not to monitor, detect, or alert. Design decisions prioritize the attacker's perspective.
 
### Repeatable
 
A finding that cannot be reproduced is not a finding. HEMLOCK structures every assessment into a consistent workflow so that results can be verified, shared, and submitted as evidence.
 
### Extensible
 
AI attack surfaces continue to evolve rapidly. HEMLOCK's architecture allows new payload classes, delivery mechanisms, and attack surfaces to be added without disrupting existing functionality.
 
### Evidence-Driven
 
Observable behavior drives every conclusion. HEMLOCK does not infer vulnerabilities — it confirms them through captured responses, payload details, and reproduction steps.
 
---
 
## 5. Operational Workflow
 
HEMLOCK organizes offensive AI security assessments into a structured operational workflow. Each stage performs a distinct function while remaining independent of the others, allowing the framework to support multiple AI attack surfaces without changing its overall methodology.
 
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
 
### Recon
 
The assessment begins by identifying accessible AI-powered interfaces, endpoints, and potential attack surfaces. This stage collects publicly observable information that helps determine where and how an assessment can be performed.
 
### Fingerprint
 
Once a target is identified, HEMLOCK attempts to determine observable implementation characteristics that influence the assessment strategy, such as supported capabilities, external integrations, or content processing behavior.
 
Initial fingerprinting capabilities focus on observable HTTP response characteristics. Advanced backend identification is planned for future releases.
 
### Generate
 
Based on the identified attack surface, HEMLOCK generates assessment payloads appropriate for the target environment. Payload generation is modular, allowing multiple techniques to be supported without changing the overall workflow.
 
### Deliver
 
Generated payloads are delivered through the selected content channel, ensuring they reach the AI system through the intended attack surface.
 
### Confirm
 
HEMLOCK evaluates the target's response to determine whether the assessment objective was successfully achieved. Confirmation relies on observable behavior rather than assumptions.
 
### Report
 
The final stage consolidates assessment results into structured findings, including supporting evidence, payload details, and information necessary to reproduce the observed behavior.
 
---
 
## 6. Target Attack Surfaces
 
HEMLOCK is designed to support offensive security assessments of AI-powered systems that consume, retrieve, process, or act upon external content.
 
Initial research focuses on the following attack surfaces:
 
| Attack Surface | Examples |
|---|---|
| **AI-Powered HTTP Endpoints** | AI APIs and AI-enabled web applications *(Initial implementation target)* |
| Web Content | Browsing agents and web retrieval |
| Document Processing | PDF, DOCX, Markdown, CSV |
| Retrieval-Augmented Generation (RAG) | External knowledge retrieval pipelines |
| Tool & API Responses | External integrations and plugin outputs |
| Model Context Protocol (MCP) | MCP-compatible services and integrations |
| Email & Messaging | AI-integrated communication assistants |
| AI Coding Assistants | AI-assisted software development workflows |
| Multi-Agent Systems | Agent-to-agent communication pipelines |
 
Additional attack surfaces may be incorporated as the framework evolves and new AI capabilities emerge.
 
---
 
## 7. References
 
HEMLOCK builds upon publicly available research, industry guidance, and open standards related to AI security.
 
### Industry Guidance
 
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OWASP GenAI Security Project](https://genai.owasp.org/)
- [MITRE ATLAS — Adversarial Threat Landscape for AI Systems](https://atlas.mitre.org/)

### Research
 
- Greshake et al. — *Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injections* (2023) — [arXiv:2302.12173](https://arxiv.org/abs/2302.12173)
- Perez & Ribeiro — *Ignore Previous Prompt: Attack Techniques for Language Models* (2022) — [arXiv:2211.09527](https://arxiv.org/abs/2211.09527)

### Standards
 
- [Model Context Protocol (MCP) Specification](https://spec.modelcontextprotocol.io/)
---
 
## 8. Prior Art
 
```text
Author     : Nanashi | Bx2 Labs
Repository : https://github.com/nanashibx2/hemlock
Disclosed  : June 23, 2026
Status     : Initial Public Disclosure
```
 
This document serves as the initial public disclosure of the HEMLOCK framework.
 
Its purpose is to establish a publicly verifiable development timeline for the framework's concepts, architecture, workflow, and implementation approach.
 
HEMLOCK does not claim ownership of any underlying vulnerability class, attack technique, or previously published research. The framework builds upon publicly available AI security research while presenting its own architecture, assessment workflow, and engineering design.
 
Subsequent revisions will be documented through the public Git history of this repository.
 
This document describes the conceptual design of HEMLOCK. Implementation status is documented separately through project milestones and public commits.
 
---
 
**HEMLOCK** | **Nanashi** | [Bx2 Labs](https://github.com/nanashibx2)