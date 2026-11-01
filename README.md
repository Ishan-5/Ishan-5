<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=36&pause=1200&color=58A6FF&center=true&vCenter=true&width=780&lines=Devansh+Kumar+Pandey;AI%2FML+Engineer;Models+%C2%B7+Evaluation+%C2%B7+Deployment;I+build+AI+that+leaves+the+notebook" alt="Devansh Kumar Pandey" />

### I build AI systems that hold up outside the notebook.

Third-year Electronics Engineering student at **HBTU Kanpur**, working across the AI/ML stack — fine-tuning transformers, benchmarking retrieval, training classical models, and shipping the backend layer that makes them usable. I optimize for **measured results**, not demos.

[![Portfolio](https://img.shields.io/badge/Portfolio-6C47FF?style=for-the-badge&logo=vercel&logoColor=white)](https://portfolio-ai-ml-ten.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ishan-5)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)

</div>



---

## 🎯 What I bring

| Area | Evidence |
|---|---|
| **LLM systems** | Difficulty-based routing across 3 cost tiers, tiered failover, semantic caching, budget controls, and a 329-test suite around it all |
| **Applied ML** | Model selection from Ridge to LightGBM; fraud detection at **ROC-AUC 0.963**; threshold tuning for imbalanced data |
| **NLP & transformers** | Fine-tuned **MuRIL (110M)** on Hinglish text for **+21 pts** over baseline; intent classification and code-mixed preprocessing |
| **Retrieval & evaluation** | Benchmarked **13 RAG configurations**; best **Recall@5 0.944** and **MRR 0.910**; Recall@1 **+14.8 pts** from hybrid + reranking |
| **Production engineering** | FastAPI services, Docker, Postgres, SSE streaming, GitHub Actions, CodeQL, Prometheus, and SDK/CLI surfaces |

---

## ⚡ Featured build

### RouteWise — Cost-Aware LLM Router

> **Route every query to the cheapest model that answers it well.**

Most teams pay frontier prices for every request. RouteWise scores a query's **difficulty** first, then sends it to the **cheapest tier that can handle it** — frontier quality where it matters, small-model prices everywhere else. Drop-in OpenAI-compatible, with no routing rules to hand-write.

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
    <td align="center"><h3>~50%</h3><sub>cheaper than frontier</sub></td>
  </tr>
</table>

**How it was built**

- **Model** — a LightGBM ensemble on MiniLM embeddings, picked over Ridge, RidgeCV, and RandomForest, trained on **8,000+ Claude-verified labels**.
- **Policies** — a general router plus a support-tuned model (17,600 tickets) exposed as two threshold cuts at **80% and 86% frontier recall**.
- **Validation** — a blind pairwise A/B (n=56) where the cheap tier matched or beat frontier **75%** of the time (95% CI 62–85%). I also found and fixed a judge bug that had been silently reporting 100% ties.
- **Reliability** — prompt-injection and PII screening, a 0.95-cosine semantic cache, circuit breakers, key balancing, and tier step-down failover across OpenRouter and Groq.
- **Surface area** — drop-in `/v1/chat/completions`, SSE streaming, live routing dashboard, Python SDK, npm CLI, MCP server, and persisted user feedback for retraining.
- **Operations** — **329 automated tests**, CI, CodeQL, Prometheus metrics, and webhook alerts on cost, error, and latency.

<sub>`Python` · `FastAPI` · `LightGBM` · `React` · `PostgreSQL` · `Docker` · `Prometheus`</sub>

---

## 🧪 Selected work

| Project | What it does | Headline result |
|---|---|---|
| [**RAG Stress-Tester**](https://github.com/Ishan-5/rag-stress-tester) | 13 RAG configs × 4 chunking strategies × 3 embedders × 3 retrievers, scored on 500 SQuAD v2.0 queries each | **Recall@1 +14.8 pts**; best **Recall@5 0.944** |
| [**Hinglish Sentiment**](https://github.com/Ishan-5/Hinglish-Sentiment-Analysis) | Fine-tuned MuRIL (110M) for 3-class sentiment on 3,190 code-mixed YouTube comments | **66% accuracy** — **+21 pts** over baseline |
| [**Fraud Detector**](https://github.com/Ishan-5/credit-card-fraud-detector) | 284K transactions, threshold-tuned and deployed as a REST API | **ROC-AUC 0.963**, **F1 0.89** |
| [**Mastercard Rebuild**](https://github.com/Ishan-5/Mastercard-Career-Chatbot-Improved-Demo) | Black-box tested a live chatbot, found 9 NLP failures, rebuilt the classifier on a custom dataset | **85.35%** test accuracy |

---

## 🛠 Toolbox

**Languages**  
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**ML & Deep Learning**  
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-02569B?style=flat-square)
![XGBoost](https://img.shields.io/badge/XGBoost-189FDD?style=flat-square&logo=xgboost&logoColor=white)

**LLM & Retrieval**  
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-4B5563?style=flat-square)
![sentence-transformers](https://img.shields.io/badge/sentence--transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

**Backend & Deployment**  
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=black)

**Data & Ops**  
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)

---

## 🧠 How I work

1. **Measure before modeling.** Every project starts with a baseline and a metric I can defend.
2. **Pick the simplest model that wins.** LightGBM beat fancier options because the benchmark said so — not because it was fashionable.
3. **Evaluate like a user.** Blind pairwise A/B, not just offline scores.
4. **Ship the boring parts.** Tests, CI, alerts, and failover are part of the system, not cleanup.

> *The interesting part of ML isn't the model. It's everything around it — the baseline you beat, the eval you trust, and the request that doesn't fall over at 3 a.m.*

**Right now:** going deeper on agentic workflows, LLM fine-tuning, and evaluation harnesses.

---

<div align="center">

### Hiring for an AI/ML role — or have a problem worth modeling?

I'm open to **internships**, **research collaborations**, and **open-source work** in LLMs, applied ML, and NLP.

[![Email](https://img.shields.io/badge/devansh.7711%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)
[![LinkedIn](https://img.shields.io/badge/Connect_with_me-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)

<sub>HBTU Kanpur · B.Tech Electronics Engineering · 2024–2028</sub>

</div>
