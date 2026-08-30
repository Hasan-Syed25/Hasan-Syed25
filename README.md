<div align="center">

# Syed Hasan Abbas

**AI Engineer / Full-Stack Engineer** · Agentic systems, retrieval, and the infrastructure around them

I build the whole path from model to product: LangGraph agent orchestration, hybrid retrieval over messy real-world documents, the FastAPI and NestJS services behind them, the Next.js frontends on top, and the Kubernetes and Celery plumbing that keeps it running.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/s-hasan-abbas)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FFD21E?style=for-the-badge&logoColor=black)](https://huggingface.co/Syed-Hasan-8503)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:hasansyed8505@gmail.com)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=x&logoColor=white)](https://x.com/syed_hasan_03)

</div>

---

## What I actually work on

**Agentic systems.** LangGraph state machines with parallel fan-out via `asyncio.gather`, sub-workflow composition, and human-in-the-loop checkpoints that survive a process restart. Plan-and-execute agents, MCP servers exposing internal data as tools, and MCP clients consuming them.

**Retrieval that holds up on real documents.** Dense plus sparse hybrid search with reciprocal rank fusion (Qdrant `Prefetch` and `FusionQuery`), BM25 and FastEmbed sparse vectors, cross-encoder reranking, GraphRAG over Neo4j, and clause-aware chunking for legal contracts where splitting a clause mid-obligation produces a confidently wrong answer.

**Model work, in the open.** 15+ models published on Hugging Face covering preference optimization, parameter-efficient fine-tuning, distillation, KV-cache compression, model merging, and linear-attention uptraining, each with the training notebook that produced it.

**The unglamorous half.** Multi-tenant database-per-tenant architecture, Celery Beat with RedBeat for distributed scheduling, Langfuse tracing on every LLM call, k6 load testing with `constant-arrival-rate` executors, NGINX ingress on Kubernetes, and CI that runs before anything ships.

---

## Open source

| Project | What it is |
|:--|:--|
| **[MCP-Server-AlphaVantage](https://github.com/Hasan-Syed25/MCP-Server-AlphaVantage)** | An MCP server on the official Python SDK exposing real market analysis as LLM tools: moving averages, RSI, Golden and Death Cross detection. Carries a third-party MseeP.ai security audit badge. |
| **[RepoMind](https://github.com/Hasan-Syed25/RepoMind)** | Conversational RAG over a repository's own codebase. Dense and sparse FastEmbed vectors fused in Qdrant, plus a self-correction loop where a structured `CodeReviewResult` check routes the agent back for a retry instead of returning an unverified answer. |
| **[iRoPE Implementation](https://github.com/Hasan-Syed25/iRope_Implementation)** | Retrofits a pretrained LLaMA's attention to interleave local RoPE attention with global temperature-scaled non-RoPE attention. Full weight-transfer logic, five configurable scaling functions, and a README honest about what a retrofit cannot match. |
| **[HF2Reasoning](https://github.com/Hasan-Syed25/HF2Reasoning)** | Turns any Hugging Face dataset into a chain-of-thought dataset using the BARE technique: a base model generates diverse rough output, an instruct model refines it. Runs against Together API or self-hosted sglang. |
| **[LLM-Based Document Chunking](https://github.com/Hasan-Syed25/LLM-Based-Document-Chunking)** | Clause-aware chunking for legal RAG. GPT-4o finds boundaries through Pydantic-constrained structured output and regex does the cutting, so extracted text stays byte-identical to the source. |
| **[AI Recruitment Synapse](https://github.com/Hasan-Syed25/AI_Recruitment_Synapse)** | Resume-to-role matching over hybrid retrieval, Azure OpenAI embeddings alongside `rank_bm25` sparse search, with LLM-generated justifications for every match. |
| **[SynGen](https://github.com/Hasan-Syed25/SynGen)** | Generates legal QA pairs from a Pakistani law corpus against a local vLLM server running Llama-3.3-70B-Instruct-AWQ. |
| **[PyTorch to SafeTensors Converter](https://github.com/Hasan-Syed25/PyTorch-SafeTensors-Converter)** | Sharded checkpoint conversion with tied-weight detection and element-wise round-trip verification on every tensor. Also live as a [Hugging Face Space](https://huggingface.co/spaces/Syed-Hasan-8503/Model_Converter_BIN-SafeTensors). |
| **[CLIAgentX](https://github.com/Hasan-Syed25/CLIAgentX)** | A terminal AI agent backed by Azure OpenAI or local vLLM, with search grounding. |

### Production work, under NDA

The systems I spend most of my time on are in private repositories. In shape, they look like this:

- A **legal contract review platform** across three services: a document pipeline doing layout-aware partitioning with automatic OCR fallback, a clause-level risk scoring engine over hybrid Qdrant retrieval, and the review interface on top.
- A **multi-vertical conversational agent platform**, voice and chat, with a real-time stack over LiveKit, Deepgram, ElevenLabs and Twilio, Neo4j-backed retrieval, and per-client configuration. Deployed for paying customers.
- An **advertising analytics agent** routing between NL-to-SQL over BigQuery and a GraphRAG path, with Celery Beat scheduling ingestion and Langfuse tracing every model call.
- A **marketing research and proposal platform** built as a Turborepo monorepo with a team.

Happy to walk through architecture and tradeoffs on any of these in a conversation.

---

## Published models

Numbers below come from the model cards and evaluation runs, not estimates.

| Model | Technique | Result |
|:--|:--|:--|
| [`PaluLlama-3-8B-Instruct`](https://huggingface.co/Syed-Hasan-8503/PaluLlama-3-8B-Instruct) | Palu low-rank KV-cache compression | **91.25%** KV-cache memory reduction |
| [`Llama-3-8b-instruct-SimPO`](https://huggingface.co/Syed-Hasan-8503/Llama-3-8b-instruct-SimPO) | SimPO preference optimization | **76.1%** reward accuracy |
| [`Idefics2-8B-SFT`](https://huggingface.co/Syed-Hasan-8503/Idefics2-8B-SFT) | VLM supervised fine-tuning | **82.29%** Levenshtein on TextVQA |
| [`phi-2-ORPO`](https://huggingface.co/Syed-Hasan-8503/phi-2-ORPO) | ORPO, no separate reward model | Reference-free alignment in a single stage |
| [`Gemma-2-2b-it-distilled`](https://huggingface.co/Syed-Hasan-8503/Gemma-2-2b-it-distilled) | Knowledge distillation, 9B teacher to 2B student | Served on hardware the teacher cannot fit |
| [`Llama-3-openhermes-reft`](https://huggingface.co/Syed-Hasan-8503/Llama-3-openhermes-reft) | ReFT, interventions on frozen representations | Adaptation without touching weights |
| [`Versatile-7B`](https://huggingface.co/Syed-Hasan-8503/Versatile-7B) · [`Exodius-70B`](https://huggingface.co/Syed-Hasan-8503/Exodius-70B) | mergekit, DARE-TIES and SLERP | Capability combination with zero gradient steps |
| [`Linear_Tiny_87M`](https://huggingface.co/Syed-Hasan-8503/Linear_Tiny_87M) | SUPRA linear-attention uptraining | Softmax attention converted to linear recurrence |

Also: NOLA, DoRA, QLoRA with custom classification heads, BAdam, CPO-SimPO, PoSE long-context extension, and QServe W4A8KV4 quantization.

---

## Stack

**Languages** Python · TypeScript · JavaScript · Java · SQL · Cypher

**AI & ML** LangGraph · LangChain · LangChainJS · MCP · PyTorch · Transformers · PEFT · TRL · mergekit · Instructor · Pydantic structured output · Langfuse · LangSmith

**Retrieval** Qdrant · Neo4j · MongoDB Atlas Vector Search · BM25 / `rank_bm25` · FastEmbed · cross-encoder reranking · RRF

**Backend** FastAPI · NestJS + Fastify · Express · Apollo GraphQL · Celery / Celery Beat / RedBeat / Flower · BullMQ · Redis

**Frontend** Next.js App Router · React · Vite · Apollo Client · GraphQL Codegen · graphql-ws · Tiptap / ProseMirror · shadcn/ui · Tailwind

**Data** BigQuery · PostgreSQL · Supabase · MongoDB · SQLAlchemy + Alembic · Drizzle

**Infra** Docker · Kubernetes + Skaffold + NGINX Ingress · AWS (EC2, ECS Fargate, ECR, CloudWatch) · GCP · Azure OpenAI · Vercel · GitHub Actions

**Testing & observability** pytest · vitest · Mocha / Chai / Sinon · Postman / Newman · k6 · Prometheus · structlog · Winston

---

## Background

**Founding AI Engineer**, 108-AI · Aug 2024 to present

**Machine Learning Engineer**, GenerexAI · Oct 2021 to Jul 2023

**B.E. Software Engineering**, National University of Sciences and Technology, Islamabad · GPA 3.81

Most of my production work lives in private company repositories, so the commit graph here is quiet. This profile is the public trace: shipped models with reproducible evaluations, the notebooks that produced them, and the projects I can share.

Open to remote AI engineering and AI-first full-stack roles. Reach me at [hasansyed8505@gmail.com](mailto:hasansyed8505@gmail.com).
