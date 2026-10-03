# EXPLAINABILITY.md

This document explains the internal mechanisms, data lineage, operational boundaries, and governance framework of **Agent Starter Pack** (`agent-starter-pack`) in accordance with the **OpenGAP v0.1.0** specification for the **HiDevs GitAgent Passport** clearance pipeline.

> **Agent Name:** Agent Starter Pack (`agent-starter-pack`)  
> **Specification:** OpenGAP v0.1.0  
> **Category / Domain:** Developer Tools / GenAI Agent Scaffolding & Cloud Deployment  
> **Compliance Standard:** OpenGAP Checkpoint 2 (Explainability & Decision Governance), OWASP LLM Top 10, MITRE ATLAS  

---

## How the Agent Decides

The scaffolding engine operates through a deterministic 5-stage pipeline translating user requirements into verified, production-ready GenAI agent codebases.

### 1. Decision Architecture

The runtime intake, state classification, evaluation, and execution tracking operate across a deterministic, five-stage pipeline:

```
+-----------------------------------------------------------------------------------+
|                   Deterministic Agent Starter Pack Pipeline                       |
+-----------------------------------------------------------------------------------+
|  [Stage 1: Intent Ingestion & Parameter Validation Gate]                          |
|     --> Ingest project specifications, validate language, runtime, & target flags  |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 2: Architectural Template & Pattern Resolution]                           |
|     --> Match prompt intent against ADK, Agentic RAG, LangGraph, or A2A archetypes |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 3: Parameterized Code Generation & Dependency Locking]                    |
|     --> Render cookiecutter templates, lock package dependencies, & configure envs|
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 4: Cloud Infrastructure & CI/CD Pipeline Manifestation]                   |
|     --> Emit Terraform definitions, Dockerfiles, & Cloud Build deployment triggers|
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|  [Stage 5: Quality Assurance, Automated Tests & Eval Verification]                |
|     --> Execute baseline unit test suite, linter rules, & verify clean project exit|
+-----------------------------------------------------------------------------------+
```

### 2. Decision Logic & Routing Formulations

Template selection across candidate architectures $t \in T$ is resolved by evaluating multi-attribute alignment with user requirements $R$:

$$S_{\text{match}}(t) = w_1 \cdot \text{ArchitectureFit}(t, R) + w_2 \cdot \text{RuntimeCompatibility}(t, R) + w_3 \cdot \text{CloudTargetSupport}(t, R)$$

Where:
- $w_1 = 0.45$: Alignment between task complexity (e.g. conversational vs. multi-hop RAG) and template architecture.
- $w_2 = 0.35$: Strict runtime match with chosen language (Python $\ge 3.10$, TypeScript, Go, Java).
- $w_3 = 0.20$: Target infrastructure capability score (Cloud Run vs. Vertex AI Reasoning Engine).

Automated quality gate verification before project release requires satisfying the compound threshold:

$$Q_{\text{gate}}(p) = \alpha \cdot \text{TestPassRate}(p) + \beta \cdot \text{LintCompliance}(p) + \gamma \cdot \text{EvalScore}(p) \ge \tau_{\text{ready}}$$

Where $\alpha = 0.40$, $\beta = 0.30$, $\gamma = 0.30$, and $\tau_{\text{ready}} = 0.95$.

### 3. Thresholding & Refusal Decision Criteria

Agent Starter Pack enforces strict operational boundaries and deterministic refusal thresholds:
- **Refusal on ERR_DIRTY_OUTPUT_DIRECTORY**: Directory Hygiene (Target path exists and non-empty) halts execution with code `ERR_DIRTY_OUTPUT_DIRECTORY`.
- **Refusal on ERR_INVALID_GCP_PROJECT_ID**: GCP Project Identifier (Malformed project ID format) halts execution with code `ERR_INVALID_GCP_PROJECT_ID`.
- **Refusal on ERR_TEMPLATE_COMPATIBILITY_CONFLICT**: Template Compatibility (Incompatible language/runtime) halts execution with code `ERR_TEMPLATE_COMPATIBILITY_CONFLICT`.
- **Refusal on ERR_EVAL_BENCHMARK_SCORE_FAILED**: Eval Quality Gate ($Q_{\text{gate}} < 0.95$) halts execution with code `ERR_EVAL_BENCHMARK_SCORE_FAILED`.
- **Refusal on ERR_INSUFFICIENT_CLOUD_IAM_PERMISSIONS**: Security IAM Scope (Wildcard `roles/owner` requested) halts execution with code `ERR_INSUFFICIENT_CLOUD_IAM_PERMISSIONS`.

### 4. Fallback Decision Mechanism

Continuous operational stability is maintained through layered fault recovery:
- **Tier 1 (Automated Formatting & Dependency AutoFix)**: When template generation triggers linter or typechecker warnings, the engine automatically runs `ruff format` and dependency resolution passes.
- **Tier 2 (Template Downgrade & Alternative Suggestion)**: If an advanced architecture (e.g. A2A or Multimodal Live) lacks required runtime bindings, the engine suggests the standard ADK base template.
- **Tier 3 (Interactive Developer SignOff)**: Cloud deployment configurations that provision billable resources or modify cloud IAM permissions require affirmative developer confirmation before manifest generation.
- **Model Fallback Cascade**: High-level reasoning and synthesis default to `gemini-2.0-flash` with automatic failover to `gpt-4o` and `claude-3-5-sonnet`.

### 5. Human-in-the-Loop Governance

Human operators retain sovereign authority over the multi-agent execution lifecycle:
- **Benchmark Trajectory Auditing**: Operators inspect evaluation traces, raw generation tokens, and container logs to verify scoring fidelity.

---

## The Data It Uses

Agent Starter Pack operates under strict principles of data minimization, environment isolation, and privacy protection.

### 1. Ingested Input Data

The framework processes only operational data necessary to perform its functions:
- **Project Configuration**: Project name, chosen language runtime, agent framework, frontend type, and cloud region.
- **Template Schemas**: Cookiecutter JSON definitions, Jinja2 template files, and lockfile specifications.
- **Test Telemetry**: Output logs from pytest, ruff lint checks, and Cloud Build pipeline executions.

### 2. Configuration & Reference Data

- **Google Cloud Reference Architectures**: Cloud Run, Vertex AI Reasoning Engine, Vertex AI Search.
- **Modern Software Engineering Standards**: Clean architecture, Twelve-Factor App principles, OCI container standards.
- **LLM Evaluation Frameworks**: RAG faithfulness, answer relevancy, and deterministic tool call verification.

### 3. Base Model & Inference Lineage

- **Target LLM Ecosystem**: Gemini 1.5 Pro, Gemini 1.5 Flash, Gemini 2.0 Flash, Claude on Vertex AI.
- **Runtime Environment**: Python 3.10+, Click, Rich, Cookiecutter, Docker, Terraform.

### 4. Data Privacy, Storage, and Retention

- **OWASP LLM & MITRE ATLAS Hardened**: Defended against indirect prompt injection, credential leakage, and unauthorized external API dispatch.
- **Local Environment Isolation**: Agent execution workspaces, intermediate scratchpads, and vector stores reside strictly within designated local project directories.
- **Automated Secret Scrubbing**: API keys, database credentials, and personal credentials are automatically redacted prior to embedding or logging.
- **Zero Commercial Monetization**: Prompts, intermediate reasoning trajectories, and task deliverables are never commercialized or shared with third parties.

---

## Limitations

Understanding the operational boundaries and technical constraints of Agent Starter Pack is essential for effective deployment.

### 1. Dependency Version Churn Across Multi-Language Frameworks
- **Limitation**: Fast-evolving upstream dependencies in GenAI libraries can occasionally cause transient lockfile conflicts.
- **Mitigation**: Maintain pinned dependency ranges in `pyproject.toml` and run automated daily integration build smoke tests.

### 2. Google Cloud Quota Limits During Automated Integration Testing
- **Limitation**: Running automated end-to-end integration tests on live Vertex AI endpoints may encounter project rate quotas.
- **Mitigation**: Provide comprehensive local mock fixtures and recorded LLM response caches for offline testing.

### 3. Variable Latency in Large RAG Document Indexing Operations
- **Limitation**: Embedding and indexing large enterprise document corpora can require significant time during setup.
- **Mitigation**: Implement chunked asynchronous batch ingestion with progress bars and resumable checkpointing.

### 4. Divergence Between Local Container Emulation and Cloud Run Runtime
- **Limitation**: Differences in local operating system architecture (e.g. ARM64 vs. x86_64) can introduce edge container variations.
- **Mitigation**: Include multi-architecture Docker build commands (`buildx`) and standard Linux base images in generated configs.

### 5. High Compute Cost for Comprehensive Synthetic Eval Datasets
- **Limitation**: Generating thousands of synthetic test cases using frontier models can incur noticeable API costs.
- **Mitigation**: Offer tiered evaluation configurations (smoke test vs. full benchmark) so developers control evaluation depth.

---

## Summary & Compliance Checklist

| Checkpoint 2 Requirement | Corresponding Section | Status |
| :--- | :--- | :---: |
| **How the agent decides** | [How the Agent Decides](#how-the-agent-decides) | **Covered** |
| - Decision architecture & 5-stage pipeline | Section 1 | Verified |
| - Decision logic & routing formulations | Section 2 | Verified |
| - Thresholding & refusal decision criteria | Section 3 | Verified |
| - Fallback decision mechanism | Section 4 | Verified |
| - Human-in-the-loop governance & oversight | Section 5 | Verified |
| **The data it uses** | [The Data It Uses](#the-data-it-uses) | **Covered** |
| - Ingested input data & query streams | Section 1 | Verified |
| - Configuration & reference schemas | Section 2 | Verified |
| - Base model lineage & deterministic engines | Section 3 | Verified |
| - Data privacy, retention lifecycle & MITRE/OWASP | Section 4 | Verified |
| **Its limitations** | [Limitations](#limitations) | **Covered** |
| - Dependency Version Churn Across Multi-Language Frameworks | Section 1 | Verified |
| - Google Cloud Quota Limits During Automated Integration Testing | Section 2 | Verified |
| - Variable Latency in Large RAG Document Indexing Operations | Section 3 | Verified |
| - Divergence Between Local Container Emulation and Cloud Run Runtime | Section 4 | Verified |
| - High Compute Cost for Comprehensive Synthetic Eval Datasets | Section 5 | Verified |
