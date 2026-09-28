# RR Skillverse — Free Learning Handbook

## AI & Machine Learning: Advanced Engineering with Cybersecurity

A free, self-contained learning handbook that teaches production machine-learning engineering and applied AI security **together**, through one running case study — a fictional lending company, **RR Finance** — that every module builds on and then attacks.

This repository is a static [GitHub Pages](https://pages.github.com/) site (no build step, no backend) plus a set of matching, fully-runnable Jupyter reference notebooks. It is shared for learning purposes only — not a commercial product or paid service.

> **All 12 modules are live.** The capstone (Module 12) is a complete, public application — **[CAMEL Sentinel](https://github.com/raushan1107/ai-ml-cybersecurity-bank-risk-capstone)** — that you can run in one command.

---

## What makes this handbook different

Most ML courses teach a technique and stop at "it works." This one carries a **single system** from a first tabular model all the way to a deployed, containerised API — and then, in the security modules, turns around and attacks the exact thing it built. Every attack is run for real against the real artifact from an earlier module, and every result is reported **honestly**, including the attacks that under-perform and the defences that only half-work. Knowing *when* something fails is treated as the point, not an embarrassment to hide.

Two layers per module:

- **Handbook page** (`moduleN.html`) — theory-first. For every technique: what it is, why it exists (the specific problem it was invented to solve), what you'd use instead, the mathematics, and a concrete RR Finance example. Each concept has an **Overview** and a **Math & Algorithm** view you can toggle.
- **Reference notebook** (`reference-notebooks/moduleN.ipynb`) — the same material as real, executed code that produces real artifacts (models, metrics, threat models) the next module consumes.
- **Lab guide** (`labs.html`) — a simpler, self-contained, copy-paste-and-run version of each module for hands-on practice, with the real expected output shown for every step.

---

## The modules

| # | Module | What it covers | Status |
|---|--------|----------------|--------|
| 1 | **Data Science + Financial Data Analysis** | The trusted foundation: EDA, feature engineering, regression, classification, clustering, anomaly detection, and the first security control — data-poisoning defence. | ✅ Live |
| 2 | **Deep Neural Networks** | Perceptrons, ANNs, backprop, optimizers, CNNs — plus the first inference-time attack: adversarial examples (FGSM/PGD) and adversarial training as a defence. | ✅ Live |
| 3 | **NLP + Financial Text AI** | Text representations, embeddings, NER, sentiment analysis on financial text, prompt injection, and PII redaction. | ✅ Live |
| 4 | **Generative AI, LLMs & RLHF** | Transformers, fine-tuning (LoRA/QLoRA), alignment (SFT → RM → PPO/DPO), and LLM red-teaming. | ✅ Live |
| 5 | **RAG, LangChain & AI Agents** | Vector retrieval, agentic tool-use, LangGraph, and the agentic-AI threat surface (retrieval poisoning, tool-call hijacking). | ✅ Live |
| 6 | **Explainable & Responsible AI** | SHAP, LIME, counterfactuals, fairness auditing, and model governance — including the age-fairness question Module 1 flagged. | ✅ Live |
| 7 | **Federated & Privacy-Preserving ML** | Federated averaging, differential privacy, and Byzantine-robust aggregation defences. | ✅ Live |
| 8 | **Multimodal AI** | Speech, vision-language models, and document intelligence — building on Module 2's CNN foundations. | ✅ Live |
| 9 | **Graph Neural Networks** | Fraud-ring detection, knowledge graphs, GraphRAG, and GNN-based intrusion detection. | ✅ Live |
| 10 | **MLOps & On-Premises Deployment** | FastAPI serving, Docker/Kubernetes, and DevSecOps controls (Trivy, Vault, TLS/mTLS). | ✅ Live |
| 11 | **AI Cybersecurity** | STRIDE and MITRE ATLAS threat modelling, then real attacks on the deployed model — extraction, evasion, and membership inference — each paired with a measured defence. | ✅ Live |
| 12 | **Final Capstone** | Everything from Modules 1–11, applied to real FDIC bank data and wired into one integrated, explainable, secured, deployable product — the **CAMEL Sentinel** app. | ✅ Live |

---

## The RR Finance running case study

Everything connects through one fictional lending company. The thread, module by module:

- **Module 1** trains the baseline loan-default model (a `StandardScaler` + `LogisticRegression` pipeline) on a synthetic, financially interpretable dataset, and saves it as a real artifact.
- **Modules 2–9** add deep learning, language models, retrieval and agents, explainability and fairness, privacy-preserving training, multimodal document intelligence, and graph-based fraud detection — each with its own attack and defence.
- **Module 10** wraps Module 1's actual saved model in a real FastAPI service with request validation, a container, Kubernetes manifests, and a mutual-TLS boundary — the first time the model is reachable over a network.
- **Module 11** threat-models that deployment (STRIDE + MITRE ATLAS) and then attacks the exact deployed API — stealing the model, evading its decisions, and probing it for training-data membership — before hardening it with measured defences.
- **Module 12** is the capstone: it applies the same twelve-stage path to **real public FDIC bank-failure data** and integrates everything — model, explanations, fairness audit, guard-railed assistant, fraud-detecting GNN, an AI security lab, and one-command deployment — into a single defended product, **CAMEL Sentinel**.

Because each module reads the previous module's real artifacts, the notebooks are meant to be run **in order, in the same project folder**.

---

## The capstone: CAMEL Sentinel

Module 12 is realised as a standalone, public, MIT-licensed application — **CAMEL Sentinel** — that ties the whole course together on real data. It predicts a bank's failure risk from public FDIC data, explains *why* with SHAP / LIME / counterfactuals, audits itself for fairness, chats about a bank through a guard-railed assistant, catches fraud rings with a graph neural network, attacks itself in a live AI Security Lab, and ships as one Docker container.

- **Run it in one command:** `docker run -d --name camel -p 8501:8501 raushanranjan/camel-sentinel:latest`, then open <http://localhost:8501>.
- **Project:** <https://github.com/raushan1107/ai-ml-cybersecurity-bank-risk-capstone>
- **Docker image:** <https://hub.docker.com/r/raushanranjan/camel-sentinel>

The Module 12 handbook page (`module12.html`) is a guided tour of that system, showing where each of the earlier eleven modules lives inside it.

---

## Repository structure

```text
AI-Machine-Learning-Handbook/
├── index.html                 # the hub — links to every module handbook, lab, and notebook
├── labs.html                  # hands-on, copy-paste lab guides for all live modules
├── module1.html … module12.html   # the theory handbooks (Module 12 is the capstone tour)
├── data/
│   └── rr_finance_module1_dataset.csv   # synthetic dataset (education only)
└── reference-notebooks/
    └── module1.ipynb … module11.ipynb   # runnable notebooks that produce the artifacts
```

The site is intentionally static — no build process and no backend are required.

---

## Getting started

### Read the handbook

Open `index.html` in a browser (or use VS Code's Live Server extension) and follow the modules from the hub. Everything renders client-side.

### Run the labs and notebooks

The notebooks build real artifacts that later modules depend on, so run them in order in one working folder:

1. Install a recent Python (3.10+) with Jupyter: `pip install jupyterlab`.
2. Keep `data/` and `reference-notebooks/` in the same project folder.
3. Open `reference-notebooks/module1.ipynb` and run it top to bottom — it creates the `data/` (enriched) and `artifacts/` folders used by later modules.
4. Move on to `module2.ipynb`, `module3.ipynb`, and so on. Each notebook installs its own libraries in its first cell and states which earlier artifacts it needs.

For a lighter, guided path, `labs.html` gives a simpler self-contained version of each module with the exact expected output shown for every step.

> The generated `artifacts/` folder and any enriched data files are build outputs — they're recreated by running the notebooks and don't need to be committed.

---

## Publishing on GitHub Pages

1. Create (or use) a GitHub repository and upload `index.html`, `labs.html`, the `moduleN.html` pages, the `data/` folder, and `reference-notebooks/`.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the branch and folder that contain `index.html` (usually `main` / root), then save.
5. GitHub Pages will publish the site at your Pages URL; `index.html` acts as the handbook hub and links to every module.

---

## Teaching approach

Every topic follows the same honest, repeatable arc:

**Business problem → financial relevance → technique/algorithm → parameters → mathematics → what changes if the parameters change → Python → real result → security/enterprise interpretation.**

Security is not a bolt-on chapter at the end — it appears in *every* module, applied to the very system that module just built. Results (including negative ones) are reported as they actually came out.

All datasets are synthetic and for education only.

---

## About

Created by **Raushan Ranjan** as part of the RR Skillverse Free Learning Handbook. Shared for learning purposes only — not a commercial product or paid service.
