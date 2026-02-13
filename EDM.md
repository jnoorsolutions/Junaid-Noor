# 🧠 Enterprise Document Manager + RAG + Multi-Agent AI Platform

An enterprise-grade, multi-tenant AI orchestration platform combining:

- Secure Document Management
- Retrieval-Augmented Generation (RAG)
- Multi-Agent Orchestration
- MCP (Model Context Protocol) Integration
- Token Quota Governance
- Tool Access Control & Bypass Rules
- 3-Tier LLM Configuration Resolution
- On-Prem / SAN / NAS Deployment Support

---

## 🚀 Core Capabilities

### 🔹 1. Secure Multi-Tenant Architecture

- Organization → Department → Section hierarchy
- Section-level isolation
- Role-Based Access Control (RBAC)
- Attachment ownership enforcement
- SMTP identity alignment validation

Designed for regulated industries (Healthcare, Finance, Legal).

---

### 🔹 2. Dynamic LLM Provider Factory

Supports:

- OpenAI
- Groq
- Google (Gemini)
- Anthropic
- HuggingFace
- Azure OpenAI
- Ollama (On-Prem)

Features:

- Dynamic provider resolution
- Encrypted API key storage
- Provider matrix validation (unit + smoke tests)
- CI-safe provider validation
- Section-level provider override

---

### 🔹 3. 3-Tier AI Configuration Resolution

- Organization-level configuration
- Department-level override
- Section-level override
- Deterministic fallback logic
- Embedding provider resolution
- Retriever provider resolution

---

### 🔹 4. Token Quota Management

Enterprise-grade governance:

- Per-user token allocation
- 90% usage warning trigger
- Immediate hard stop at quota = 0
- Audit-ready tracking
- Rate limit enforcement
- Abuse prevention

---

### 🔹 5. Tool Governance & MCP Integration

- Tool assignment per section
- Role-based tool validation
- Tool bypass rules (case-insensitive enforcement)
- Rate limit per tool
- External tool orchestration (DB / MCP / App tools)
- Multi-agent tool execution pipeline

Planner → ToolService → Composer architecture

---

### 🔹 6. Agentic AI Architecture

- Single-Agent orchestration
- Multi-Agent orchestration
- Deterministic tool sequencing
- RAG fallback mode
- Tool error handling
- Controlled tool injection

---

### 🔹 7. Secure Document & Vector Management

- Chroma Vector DB
- Secure file storage
- Version management
- Duplicate detection
- OCR support (Image / Scanned PDF)
- SAN / NAS ready storage

---

## 🏢 Enterprise Use Cases

✔ Healthcare (HIPAA-aligned document intelligence)  
✔ Financial institutions (SOC2 governance-ready)  
✔ Legal firms (secure case intelligence)  
✔ Corporate knowledge management  
✔ Manufacturing compliance  
✔ Educational institutions  

---

## 🛠 Technical Stack

### Backend
- Python 3.11
- FastAPI
- SQLAlchemy
- Celery
- PostgreSQL / SQLite (testing)

### AI Stack
- LangChain
- LangGraph
- Chroma
- MCP
- Multi-Provider LLM Factory

### Governance
- Token quota enforcement
- Tool bypass rules
- 3-tier configuration resolution
- Encrypted credential storage

---

## 🔬 Testing & Quality

- 3-Tier resolution validation
- Provider matrix testing
- Multi-agent orchestration tests
- Token quota enforcement tests
- Tool governance validation
- SMTP resolution validation
- End-to-End integration tests
- CI-safe provider validation

---

## 🏗 Deployment Options

- Local Development
- Cloud (UAT / Production)
- On-Premise Deployment
- SAN / NAS-mounted storage
- Offline LLM (Ollama support)

---

## 🔐 Security Highlights

- Encrypted API keys
- Role-based tool execution
- Strict SMTP identity validation
- Section-based data isolation
- Audit logging
- Deterministic orchestration paths

---

## 📌 Status

Production-ready backend  
Frontend (Next.js + ShadCN) in progress  

Last major test update: FEB-2026

---

## 🧠 Architecture Diagram (Visual Explanation Style)

                         ┌──────────────────────────┐
                         │      Frontend UI         │
                         │  (Next.js / ShadCN)      │
                         └────────────┬─────────────┘
                                      │
                                      ▼
                         ┌──────────────────────────┐
                         │       FastAPI API        │
                         │ Auth + RBAC + Routing    │
                         └────────────┬─────────────┘
                                      │
             ┌────────────────────────┴────────────────────────┐
             ▼                                                 ▼
 ┌─────────────────────┐                           ┌─────────────────────┐
 │ Governance Engine   │                           │ AI Orchestration    │
 │                     │                           │ Engine              │
 │ - Token Quota       │                           │                     │
 │ - Rate Limit        │                           │ - Planner Agent     │
 │ - Tool Bypass       │                           │ - ToolService       │
 │ - Role Validation   │                           │ - Composer          │
 └─────────────────────┘                           └──────────┬──────────┘
                                                                │
                          ┌─────────────────────────────────────┴─────────────────────────────┐
                          ▼                                                                   ▼
              ┌────────────────────┐                                              ┌────────────────────┐
              │ RAG Layer          │                                              │ Tool Layer         │
              │                    │                                              │                    │
              │ - Chroma Vector DB │                                              │ - App Tools        │
              │ - Retriever        │                                              │ - DB Tools         │
              │ - Embeddings       │                                              │ - MCP Tools        │
              └──────────┬─────────┘                                              └──────────┬─────────┘
                         │                                                              │
                         ▼                                                              ▼
              ┌────────────────────┐                                        ┌────────────────────┐
              │ LLM Provider       │                                        │ External Systems   │
              │ Factory            │                                        │ SMTP / DB / APIs   │
              │                    │                                        └────────────────────┘
              │ OpenAI             │
              │ Groq               │
              │ Google             │
              │ Azure              │
              │ Anthropic          │
              │ Ollama             │
              └────────────────────┘

---
