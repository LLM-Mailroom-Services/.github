<div align="center">

# 📬 MAILROOM INCORPORATED ™

**The organization behind the LLM-Mailroom constellation — a governed, multi-agent legal-document processing platform built as one reproducible ecosystem.**

Multi-agent pipeline · Prompt-experiment loop · Deterministic scoring · Pixel-art visualizer · Walking-office-floor mailroom · Corpus EDA

[![Organization](https://img.shields.io/badge/organization-LLM--Mailroom--Services-181717?logo=github)](https://github.com/LLM-Mailroom-Services)
[![Repositories](https://img.shields.io/badge/repositories-10%20managed-6C63FF)](https://github.com/orgs/LLM-Mailroom-Services/repositories)
[![Python 3.11+](https://img.shields.io/badge/python-3.11%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green)](https://github.com/LLM-Mailroom-Services/Digital-Mailroom/blob/main/LICENSE)


</div>

---

## ⚚ About Us...

**Mailroom Incorporated™** (`LLM-Mailroom-Services`) is the governing organization for the **LLM-Mailroom** — an open, reproducible platform that reads, classifies, extracts from, and archives legal and business documents with a coordinated team of specialist LLM agents.

Everything is governed: one monorepo is the central truth, every package mirrors an independent upstream repository, and a machine-readable task board keeps work claimed, evidenced, and closed. The organization's repositories are the coordination surface for that work — the pipeline, the corpora, the experiments, the evaluations, and the people who run them.

## Architecture

```plaintext
                    ┌── corpus feeds (colocated data) ─────────────────────┐
                    │  Enron-Evaluation-Environment   claims-data-eda      │
                    │  mailroom-corpus-eda   (mailroom-corpus, P0–P6 EDA)  │
                    └──────────────────────────┬───────────────────────────┘
                                               ▼
                    ┌── prompt-experiment loop ────────────────────────────┐
                    │  llm-entity-extraction        (GEPA prompt versions) │
                    └──────────────────────────┬───────────────────────────┘
                                               ▼
┌────────────────────────┐        ┌───────────────────────────────────────┐
│  llm-dojo-scoring      │◀───────│           llm-mailroom                │
│  shared scoring engine │ import │  LangGraph multi-agent pipeline       │
└────────────────────────┘        └──────────────────┬────────────────────┘
                                                     ▼
                    ┌── surfaces ──────────────────────────────────────────┐
                    │  The-Mailroom (visualizer)     agent-mailroom        │
                    │  local-mailroom-sandbox        llm-mailroom-graph    │
                    └──────────────────────────┬───────────────────────────┘
                                               ▼
                    ┌──────────────────────────────────────────────────────┐
                    │            Digital-Mailroom — the hub monorepo       │
                    │        (central truth; every box lives in it)        │
                    └──────────────────────────────────────────────────────┘
```

## Projects under management

The org operates the **hub and coordination surfaces** directly, and mirrors the **ten-package constellation** as git subtrees. Upstream `Exios66/*` repositories remain the independent release vehicles; `Digital-Mailroom` is the development source of truth.

### Organization repositories

<div align="center">

| Layer | Repository | Role | Surface |
| :--- | :--- | :--- | :--- |
| **Hub** (central truth) | [`LLM-Mailroom-Services/Digital-Mailroom`](https://github.com/LLM-Mailroom-Services/Digital-Mailroom) | Standalone monorepo — pipeline, governance, ten packages | [Dispatch Board](https://digital-mailroom-theta.vercel.app) |
| **Issue hub** | [`LLM-Mailroom-Services/mailroom-issues`](https://github.com/LLM-Mailroom-Services/mailroom-issues) | Cross-repo issues, epics, RFCs, label taxonomy | — |
| **Evaluation** | [`LLM-Mailroom-Services/eval-environment`](https://github.com/LLM-Mailroom-Services/eval-environment) | Per-node performance evals, pilots, calibration suites | [eval-environment.vercel.app](https://eval-environment.vercel.app) |
| **Prompt experiments** | [`LLM-Mailroom-Services/Entity-Extraction-Experiments`](https://github.com/LLM-Mailroom-Services/Entity-Extraction-Experiments) | Prompt-experiment loop (GEPA) over CUAD / LegalBench / MAUD | — |
| **Corpus EDA** | [`LLM-Mailroom-Services/Mailroom-Corpus`](https://github.com/LLM-Mailroom-Services/Mailroom-Corpus) | Full-corpus EDA for the mailroom-dataset family | — |
| **Local sandbox** | [`LLM-Mailroom-Services/mailroom-sandbox`](https://github.com/LLM-Mailroom-Services/mailroom-sandbox) | Local-first pipeline sandbox (Ollama, vLLM, llama.cpp) | — |
| **Corporate monorepo** | [`LLM-Mailroom-Services/mailroom-ops`](https://github.com/LLM-Mailroom-Services/mailroom-ops) | HUB-era board, history & package release home (archived) | — |
| **Org profile** | [`LLM-Mailroom-Services/.github`](https://github.com/LLM-Mailroom-Services/.github) | Organization profile and community health files | this page |

</div>

### The ten-package constellation

Every package lives in `Digital-Mailroom/packages/` as a git subtree and mirrors an independent upstream repository.

<div align="center">

| Layer | Package | Role | Source |
| :--- | :--- | :--- | :--- |
| **Scoring engine** | `llm-dojo-scoring` | Deterministic scoring, error-analysis, visualization & interpretation suite | [`Exios66/llm-dojo-scoring`](https://github.com/Exios66/llm-dojo-scoring) |
| **LangGraph pipeline** | `llm-mailroom` | 13-node multi-agent legal-document pipeline (FastAPI producer) | [`Exios66/llm-mailroom`](https://github.com/Exios66/llm-mailroom) |
| **Prompt experiments** | `llm-entity-extraction` | Prompt versions × models over CUAD / LegalBench / MAUD | [`Exios66/llm-entity-extraction`](https://github.com/Exios66/llm-entity-extraction) |
| **Pixel visualizer** | `The-Mailroom` | Pixel-art console + hosted Observatory (Langfuse as source of truth) | [`Exios66/The-Mailroom`](https://github.com/Exios66/The-Mailroom) |
| **Walking floor** | `agent-mailroom` | One state machine per document, specialist agents at desks | [`Exios66/agent-mailroom`](https://github.com/Exios66/agent-mailroom) |
| **Local sandbox** | `local-mailroom-sandbox` | Local-first experiment sandbox (Ollama, vLLM, llama.cpp) | [`Exios66/local-mailroom-sandbox`](https://github.com/Exios66/local-mailroom-sandbox) |
| **Corpus feed** | `Enron-Evaluation-Environment` | Enron corpus EDA → pipeline-ready correspondence dataset | [`Exios66/Enron-Evaluation-Environment`](https://github.com/Exios66/Enron-Evaluation-Environment) |
| **Corpus feed** | `claims-data-eda` | CMS DE-SynPUF EDA → pipeline-ready insurance_claim dataset | [`Exios66/claims-data-eda`](https://github.com/Exios66/claims-data-eda) |
| **Knowledge graph** | `llm-mailroom-graph` | Derived knowledge-graph site of `llm-mailroom` | [`Exios66/llm-mailroom-graph`](https://github.com/Exios66/llm-mailroom-graph) |
| **Corpus EDA + HF** | `mailroom-corpus-eda` | Corpus EDA (P0–P6) + centralized HuggingFace upload helpers | [`Exios66/Mailroom-Corpus-EDA`](https://github.com/Exios66/Mailroom-Corpus-EDA) |

</div>

> The corpus is published as [`Lucius-Morningstar/mailroom-dataset`](https://huggingface.co/datasets/Lucius-Morningstar/mailroom-dataset) (v9, 3,302 documents across 5 classes and 55 strata).

## Members

<div align="center">

| Member | Role | Focus | Affiliation |
| :--- | :--- | :--- | :--- |
| [**Exios66**](https://github.com/Exios66) — Jack J Burleson // LJM | Owner | Neuroscience & Machine Learning · platform architecture, pipeline & prompt engineering | UW-Madison · Las Vegas, NV |
| [**grantmooslin**](https://github.com/grantmooslin) | Owner | Constellation engineering & review | UW-Madison |
| [**jjburleson**](https://github.com/jjburleson) | Security Manager | Security Analyst & Moderator | UW-Madison |

</div>

The organization is small by design: a governed evaluation family where every specialty — data, prompts, UI, systems, docs, governance — has an accountable owner, and every change is claimed on the board before it is written.

## Quick links

<div align="center">

**[Digital-Mailroom](https://github.com/LLM-Mailroom-Services/Digital-Mailroom)** ·
**[Dispatch Board](https://digital-mailroom-theta.vercel.app)** ·
**[mailroom-issues](https://github.com/LLM-Mailroom-Services/mailroom-issues)** ·
**[eval-environment](https://eval-environment.vercel.app)** ·
**[mailroom-dataset (HF)](https://huggingface.co/datasets/Lucius-Morningstar/mailroom-dataset)**

</div>

---

<div align="center">

**[llm-mailroom](https://github.com/Exios66/llm-mailroom)** ·
**[llm-entity-extraction](https://github.com/Exios66/llm-entity-extraction)** ·
**[llm-dojo-scoring](https://github.com/Exios66/llm-dojo-scoring)** ·
**[The-Mailroom](https://github.com/Exios66/The-Mailroom)** ·
**[agent-mailroom](https://github.com/Exios66/agent-mailroom)**

<sub>Built by the governed evaluation family under <a href="https://github.com/LLM-Mailroom-Services">Mailroom Incorporated™</a> (Exios66 · grantmooslin) · 2026</sub>

</div>
