# 🧠 ML Starter Portfolio

A beginner-friendly machine-learning portfolio. **Four small projects, four different kinds of
machine learning** — each one is a Jupyter notebook with the code, the explanations, and the charts
all in one place.

| # | Project | What it does | Kind of ML |
|---|---------|--------------|-----------|
| 1 | [House prices](01_regression_house_prices/) | Predicts a house's price from its features | **Regression** (predict a number) |
| 2 | [Up or down?](02_classification_up_or_down/) | Predicts whether an asset closes higher tomorrow | **Classification** (predict a category) |
| 3 | [Asset groups](03_clustering_assets/) | Groups assets that behave alike | **Clustering** (find hidden groups) |
| 4 | [Digit recognizer](04_neural_net_digits/) | Reads handwritten digits (0–9) | **Neural network** (images) |

> ⚠️ Project #2 is a *learning exercise*, not trading advice. Real markets are close to random —
> the notebook explains why an impressive accuracy here is usually a red flag, not a money-printer.

## Getting started

You need **Python 3.10+** (this project was built on 3.12).

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

Then open the projects **in order (1 → 4)** — each one builds on ideas from the last.

## ⚠️ Pick the right Python kernel (read this if you get a `ipykernel`/`package not found` error)

If your editor shows something like *"Running cells with 'Python 3.12.3' requires the ipykernel
package"*, it means it's trying to use your **system Python** instead of this project's `.venv`
(which is where all our libraries live). **Don't** install anything into the system Python — just
point the notebook at the venv.

The venv's interpreter path is:
```
ml-portfolio/.venv/bin/python
```

**In VS Code**
1. Open the notebook.
2. Click the kernel/interpreter button at the **top-right** of the notebook.
3. Choose **Python Environments…** → pick **`.venv`** (shown as `ml-portfolio/.venv/bin/python`).
   If it isn't listed, choose **"Enter interpreter path…"** and paste the path above.

**In JupyterLab**
- Easiest: launch it *from* the activated venv (`source .venv/bin/activate` then `jupyter lab`).
- Or, in an open notebook, use the kernel menu (top-right) and select **"Python (ml-portfolio)"**.

> One-time setup (already done, but here's how to recreate the named kernel if needed):
> ```bash
> ./.venv/bin/python -m ipykernel install --user --name ml-portfolio --display-name "Python (ml-portfolio)"
> ```

**Why?** A virtual environment (`.venv`) is a private copy of Python holding only the libraries this
project needs. The editor often defaults to the system Python, which doesn't have them — pointing it
at `.venv` fixes every "package not found" message at once.

## What you'll learn (in order)
1. **Regression** — features vs. target, the all-important train/test split, fitting a model, reading R².
2. **Classification** — predicting categories, comparing several models, the confusion matrix, overfitting.
3. **Clustering** — learning *without* labels, building features (returns & volatility), choosing how many groups.
4. **Neural networks** — treating images as numbers, training a small neural net, multi-class accuracy.

## Built with
`scikit-learn` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `yfinance` · `jupyterlab`
