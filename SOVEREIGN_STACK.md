# Sovereign Stack — InsightsLM fork notes

This is the EagleEyeVisionLabz fork of theaiautomators/insights-lm-public.

## Role in the stack

- **InsightsLM** (this repo) — RAG / NotebookLM-style research over your docs, wired to local Ollama models.
- **Open Notebook** — separate research notebook app (installing).
- **Open Knowledge** — LLM wiki / knowledge base.
- **Płane** — notes.
- **Colanode** — planners + handwriting.
- **Plane** — projects + work items (replacing Linear/Jira/Atlassian).

## Wiring

- Local models via Ollama (Qwen) — no cloud inference required for the core loop.
- n8n workflows orchestrate extract → embed → vector store → chat.
- Findings and bot-template specs from the daily audit pipeline land here as source documents for RAG.

## License

MIT for this codebase. n8n (backend) is Sustainable Use — internal use OK; Enterprise license required if reselling hosted access.
