# RR Skillverse — Free Learning Handbook — Module 1

## Secure Financial ML Engineering

This folder is a self-contained GitHub Pages site for Module 1 of the RR Skillverse Free Learning Handbook:

**AI & Machine Learning: Advanced Engineering with Cybersecurity**

### Files

- `module1.html` — complete Module 1 handbook/site
- `data/rr_finance_module1_dataset.csv` — synthetic, financially interpretable dataset

### Run locally

Open `index.html` in a browser, or use VS Code Live Server.

### GitHub Pages

1. Create a GitHub repository (or use the existing course repository).
2. Upload `index.html` and the `data` folder.
3. Enable GitHub Pages from the repository's Pages settings.
4. A future root `index.html` can act as the handbook hub and link to `module1.html`, `module2.html`, and later modules.
4. Select the branch/folder containing `index.html`.

The site is intentionally static: no build process and no backend are required.

### Teaching approach

Every topic uses:
Business problem → financial relevance → technique/algorithm → parameters → mathematics → what changes if parameters change → Python → result → security/enterprise interpretation.

The dataset is synthetic and for education only.


## Planned multi-module structure

```text
rr-skillverse-handbook/
├── index.html
├── module1.html
├── module2.html
├── module3.html
├── ...
├── module12.html
├── assets/
└── data/
```

The root `index.html` will eventually become the module hub. Each module page will retain the same learning UX and visual language while adding the next stage of the running financial AI system.
