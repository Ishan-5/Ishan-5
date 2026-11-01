<div align="center">

# Devansh Kumar Pandey

**AI/ML engineer in the making — I build systems that retrieve, reason, and ship.**

Third-year Electronics Engineering student at HBTU Kanpur, working on LLM routing, RAG evaluation, and transformer-based NLP. I care about the unglamorous parts: benchmarks, guardrails, and getting models into production.

[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-6C47FF?style=for-the-badge&logo=vercel&logoColor=white)](https://portfolio-ai-ml-ten.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)
[![Email](https://img.shields.io/badge/Email-devansh.7711%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)

</div>

---

## What I'm working on

- **LLM routing** — deciding, per request, which model tier is good enough, so quality stays high and cost drops.
- **RAG evaluation** — measuring retrieval properly instead of eyeballing answers.
- **NLP for messy text** — Hinglish, code-mixed input, and low-resource sentiment.
- **Deployment** — FastAPI services, dashboards, SDKs, and enough tests to trust a release.

---

## Featured Projects

### RouteWise — Cost-Aware LLM Router
[![Repo](https://img.shields.io/badge/GitHub-llm--router-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/llm-router)
[![Live](https://img.shields.io/badge/Live_Demo-Vercel-000000?style=flat-square&logo=vercel)](https://llm-router-nine-eta.vercel.app/)
[![PyPI](https://img.shields.io/badge/PyPI-routewise-3775A9?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/project/routewise/)
[![npm](https://img.shields.io/badge/npm-routewise-CB3837?style=flat-square&logo=npm&logoColor=white)](https://www.npmjs.com/package/routewise)

A difficulty-aware router that sends each request to the cheapest model tier that can handle it — no routing rules to hand-write.

- Trains a **LightGBM ensemble on MiniLM embeddings** (chosen over Ridge, RidgeCV, and RandomForest) on **8,000+ Claude-verified labels**.
- Reaches **77.5% exact-tier accuracy**, **MAE 1.018**, and **Spearman 0.86** on held-out data with **~16.5 ms** local scoring.
- Routes across **3 cost tiers** for **~50% lower per-request cost** than always-frontier at a measured traffic mix.
- Ships three policies: a general model plus a support-tuned model (17,600 tickets) with **80% / 86% frontier-recall** cuts.
- Blind pairwise A/B (n=56): cheap tier matched or beat frontier **75%** of the time (95% CI 62–85%).
- Production hardening: prompt-injection and PII screening, 0.95-cosine semantic cache, budget caps, tier step-down failover, circuit breakers, and **329 automated tests**.
- Drop-in **`/v1/chat/completions`** endpoint, SSE streaming, live routing dashboard, Python SDK, npm CLI, and MCP server.

`Python` · `FastAPI` · `LightGBM` · `React` · `PostgreSQL` · `Docker` · `Prometheus` · `Groq` · `OpenRouter`

---

### RAG Pipeline Stress-Test Framework
[![Repo](https://img.shields.io/badge/GitHub-rag--stress--tester-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/rag-stress-tester)

Benchmarked **13 RAG configurations** across 4 chunking strategies, 3 embedding models, and 3 retrieval methods on 500 SQuAD v2.0 queries per config.

- Hybrid retrieval + cross-encoder reranking lifted **Recall@1 by 14.8 points** over dense-only (0.868 vs 0.720).
- Semantic chunking gave the best **Recall@5 (0.944)** and **MRR (0.910)** — at 7.4× the latency of the fastest config (18.5 ms, Recall@5 0.918).

`ChromaDB` · `sentence-transformers` · `BM25` · `Groq` · `Streamlit`

---

### Hinglish Sentiment Analyzer
[![Repo](https://img.shields.io/badge/GitHub-Hinglish--Sentiment--Analysis-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/Hinglish-Sentiment-Analysis)

Fine-tuned **MuRIL (110M params)** for 3-class sentiment on 3,190 Hinglish YouTube comments.

- **66% accuracy** and **0.65 macro-F1** — a **+21 point** gain over the 44.7% majority baseline.
- Used class-weighted loss to handle label imbalance; served predictions through FastAPI.

`PyTorch` · `Hugging Face` · `MuRIL` · `FastAPI` · `scikit-learn`

---

### Credit Card Fraud Detector
[![Repo](https://img.shields.io/badge/GitHub-credit--card--fraud--detector-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/credit-card-fraud-detector)

Fraud detection on **284K transactions**, with threshold tuning and a deployed REST API.

- **ROC-AUC 0.963** and **F1 0.89** after tuning the decision threshold for the imbalanced class.

`scikit-learn` · `Flask` · `Render`

---

### Mastercard Chatbot Rebuild
[![Repo](https://img.shields.io/badge/GitHub-Mastercard--Career--Chatbot--Improved--Demo-181717?style=flat-square&logo=github)](https://github.com/Ishan-5/Mastercard-Career-Chatbot-Improved-Demo)

Black-box tested a live career chatbot, documented **9 NLP failure modes**, then rebuilt it with a custom intent dataset.

- Reached **85.35% test accuracy** on the rebuilt classifier.

`scikit-learn` · `NLP` · `Streamlit`

---

## Stack

**Languages & Core**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**ML & Deep Learning**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-189FDD?style=flat-square&logo=xgboost&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-02569B?style=flat-square)

**RAG & Retrieval**
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6B35?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-4B5563?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)

**Backend & Deployment**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat-square&logo=render&logoColor=black)

**Data & Tooling**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)

---

## Currently exploring

```python
learning = ["agentic workflows", "LLM fine-tuning", "routing + evaluation at scale"]
open_to  = ["AI/ML internships", "research collaborations", "open-source contributions"]
```

---

<div align="center">

**Building something in retrieval, routing, or applied NLP? Let's talk.**

[![Email](https://img.shields.io/badge/devansh.7711%40gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:devansh.7711@gmail.com)
[![LinkedIn](https://img.shields.io/badge/Devansh_Kumar_Pandey-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/devansh584)

<sub>HBTU Kanpur · B.Tech Electronics Engineering · 2024–2028</sub>

</div>
