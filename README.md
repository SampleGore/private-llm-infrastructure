![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-success)
![Stack](https://img.shields.io/badge/stack-Docker%20%7C%20Ollama%20%7C%20OpenWebUI%20%7C%20AnythingLLM-blue)
![Security](https://img.shields.io/badge/security-local_only,%20min_priv-blueviolet)

# Local Cybersecurity AI Assistant — Homelab Project

This project implements a fully local, privacy-preserving LLM assistant configured to support cybersecurity study, analysis, and governance workflows. The system runs offline using Docker and Ollama, with extensible Retrieval-Augmented Generation (RAG) for querying personal documents such as white papers, reports, and training materials.

The goal of this project is to integrate practical cybersecurity tooling with AI-assisted research and documentation — while maintaining strict boundaries for safety, trust, and accuracy.

## Architecture at a Glance

User → OpenWebUI → AnythingLLM → Ollama (models)
              ↘ logs/metrics ↙

---

## Quickstart

### 1) Configure env (no secrets in Git)
# Linux/macOS
cp .env.sample .env
# Windows PowerShell
Copy-Item .env.sample .env

# Edit .env and set your real values (e.g., SECRET_KEY)

### 2) Launch
docker compose up -d

### 3) Access
OpenWebUI:  http://localhost:${OPENWEBUI_PORT:-3000}
Ollama API: http://localhost:${OLLAMA_PORT:-11434}

### 4) Stop / Logs
docker compose down
docker compose logs -f

---

## Security Highlights
- Local-only networking (127.0.0.1)
- Minimal-privilege containers; separate config and data volumes
- No secrets in VCS; `.env` used for runtime secrets
- Behavior probing in progress (hallucination, jailbreak attempts, identity drift)

---

## Behavior Probing (Active)
Focus areas:
- Topic switching stability (cyber → physics → lore → AGI)
- Boundary adherence / jailbreak attempt resistance
- Identity drift & “buffer references”
- Stability under token load

---

## Runbook (Common tasks)
# Pull latest images
docker compose pull

# Recreate after config changes
docker compose up -d --force-recreate

# Healthcheck poke (Ollama tags endpoint)
curl http://localhost:${OLLAMA_PORT:-11434}/api/tags

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
