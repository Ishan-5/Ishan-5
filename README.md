<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=38&pause=1200&color=58A6FF&center=true&vCenter=true&width=760&lines=Devansh+Kumar+Pandey;AI%2FML+Engineer;LLM+Routing+%C2%B7+RAG+Evaluation;Ship+it%2C+then+measure+it" alt="Devansh Kumar Pandey" />

### I build the layer between *a model* and *the right model*.

Third-year ECE @ HBTU Kanpur. I work on **LLM routing**, **retrieval evaluation**, and **transformer NLP** — and on the unglamorous parts that make them production-grade: benchmarks, guardrails, failover, tests.

[![Portfolio](https://img.shields.io/badge/Portfolio-6C47FF?style=for-the-badge&logo=vercel&logoColor=white)](https://portfolio-ai-ml-ten.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ishan-5)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)

</div>

```console
$ whoami
devansh — third-year Electronics Engineering @ HBTU Kanpur

$ cat focus.txt
LLM routing · RAG evaluation · transformer NLP · production backends

$ ls ~/currently-building
routewise/   # difficulty-aware LLM router — live, on PyPI & npm
```

---

## ⚡ Featured Project

### RouteWise — Cost-Aware LLM Router

> **Route every query to the cheapest model that answers it well.**

Most teams pay frontier prices for every request. RouteWise scores each query's **difficulty** first, then sends it to the **cheapest tier that can handle it** — frontier quality where it matters, small-model prices everywhere else. Drop-in OpenAI-compatible, zero routing rules to hand-write.

[![Repo](https://img.shields.io/badge/Source-llm--router-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/llm-router)
[![Live](https://img.shields.io/badge/Live_Demo-000000?style=flat-square&logo=vercel)](https://llm-router-nine-eta.vercel.app/)
[![PyPI](https://img.shields.io/badge/PyPI-routewise-3775A9?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/project/routewise/)
[![npm](https://img.shields.io/badge/npm-routewise-CB3837?style=flat-square&logo=npm&logoColor=white)](https://www.npmjs.com/package/routewise)

```text
                  ┌───────────────────────────┐
     request ────▶│   difficulty head         │
                  │   LightGBM + MiniLM       │
                  └─────────────┬─────────────┘
                                │  score
            ┌───────────────────┼───────────────────┐
            ▼                   ▼                   ▼
      ┌───────────┐       ┌───────────┐       ┌────────────┐
      │  cheap    │       │    mid    │       │  frontier  │
      │  tier     │       │   tier    │       │    tier    │
      └───────────┘       └───────────┘       └────────────┘
```

<table>
  <tr>
    <td align="center"><h3>77.5%</h3><sub>exact-tier accuracy</sub></td>
    <td align="center"><h3>0.86</h3><sub>Spearman correlation</sub></td>
    <td align="center"><h3>1.018</h3><sub>MAE</sub></td>
    <td align="center"><h3>16.5 ms</h3><sub>local scoring</sub></td>
    <td align="center"><h3>~50%</h3><sub>lower cost vs frontier</sub></td>
  </tr>
</table>

**Under the hood**

- **The model** — a LightGBM ensemble on MiniLM embeddings, chosen over Ridge, RidgeCV, and RandomForest, trained on **8,000+ Claude-verified labels**.
- **The policies** — one general router, plus a support-tuned model (17,600 labeled tickets) exposed as two threshold cuts at **80% and 86% frontier recall**.
- **The proof** — a blind pairwise A/B (n=56 easy queries) where the cheap tier matched or beat frontier **75%** of the time (95% CI 62–85%). Along the way I found and fixed a judge bug that had been silently reporting 100% ties.
- **The guardrails** — prompt-injection and PII screening, a 0.95-cosine semantic cache, per-key budget caps, circuit breakers, round-robin key balancing, and tier step-down failover (frontier → mid/cheap across OpenRouter and Groq, Gemini as last resort).
- **The surface area** — a drop-in `/v1/chat/completions` endpoint, SSE token streaming, a live routing dashboard, a Python SDK on PyPI, a zero-dependency npm CLI, an MCP server, and thumbs up/down feedback persisted for retraining.
- **The boring stuff that matters** — **329 automated tests**, GitHub Actions CI, CodeQL, Prometheus metrics, and webhook alerts on cost, error, and latency thresholds.

<sub>`Python` · `FastAPI` · `LightGBM` · `React` · `PostgreSQL` · `Docker` · `Prometheus` · `Groq` · `OpenRouter`</sub>

---

## 🧪 More builds

| Project | What it does | Headline result |
|---|---|---|
| [**RAG Stress-Tester**](https://github.com/Ishan-5/rag-stress-tester) | 13 RAG configs × 4 chunking × 3 embedders × 3 retrievers, scored on 500 SQuAD v2.0 queries each | Hybrid + reranking lifted **Recall@1 +14.8 pts** (0.868 vs 0.720); best **Recall@5 0.944** |
| [**Hinglish Sentiment**](https://github.com/Ishan-5/Hinglish-Sentiment-Analysis) | Fine-tuned **MuRIL (110M)** for 3-class Hinglish sentiment on 3,190 YouTube comments | **66% accuracy**, 0.65 macro-F1 — **+21 pts** over majority baseline |
| [**Fraud Detector**](https://github.com/Ishan-5/credit-card-fraud-detector) | 284K transactions, threshold-tuned and shipped as a REST API | **ROC-AUC 0.963**, **F1 0.89** |
| [**Mastercard Rebuild**](https://github.com/Ishan-5/Mastercard-Career-Chatbot-Improved-Demo) | Black-box tested a live chatbot, documented 9 NLP failures, rebuilt the classifier | **85.35%** test accuracy |

---

## 🛠 Stack

| Area | Tools |
|---|---|
| **Core** | `Python` · `SQL` |
| **ML / DL** | `PyTorch` · `Hugging Face` · `scikit-learn` · `LightGBM` · `XGBoost` · `BERT` · `MuRIL` |
| **Retrieval** | `ChromaDB` · `BM25` · `hybrid search` · `cross-encoder reranking` · `semantic chunking` |
| **Backend** | `FastAPI` · `Flask` · `Streamlit` · `REST APIs` · `Docker` |
| **Infra / Data** | `PostgreSQL` · `MongoDB` · `GitHub Actions` · `CodeQL` · `Prometheus` · `Render` |

---

## 📈 Signal

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Ishan-5&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&theme=tokyonight" alt="GitHub stats" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ishan-5&layout=compact&langs_count=8&hide_border=true&theme=tokyonight" alt="Top languages" />

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Ishan-5&theme=tokyo-night&hide_border=true&area=true" alt="Contribution activity" />

</div>

---

## 🧭 How I work

```python
principles = [
    "Measure first — a number beats a hunch.",
    "The cheapest model that works is the right model.",
    "If it isn't tested, it isn't shipped.",
    "Evaluation is a product feature, not an afterthought.",
]
```

**Currently exploring:** agentic workflows · LLM fine-tuning · routing and eval at scale
**Open to:** AI/ML internships · research collaborations · open-source contributions

---

<div align="center">

### Got a hard retrieval, routing, or NLP problem?

[![Say hello](https://img.shields.io/badge/devansh.7711%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)
[![Connect](https://img.shields.io/badge/Let's_connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)

<sub>HBTU Kanpur · B.Tech Electronics Engineering · 2024–2028</sub>

</div>
