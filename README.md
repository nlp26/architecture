# architecture

Reference catalog of production architecture patterns for AI agents and modern SWE. One notebook, one pattern per cell, runnable mocks. Where a pattern has a full reproduction, the source repo is linked next to it.

The notebook is `modern_architecture_patterns_2026.ipynb`. Each cell stands alone and runs without dependencies — you can read top to bottom or jump.

## Sections

1. **Agentic Architecture Patterns** — ReAct, Plan-and-Execute, Deep Agents Harness
2. **Tool-Use & Function Calling** — Tool Registry, MCP Server/Client, Code-Execution with MCP
3. **Memory & State Management** — Layered Memory, Environment-Experience Memory
4. **Multi-Agent Orchestration** — Supervisor, Pipeline, Swarm, Quality-Gated Granularity
5. **Retrieval-Augmented Generation** — Agentic RAG, Adaptive RAG (routed), Process-Supervised RAG
6. **Evaluation & Observability** — Tracing, LLM-as-Judge, Agent-as-a-Judge, Distilled Judge
7. **Modern SWE Patterns** — Structured Output, Circuit Breaker, Event Bus
8. **Deployment & Infrastructure** — Model Routing, Guardrails, Cost Tracking, Stateless MCP + OAuth 2.1
9. **Anti-Patterns** — failure modes seen repeatedly in 2026 agent code
10. **Decision Guide** — picking the smallest pattern that solves the problem

## Runnable companion code

Patterns in this notebook are conceptual mocks. Working implementations of the agentic ones live in separate repos:

| Pattern | Repo |
|---|---|
| 1C Deep Agents Harness | [nlp26/langchain-deepagents](https://github.com/nlp26/langchain-deepagents) — deepagents 0.6.2 + MCP + FastAPI |
| 2B / 2C MCP Server + Code-Execution | [nlp26/langchain-deepagents](https://github.com/nlp26/langchain-deepagents) — FastMCP child process over stdio |
| 4D Quality-Gated Granularity | [nlp26/agentic-papers/agent_capsules](https://github.com/nlp26/agentic-papers/tree/main/agent_capsules) — −38.7% tokens vs baseline (mock) |
| 5C Process-Supervised RAG | [nlp26/agentic-papers/rag_gym](https://github.com/nlp26/agentic-papers/tree/main/rag_gym) — per-step scoring, Re²Search |
| 6 / 6B Judge | [nlp26/agentic-papers/agent_as_judge](https://github.com/nlp26/agentic-papers/tree/main/agent_as_judge) — rubric + CoT + calibration |

## Run

```bash
jupyter notebook modern_architecture_patterns_2026.ipynb
```

Or open in any IDE that renders `.ipynb`. No `pip install` required — every cell uses stdlib only and runs end-to-end.

## What changed in this revision

The catalog evolved against May 2026 sources. New: Deep Agents Harness (1C), MCP Server/Client (2B), Code-Execution with MCP (2C), Environment-Experience Memory (3B), Quality-Gated Granularity (4D), Adaptive RAG (5B), Process-Supervised RAG (5C), Agent-as-a-Judge (6B), Distilled Judge (6C), Stateless HTTP MCP + OAuth 2.1 (8D), plus Anti-Patterns and a Decision Guide.

## License

Apache-2.0
