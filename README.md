<div align="center">

# Hi, I'm Hazem Haddar 👋

### Software Engineering Student @ ENIT

**Multi-Agent Systems • Information Retrieval & RAG • Generative AI Evaluation • Cloud-Native Intelligent Systems**

I am a software engineering student interested in going beyond simply using AI models.

I want to understand how intelligent systems are **designed, orchestrated, evaluated, tested, deployed, and made reliable in real applications**.

<p>
  <a href="https://www.linkedin.com/in/hazem-haddar-28a988284/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="https://github.com/haddarhazem" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
</p>

</div>

---

## About Me

- 🎓 Software Engineering student at **ENIT, École Nationale d'Ingénieurs de Tunis**
- 🤖 Interested in **Agentic AI, Multi-Agent Systems, RAG, and LLM-powered applications**
- 🔎 Exploring **Information Retrieval, embeddings, vector search, reranking, and evidence-grounded generation**
- 🧪 Interested in evaluating AI systems through **controlled experiments, benchmarks, metrics, and documented engineering decisions**
- ☁️ Building toward **cloud-native intelligent systems** combining AI, backend engineering, databases, APIs, security, and infrastructure
- 🌍 Open to **AI / GenAI research-oriented internships and engineering opportunities**

---

# Featured Projects

## 🧠 RegBridge

### Research-Oriented GenAI & Multi-Agent Platform

[![Repository](https://img.shields.io/badge/Repository-RegBridge-181717?style=for-the-badge&logo=github)](https://github.com/haddarhazem/RegBridge)

**RegBridge** is my main project for exploring the engineering and evaluation of LLM-powered and multi-agent systems.

The platform targets the French entrepreneurship, startup, investment, and scientific-research ecosystem and combines specialized AI capabilities with retrieval, orchestration, verification, and evidence-grounded generation.

### What I Work On

#### Multi-Agent Orchestration

Exploring how specialized AI capabilities can be coordinated through a central orchestrator while maintaining:

- authorization boundaries
- traceability
- predictable execution
- testability
- extensibility
- controlled failure handling

This included comparing lightweight Python-based orchestration with structured workflow approaches such as **LangGraph**.

#### Regulatory RAG

Building and evaluating retrieval pipelines for French regulatory information.

Topics and technologies include:

- **BGE-M3 embeddings**
- **Qdrant vector search**
- dense retrieval
- retrieval benchmarks
- evidence grounding
- Recall@k
- Precision@k
- MRR
- evidence coverage

The objective is not simply to generate an answer, but to ensure that the answer is supported by relevant regulatory evidence.

#### Generative AI Evaluation

A major part of RegBridge is evaluating AI behavior instead of relying only on subjective output inspection.

Areas explored include:

- groundedness
- unsupported claims
- citation correctness
- structured-output validity
- retrieval quality
- latency
- token usage
- cost
- provider reliability

#### AI Reliability & Safety

I am also exploring mechanisms for making LLM-based systems more reliable, including:

- deterministic validation
- verification stages
- trusted vs untrusted context separation
- prompt-injection defense
- evidence-constrained generation
- authorization-aware agent execution

### Research-Oriented Engineering Workflow

For meaningful technical uncertainty, I try to follow a workflow similar to:

```text
Research Question
        ↓
Hypothesis
        ↓
Candidate Approaches
        ↓
Experimental Protocol
        ↓
Controlled Experiment
        ↓
Metrics
        ↓
Results
        ↓
Interpretation
        ↓
Limitations
        ↓
Engineering Decision
        ↓
Production Implementation
```

### RegBridge Research Topics

Some of the technical questions investigated or documented in the project include:

```text
RQ-001  Orchestration architecture

RQ-002  Regulatory information retrieval

RQ-003  Response verification

RQ-004  Model quality / latency / cost trade-offs

RQ-027  Prompt-injection defense-in-depth
```

Additional areas include:

- evidence-constrained scientific information extraction
- research / startup matching
- compliance-related AI systems
- factuality verification
- retrieval and ranking strategies

📚 [Engineering Research](https://github.com/haddarhazem/RegBridge/tree/main/docs/engineering-research)

📋 [Research Agenda](https://github.com/haddarhazem/RegBridge/blob/main/docs/engineering-research/RESEARCH_AGENDA.md)

🧪 [Experiment Results](https://github.com/haddarhazem/RegBridge/tree/main/docs/engineering-research/results)

---

## 🧾 InvoiceScanner

### Cloud-Native AI System for Tunisian Invoice Processing

**ENIT End-of-Year Project II • 2025–2026**

Co-developed with **Mohamed Ali Besbes**

[![Repository](https://img.shields.io/badge/Repository-PFA2%20InvoiceScanner-181717?style=for-the-badge&logo=github)](PASTE_PFA2_REPOSITORY_URL_HERE)

**InvoiceScanner** is a cloud-native mobile application designed to transform physical Tunisian invoices into structured digital information using **document understanding, OCR, Large Language Models, and domain-specific validation**.

The project was motivated by the transition toward electronic invoicing in Tunisia and the difficulty small businesses face when converting existing paper invoices into structured digital formats.

### AI Processing Pipeline

```text
Invoice Image / PDF
        ↓
Docling
Document Layout Analysis
        ↓
RapidOCR
Text & Spatial Extraction
        ↓
LLM through Groq API
Structured Information Extraction
        ↓
Tunisian Validation Rules
        ↓
Human Verification
        ↓
TEIF XML Export
```

Rather than relying on OCR alone, the system combines document structure, character recognition, LLM-based information extraction, domain-specific validation, and human verification.

### 🇹🇳 Tunisian Invoice Adaptation

A central challenge was that generic extraction systems do not understand many Tunisian financial-document conventions.

The system therefore includes domain-specific validation for:

- **Matricule Fiscal**
- **TVA rates**
- **TND / DT currency formats**
- comma-based decimal notation
- **Timbre Fiscal**
- French-language financial terminology

This validation layer acts between AI extraction and final invoice generation, reducing incorrect financial values before they reach the user.

### Human-in-the-Loop Verification

Because financial documents cannot safely rely on AI predictions alone, the application preserves a human validation step.

Users can:

1. Scan or upload an invoice
2. Wait for asynchronous AI extraction
3. Review the extracted information
4. Correct individual fields or line items
5. Validate the invoice
6. Generate the TEIF XML representation

The system keeps the original AI extraction separate from the human-corrected data, creating a clear audit trail.

### Cloud-Native Architecture

The system follows an API-first, stateless client-server architecture.

```text
Flutter Mobile App
        ↓
      HTTPS
        ↓
NGINX Reverse Proxy
        ↓
FastAPI Backend
   ↙        ↓        ↘
PostgreSQL Firebase  AI Pipeline
             ↓
   Firestore / Storage / FCM
```

Key architectural decisions include:

- **Flutter + Riverpod** mobile client
- **FastAPI** asynchronous backend
- **JWT access / refresh authentication**
- **PostgreSQL** for relational application data
- **Firebase Firestore** for flexible AI-generated document data
- **Firebase Storage** for invoice files
- **Firebase Cloud Messaging** for asynchronous processing notifications
- **Alembic** for database migrations
- **NGINX** as reverse proxy and TLS termination
- **Docker** containerization
- **DigitalOcean** production hosting

### Asynchronous Processing

OCR and document understanding can require tens of seconds to complete, so invoice extraction does not block the mobile application.

The backend creates the invoice with a pending state and performs the AI pipeline in the background.

When processing completes:

```text
FastAPI
   ↓
Firebase Cloud Messaging
   ↓
Flutter
   ↓
Riverpod State Invalidation
   ↓
Dashboard Automatically Refreshes
```

This avoids continuous polling and keeps the application responsive during long-running AI operations.

### DevOps & Production Engineering

The project was not limited to a local prototype.

The backend was containerized and deployed to a live DigitalOcean environment through an automated GitHub Actions pipeline.

```text
Developer Push
      ↓
GitHub Actions
      ↓
Code Quality
      ↓
Security Analysis
      ↓
API Tests
      ↓
Docker Build
      ↓
GitHub Container Registry
      ↓
Automated Deployment
      ↓
DigitalOcean
```

Engineering practices included:

- Docker / Docker Compose
- GitHub Actions
- GitHub Container Registry
- automated API tests
- Ruff and Black
- Bandit SAST
- pip-audit dependency scanning
- pre-commit hooks
- NGINX
- TLS / HTTPS
- CI/CD deployment gates

### Tech Stack

`Flutter` • `Dart` • `Riverpod` • `Python` • `FastAPI` • `Docling` • `RapidOCR` • `PyTorch` • `LangChain` • `Groq` • `PostgreSQL` • `Firebase Firestore` • `Firebase Storage` • `FCM` • `Alembic` • `Docker` • `NGINX` • `GitHub Actions` • `DigitalOcean`

---

## 🌱 GeoAI Decision Support System

[![Repository](https://img.shields.io/badge/Repository-AGRI_AI_PROJECT-181717?style=for-the-badge&logo=github)](https://github.com/haddarhazem/AGRI_AI_PROJECT)

A geospatial AI system for crop recommendation using atmospheric, soil, climate, and topographical information.

### Highlights

- Integrates **Copernicus DEM, Open-Meteo, and OpenWeatherMap**
- Uses a **Random Forest** model for crop recommendation
- Includes agronomic guardrails designed to reduce extrapolation bias
- Exposes predictions through a **FastAPI** backend
- Produces **KML / Google Earth** visualizations
- Includes an interactive **React / Three.js** interface

### Topics

`GeoAI` • `Machine Learning` • `Remote Data Sources` • `FastAPI` • `Geospatial Visualization`

---

## 🔗 LLM Application Development

[![Repository](https://img.shields.io/badge/Repository-LangChain_for_LLM_Application_Development-181717?style=flat-square&logo=github)](https://github.com/haddarhazem/LangChain-for-LLM-Application-Development)

Learning and experimentation around building applications powered by Large Language Models.

Topics include:

- prompting
- chains
- retrieval
- LLM application architecture
- orchestration concepts

---

## ⚙️ ML Engineering & Infrastructure

I also use smaller projects and experiments to strengthen the engineering surrounding AI systems.

[![CI/CD ML](https://img.shields.io/badge/CI%2FCD_for_ML-Repository-181717?style=flat-square&logo=github)](https://github.com/haddarhazem/ci-cd-for-ml-demo)

[![Kubernetes](https://img.shields.io/badge/Kubernetes-Demo-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://github.com/haddarhazem/kubernetes-demo)

These complement my AI work with concepts such as:

- containerization
- CI/CD
- automated testing
- deployment
- reproducibility
- cloud-native infrastructure

---

# Areas of Interest

| Area | Current Focus |
| --- | --- |
| **Multi-Agent Systems** | Orchestration, routing, specialized agents, authorization, workflows |
| **Information Retrieval & RAG** | Embeddings, vector databases, ranking, evidence retrieval |
| **Generative AI Evaluation** | Benchmarks, groundedness, factuality, quality, latency and cost |
| **Reliable AI Systems** | Verification, prompt-injection defenses, failure handling |
| **Document AI** | OCR, layout analysis, information extraction, structured outputs |
| **Cloud-Native Intelligent Systems** | APIs, containers, databases, CI/CD and scalable AI infrastructure |

---

# Technical Toolbox

### AI & Retrieval

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=flat-square)
![LangGraph](https://img.shields.io/badge/LangGraph-Agent_Orchestration-1C3C3C?style=flat-square)
![Mistral AI](https://img.shields.io/badge/Mistral_AI-LLM-FF7000?style=flat-square)
![Groq](https://img.shields.io/badge/Groq-LLM_Inference-F55036?style=flat-square)

**Concepts**

`RAG` • `Embeddings` • `Vector Search` • `Agent Orchestration` • `LLM Evaluation` • `Evidence Grounding` • `OCR` • `Document AI`

---

### Backend & Data

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)

**Concepts**

`REST APIs` • `Async Python` • `Database Migrations` • `Authentication` • `Authorization` • `Testing` • `Polyglot Persistence`

---

### Mobile & Frontend

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=flat-square&logo=dart&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)

**Concepts**

`Reactive UI` • `Asynchronous State Management` • `Riverpod` • `Mobile API Integration`

---

### Infrastructure & Engineering

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![NGINX](https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=nginx&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**Concepts**

`CI/CD` • `Containers` • `Reverse Proxy` • `TLS` • `SAST` • `Dependency Scanning` • `Cloud Deployment`

---

### Programming

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)

---

# What I Want to Work On

I am particularly interested in projects involving:

```text
Agentic AI
Multi-Agent Systems
Dynamic Agent Workflows
Retrieval-Augmented Generation
Information Retrieval
LLM Evaluation
AI Reliability
Generative AI
Document AI
AI Infrastructure
Cloud-Native AI Systems
```

I am especially interested in environments where I can both **build systems and investigate why one technical approach performs better than another**.

---

# GitHub Activity

<div align="center">

<img
  height="170em"
  src="https://github-readme-stats.vercel.app/api?username=haddarhazem&show_icons=true&hide_border=true&include_all_commits=true&count_private=true"
  alt="Hazem Haddar GitHub statistics"
/>

<img
  height="170em"
  src="https://github-readme-stats.vercel.app/api/top-langs/?username=haddarhazem&layout=compact&hide_border=true"
  alt="Most used languages"
/>

</div>

---

# Let's Connect

I am open to opportunities involving:

**Generative AI • Agentic Systems • RAG • Information Retrieval • AI Evaluation • Document AI • Reliable AI Engineering**

<div align="center">

<a href="https://www.linkedin.com/in/hazem-haddar-28a988284/">
  <img src="https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>

<a href="https://github.com/haddarhazem">
  <img src="https://img.shields.io/badge/Explore_My_Repositories-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>

</div>

<br/>

<div align="center">

<img
  src="https://komarev.com/ghpvc/?username=haddarhazem&label=Profile+Views&style=flat"
  alt="Profile views"
/>

</div>
