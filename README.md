<div align="center">

# Syed Hasan Abbas

### AI Engineer · Full-Stack Engineer

**I take AI products from an idea to something customers pay for.**
Model to interface, and the infrastructure holding it up.

### *A good agent can lie truthfully.*

When it is wrong, it can still show you exactly what it saw and why it concluded that.
I build agents that are fast, accurate, and accountable when they are none of the above.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/s-hasan-abbas)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-FFD21E?style=for-the-badge&logoColor=black)](https://huggingface.co/Syed-Hasan-8503)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:hasansyed8505@gmail.com)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/syed_hasan_03)

</div>

---

## The problems I get hired to solve

**"Our agent is right, eventually, and nobody will wait that long."**
Speed in an agent is not a faster model, it is refusing to do the same work twice. I make the expensive parts of a run reusable: identical questions collapse into one computation instead of one per user, a step that already fetched something is never allowed to fetch it again, and the queries an agent writes are made deterministic so the same request produces the same result rather than a fresh guess. Users get an answer while they still care about the question.

**"It gave us the wrong number and we cannot find out why."**
This is the failure that ends trust in an AI product, and it is an architecture problem, not a model problem. I build agents where the evidence outlives the answer: whatever a step concludes, the full data it actually saw is preserved alongside it rather than being summarised away. So when an answer is wrong, you can open it, see the real inputs, and say precisely where it went wrong. Every model call is traced end to end. Nothing has to be reproduced from memory.

**"Our team is drowning in a manual process."**
Contract review, ad account management, campaign reporting, recruitment screening. I find the judgement-heavy work that people should keep, automate the mechanical work around it, and leave a human in the loop at the point where it actually matters.

**"We need this built, and there is nobody to hand the other half to."**
I ship the API, the interface, the data pipeline, and the deployment. Small teams get a working product instead of a component that needs three more hires to become one.

Separately, in published research: model compression and alignment work, including a **91.25% reduction in KV-cache memory** on an 8B model that *improved* long-context benchmark scores.

---

## What I am building now

**Lead engineer on the AI platform at [Plug](https://github.com/pluuug-net)**, a startup automating Meta advertising for growing brands.

Advertisers waste budget because nobody can watch every campaign every hour. Plug does. I built the system that ingests a brand's ad, analytics, and creative data, monitors performance continuously, and surfaces what changed and what to do about it in plain language, so a marketer without an analyst can act on their own numbers.

What that meant in practice:

- An **orchestration layer** running eleven independent background workers with resilient scheduling, so one slow integration never stalls the rest of the platform.
- A **conversational analytics agent** that turns a plain-English question into a warehouse query and answers over live campaign data, replacing dashboard archaeology.
- A **caching layer** that took multi-second page loads off the critical path. Concurrent requests for the same view collapse into a single computation, results stay servable while they refresh in the background, and any user action that changes the data invalidates it immediately. Fast and stale is a bug; this is fast and correct.
- **Answers you can audit.** Tool results are preserved in full rather than being retyped and truncated by each model that handles them. The agent works from a bounded view, the complete evidence travels to the user, and a wrong answer can always be traced back to the exact rows that produced it.
- A **creative intelligence pipeline** that reads the actual images and video in an ad account and connects creative choices to performance.
- A **tested codebase**, not a prototype: over 200 test files across the services, tracing on every model call, and monitoring that surfaces failures before customers report them.

---

## Selected work

**Legal contract review platform.** Lawyers reviewing agreements clause by clause. The hard part was not summarisation, it was making sure a retrieved clause arrived whole, because half an obligation reads as a different obligation entirely. Built the document pipeline, the clause-level risk scoring, and the review interface. → [the technique, open-sourced](https://github.com/Hasan-Syed25/LLM-Based-Document-Chunking)

**Voice and chat agent platform for service businesses.** Missed calls are lost revenue for contractors. Built a configurable agent that answers, qualifies, and books appointments over real-time voice or chat, deployed for paying customers across multiple verticals from one codebase.

**Marketing research and proposal platform.** Trend ingestion through to a finished client-ready proposal, built with a team as a monorepo.

**Model research, published openly.** 15+ models on [Hugging Face](https://huggingface.co/Syed-Hasan-8503) reproducing frontier techniques end to end, with evaluations rather than claims: [91.25% KV-cache compression](https://huggingface.co/Syed-Hasan-8503/PaluLlama-3-8B-Instruct) with benchmark gains, [76.1% reward accuracy](https://huggingface.co/Syed-Hasan-8503/Llama-3-8b-instruct-SimPO) on preference alignment over a dataset I built myself, and [82.29% on TextVQA](https://huggingface.co/Syed-Hasan-8503/Idefics2-8B-SFT) for a vision-language model.

---

## Open source

| | |
|:--|:--|
| **[MCP-Server-AlphaVantage](https://github.com/Hasan-Syed25/MCP-Server-AlphaVantage)** ⭐ 7 | Gives any assistant real market analysis tools. Independently security-audited by MseeP.ai. |
| **[RepoMind](https://github.com/Hasan-Syed25/RepoMind)** | Ask a codebase questions. Reviews its own answer and retries rather than guessing. |
| **[HF2Reasoning](https://github.com/Hasan-Syed25/HF2Reasoning)** ⭐ 2 | Turns any public dataset into a reasoning dataset, so small teams can build training data without a labelling budget. |
| **[iRoPE Implementation](https://github.com/Hasan-Syed25/iRope_Implementation)** | Long-context attention rebuilt from a paper description, with an honest account of the limits. |
| **[SafeTensors Converter](https://github.com/Hasan-Syed25/PyTorch-SafeTensors-Converter)** | Converts model checkpoints out of a format that executes code on load. Verifies every tensor. Also a [hosted app](https://huggingface.co/spaces/Syed-Hasan-8503/Model_Converter_BIN-SafeTensors). |
| **[AI Recruitment Synapse](https://github.com/Hasan-Syed25/AI_Recruitment_Synapse)** | Matches candidates to roles and explains why, instead of returning an unexplained score. |
| **[SynGen](https://github.com/Hasan-Syed25/SynGen)** | Builds legal question-answer datasets for a jurisdiction that has almost none. |

---

## Stack

<div align="center">

[![Languages](https://skillicons.dev/icons?i=py,ts,js,java,pytorch&theme=dark)](https://skillicons.dev)

[![Backend](https://skillicons.dev/icons?i=fastapi,nestjs,nodejs,graphql,redis&theme=dark)](https://skillicons.dev)

[![Frontend](https://skillicons.dev/icons?i=nextjs,react,tailwind,vercel&theme=dark)](https://skillicons.dev)

[![Data](https://skillicons.dev/icons?i=postgres,mongodb,supabase,sqlite&theme=dark)](https://skillicons.dev)

[![Infrastructure](https://skillicons.dev/icons?i=docker,kubernetes,aws,gcp,azure,githubactions&theme=dark)](https://skillicons.dev)

</div>

Alongside these: agent orchestration and evaluation frameworks, vector and graph databases, hybrid retrieval, distributed task queues, LLM observability tooling, and load testing.

---

## Background

**Lead AI Engineer**, Plug · advertising automation

**Founding AI Engineer**, 108-AI

**Machine Learning Engineer**, GenerexAI

**B.E. Software Engineering** · National University of Sciences and Technology, Islamabad · GPA 3.81

---

<div align="center">

Most of my work lives in private repositories, so the graph here is quiet.
This page is the public trace of it.

**Open to remote AI engineering and AI-first full-stack roles.**

[hasansyed8505@gmail.com](mailto:hasansyed8505@gmail.com)

</div>
