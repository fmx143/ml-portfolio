# CLAUDE.md — House rules for this project

This file tells any future Claude Code session (and reminds you) how this project is built,
so the style stays consistent.

## What this project is
A **beginner machine-learning portfolio**: four small, self-contained projects, each one
demonstrating a *different type* of machine learning. The owner knows basic Python but is new
to ML, and wants to genuinely understand the code — not receive a black box.

| # | Folder | ML type | Technique |
|---|--------|---------|-----------|
| 1 | `01_regression_house_prices/` | Supervised — Regression | Linear Regression |
| 2 | `02_classification_up_or_down/` | Supervised — Classification | Logistic Regression / Decision Tree / Random Forest |
| 3 | `03_clustering_assets/` | Unsupervised — Clustering | K-Means |
| 4 | `04_neural_net_digits/` | Neural network / images | MLPClassifier |

## Library policy
- **scikit-learn for everything**, including the neural net (`MLPClassifier`). Keep it to one
  consistent API so the learner focuses on concepts, not library juggling.
- `pandas`/`numpy` for data, `matplotlib`/`seaborn` for charts, `yfinance` for market data (#2, #3).
- Do **not** introduce PyTorch/TensorFlow unless the owner explicitly asks (it's a future stretch goal).

## How we work
- **Build and explain ONE project at a time, in order 1 → 4.** Do not jump ahead.
- Style is *explain-before-code*: I write fully-commented notebooks, then walk through them cell-by-cell.
- Each notebook follows the same **8-step template**: (1) the question, (2) load & peek at data,
  (3) visualize, (4) prepare / train-test split, (5) train, (6) evaluate, (7) interpret,
  (8) "🧪 Your turn" exercise.

## Coding conventions (readability over cleverness)
- **Descriptive variable names**, the kind a beginner would write — NOT cryptic ML shorthand.
  - Use `house_features` / `house_prices`, not `X` / `y`.
  - Use `training_features`, `test_features`, `training_labels`, `test_labels`, not `X_train` / `y_test`.
  - Other examples: `price_history`, `daily_returns`, `went_up_tomorrow`, `predicted_direction`,
    `flower_model`, `digit_model`, `asset_clusters`.
- When a variable maps to a standard ML name, add a one-line comment, e.g. `# books usually call this 'X'`,
  so the learner also recognizes the conventional form elsewhere.
- `snake_case` everywhere. Short, plain-English comments above each step. Define jargon the first time it appears.

## Tooling
- Python virtual environment lives at `ml-portfolio/.venv`.
- Dependencies are pinned in `requirements.txt`; install with `pip install -r requirements.txt`.
- Notebooks run in **JupyterLab** (`jupyter lab`).
- Projects #2 and #3 need internet to fetch prices; they cache a CSV into `data/` so they re-run offline.
