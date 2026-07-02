<h1 align="center">ML Starter Portfolio 🧠</h1>

<div align="center">
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.10+" />
  <img src="https://img.shields.io/badge/scikit--learn-ML-f7931e?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/pandas-data-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="pandas" />
  <img src="https://img.shields.io/badge/JupyterLab-notebooks-f37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="JupyterLab" />
</div>

<div align="center">
  <br />
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-GPLv3-lightgrey.svg" alt="License: GPLv3" />
  </a>
  <img src="https://img.shields.io/badge/level-beginner%20friendly-success.svg" alt="Beginner friendly" />
  <br />
  <br />
  <i>A beginner-friendly machine-learning portfolio.</i>
  <br />
  <i>Small, self-contained Jupyter notebooks — code, explanations and charts in one place.</i>
  <br />
  <i>Each project demonstrates a different kind of machine learning.</i>
  <br />
</div>

<hr />

### In plain terms — what is this?

**Machine learning** is teaching a computer to spot patterns from examples instead of
hand-writing rules. This portfolio walks through it one small project at a time: each is a
single Jupyter notebook you read top-to-bottom, with the code, plain-English explanations
and the charts all together. The style is **explain-before-code** — you should understand
what every line does, not receive a black box.

**Who is it for?** Someone who knows basic Python but is **new to ML** and wants to genuinely
learn the concepts (regression, classification, and — planned — clustering and neural nets).

> 📚 **Learning exercise, not a product.** Project #2 predicts market direction as a *teaching*
> example, **not** trading advice. Real markets are close to random — the notebook explains why
> an impressive accuracy here is usually a red flag, not a money-printer.

**📚 Reference docs**
- [`CLAUDE.md`](CLAUDE.md) — house rules: library policy, the 8-step notebook template, naming conventions.

---

## 🧭 Table of contents

1. [✨ The projects](#-the-projects)
2. [🔁 How each notebook works](#-how-each-notebook-works)
3. [📋 Prerequisites](#-prerequisites)
4. [🚀 Getting started](#-getting-started)
5. [🧩 Pick the right Python kernel](#-pick-the-right-python-kernel)
6. [🎓 What you'll learn](#-what-youll-learn)
7. [🏗️ Project layout](#-project-layout)
8. [📜 License](#-license)

---

## ✨ The projects

**Four projects, four different kinds of machine learning.** Two are built today; two are planned.

| # | Project | What it does | Kind of ML | Status |
|---|---------|--------------|-----------|--------|
| 1 | [House prices](01_regression_house_prices/) | Predicts a house's price from its features | **Regression** (predict a number) | ✅ Available |
| 2 | [Up or down?](02_classification_up_or_down/) | Predicts whether an asset closes higher tomorrow | **Classification** (predict a category) | ✅ Available |
| 3 | Asset groups | Groups assets that behave alike | **Clustering** (find hidden groups) | 🚧 Planned |
| 4 | Digit recognizer | Reads handwritten digits (0–9) | **Neural network** (images) | 🚧 Planned |

> 🛠️ **Library policy:** scikit-learn for *everything* (including the planned neural net via
> `MLPClassifier`), so you focus on concepts rather than juggling APIs. `pandas`/`numpy` for
> data, `matplotlib`/`seaborn` for charts, `yfinance` for market data. No PyTorch/TensorFlow.

---

## 🔁 How each notebook works

Every notebook follows the same **8-step template**, so once you've read one you know the shape of them all:

```
1. the question   →  2. load & peek   →  3. visualize   →  4. prepare / split
      ↓
5. train model    →  6. evaluate      →  7. interpret   →  8. 🧪 your-turn exercise
```

Open the projects **in order (1 → …)** — each one builds on ideas from the last.

---

## 📋 Prerequisites

- 🐍 **Python 3.10+** (this project was built on 3.12).
- 📦 The libraries in [`requirements.txt`](requirements.txt): `numpy`, `pandas`, `matplotlib`,
  `seaborn`, `scikit-learn`, `yfinance`, `jupyterlab`.
- 🌐 Internet the first time you run project #2 (it fetches prices via `yfinance`, then caches a
  CSV into `data/` so it re-runs offline).

---

## 🚀 Getting started

```bash
# 1. Go into the project
cd ml-portfolio

# 2. Create an isolated environment (keeps these libraries separate from the rest of your system)
python3 -m venv .venv

# 3. Turn the environment on
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 4. Install the libraries
pip install -r requirements.txt

# 5. Launch the notebooks in your browser
jupyter lab
```

Then open the projects **in order** — each one builds on ideas from the last.

---

## 🧩 Pick the right Python kernel

*(Read this if you get an `ipykernel` / "package not found" error.)*

If your editor shows *"Running cells with 'Python 3.12.3' requires the ipykernel package"*, it's
trying to use your **system Python** instead of this project's `.venv` (where all the libraries
live). **Don't** install anything into the system Python — just point the notebook at the venv.

The venv's interpreter path is:
```
ml-portfolio/.venv/bin/python
```

**In VS Code**
1. Open the notebook.
2. Click the kernel/interpreter button at the **top-right** of the notebook.
3. Choose **Python Environments…** → pick **`.venv`** (`ml-portfolio/.venv/bin/python`).
   If it isn't listed, choose **"Enter interpreter path…"** and paste the path above.

**In JupyterLab**
- Easiest: launch it *from* the activated venv (`source .venv/bin/activate` then `jupyter lab`).
- Or, in an open notebook, use the kernel menu (top-right) and select **"Python (ml-portfolio)"**.

> One-time setup (already done, but here's how to recreate the named kernel if needed):
> ```bash
> ./.venv/bin/python -m ipykernel install --user --name ml-portfolio --display-name "Python (ml-portfolio)"
> ```

**Why?** A virtual environment (`.venv`) is a private copy of Python holding only this project's
libraries. The editor often defaults to the system Python, which doesn't have them — pointing it
at `.venv` fixes every "package not found" message at once.

---

## 🎓 What you'll learn

1. **Regression** — features vs. target, the all-important train/test split, fitting a model, reading R².
2. **Classification** — predicting categories, comparing several models, the confusion matrix, overfitting.
3. **Clustering** *(planned)* — learning *without* labels, building features (returns & volatility), choosing how many groups.
4. **Neural networks** *(planned)* — treating images as numbers, training a small neural net, multi-class accuracy.

---

## 🏗️ Project layout

Flat, one folder per project — each notebook is standalone and runs top-to-bottom.

```
ml-portfolio/
  01_regression_house_prices/   ✅ house_prices.ipynb — regression on housing data
  02_classification_up_or_down/ ✅ up_or_down.ipynb — next-day SPY direction
  03_clustering_assets/         🚧 planned — K-Means on asset returns/volatility
  04_neural_net_digits/         🚧 planned — MLPClassifier on digit images
  data/                         cached market data (e.g. SPY_prices.csv) for offline re-runs
  requirements.txt              pinned-by-name dependencies
  CLAUDE.md                     house rules / conventions
  LICENSE                       GPLv3
```

---

## 📜 License

[GNU GPL v3](LICENSE).
