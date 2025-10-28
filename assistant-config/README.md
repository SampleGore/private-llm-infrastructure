# Local Cybersecurity AI Assistant — Homelab Project

This project implements a fully local, privacy-preserving LLM assistant configured to support cybersecurity study, analysis, and governance workflows. The system runs offline using Docker and Ollama, with extensible Retrieval-Augmented Generation (RAG) for querying personal documents such as white papers, reports, and training materials.

The goal of this project is to integrate practical cybersecurity tooling with AI-assisted research and documentation — while maintaining strict boundaries for safety, trust, and accuracy.

User → OpenWebUI → AnythingLLM → Ollama (models)
              ↘ logs/metrics ↙

---

# Core Capabilities

- Secure, offline LLM inference (no cloud dependency)
- Configurable model behavior with system prompts and safety policies
- Structured response format designed for SOC/GRC workflows
- Document ingestion for standards-based recommendations (RAG)
- Version-controlled prompt and policy configuration
- Architecture aligned with **CIA triad** and **Zero Trust principles**

---

# Tech Stack

| Component | Purpose |
|----------|---------|
| **Docker Desktop** | Containerized deployment |
| **Ollama** | Local LLM runtime |
| **Models** | e.g., LLaMA 3, Mistral, Phi-3 |
| **OpenWebUI** *(optional)* | Chat interface for LLM |
| **VS Code** | Configuration editing & version control |
| **External HDD** | Segregated data storage (models, knowledge base) |

Data storage is isolated to `D:\AI_DATA\` to support portability and security.

---

# Governance & Safety

Includes:
- **System Prompt** with cybersecurity alignment
- **Safety Profile v1** for reliability and risk control
- **Usage Policy** enforcing authorized-lab constraints
- **Citations & escalation behaviors** for auditability

See `/prompts` and `/policies` folders for full content.

---

# Roadmap (Next Enhancements)

- Deploy **OpenWebUI** container mapped to external drive
- Enable RAG using personal cybersecurity documents (white papers, PDFs)
- Add knowledge tagging system: NIST/ISO/CIS categories
- Logging and evidence output for incident triage practice
- Expand prompt variants: SOC L1, GRC Analyst, Cloud Security

---

# Why This Matters

Modern cybersecurity requires:
- AI literacy
- System deployment skills
- Governance + alignment expertise
- Understanding of risk boundaries in automation

This project demonstrates practical capability across all four.

It also serves as my personal **Security+ / CySA+** study and workflow accelerator.

---

# Author

**Mathias Kucharsyn**  
Cybersecurity Graduate — Canada  
Focused on GRC, SOC fundamentals, and secure AI adoption

---

## 📌 Status

✅ Phase 1 complete: local runtime operational  
🔄 Phase 2 in progress: UI + RAG setup  
🚀 Future: SOC lab automation & documentation pipeline

---
