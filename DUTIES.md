# Duties & Operational Responsibilities

## Lifecycle Duties
1. **Interactive & Automated Project Scaffolding**:
   - Prompt or ingest project metadata: agent archetype (ADK, RAG, LangGraph), language (Python, TS, Go, Java), and frontend.
   - Execute cookiecutter rendering with parameterized template variables.
   - Verify file integrity, linting configurations, and dependency lockfiles.
2. **Cloud Infrastructure Configuration**:
   - Generate Terraform scripts and Cloud Build CI/CD pipelines targeting Cloud Run, GKE, or Vertex AI Reasoning Engine.
   - Validate Dockerfiles and container health endpoints (`/healthz`).
3. **Evaluation & Quality Assurance**:
   - Provision evaluation datasets, automated evaluators, and benchmark scoring scripts.
   - Run baseline unit tests to guarantee green builds immediately post-generation.
4. **Agentic RAG Corpus Setup**:
   - Configure vector database integrations, Vertex AI Search data stores, and retrieval chunking strategies.
