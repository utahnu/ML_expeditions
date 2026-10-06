# Machine Learning Expeditions

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![scikit--learn](https://img.shields.io/badge/scikit--learn-Modeling-F7931E?logo=scikit-learn&logoColor=white)

A practical portfolio of machine-learning experiments implemented in Python and Jupyter. This repository explores model selection, feature preparation, evaluation, and interpretation across supervised, unsupervised, and reinforcement-learning problems.

## Objectives

- Building and evaluating classification models with repeatable train/test splits
- Comparing hyperparameters and their effects on accuracy, convergence, and generalization
- Preparing ARFF, CSV, and remote UCI datasets for modeling
- Normalizing continuous features and encoding nominal or categorical features
- Measuring models with accuracy, mean absolute error, coefficient of determination, inertia, and silhouette score
- Investigating overfitting through early stopping, regularization, pruning, and model complexity
- Implementing a Q-learning agent with an epsilon-greedy policy in Gymnasium
- Communicating results through plots, tables, and written analysis in notebooks
- Maintaining readable, linted notebook code with Ruff

## Project map

| Area | Focus | Notebook |
| --- | --- | --- |
| Perceptrons | Linear classification, decision boundaries, convergence, feature weights, and hyperparameter experiments | [Perceptron Lab](perceptron/Perceptron%20Lab.ipynb) · [From-scratch walkthrough](perceptron/Perceptron.ipynb) |
| K-nearest neighbors | Classification, regression, normalization, distance weighting, choice of *k*, and a mixed-type custom distance metric | [KNN Lab](K-nearest-neighbors/KNN_Lab.ipynb) |
| Decision trees | Classification, missing-value handling, one-hot encoding, cross-validation, feature importance, pruning, and regression | [Decision Tree Lab](decision_tree/Decision_Tree_Lab.ipynb) |
| Backpropagation | MLP classification, early stopping, L2 regularization, learning-rate and architecture studies, grid/random search, and regression | [Backpropagation Lab](backpropagation/Backpropagation_Lab.ipynb) |
| Clustering | K-means, hierarchical agglomerative clustering, centroid initialization, linkage comparison, and silhouette analysis | [Clustering Lab](clustering/Clustering_Lab.ipynb) |
| Q-learning | Tabular Q-learning, Bellman updates, epsilon-greedy exploration, policy evaluation, and FrozenLake environments | [Q-learning Lab](Q-learning/QLearning_Lab.ipynb) |

## Selected experiments

The notebooks contain the full code, outputs, plots, and discussion. A few representative documented results include:

- A perceptron reached **97.67% accuracy** on the banknote authentication dataset using the lab's fixed training configuration.
- A KNN classifier achieved **78.95% training accuracy** and **67.44% test accuracy** on one glass-identification split, with probability outputs used to inspect prediction confidence.
- A decision tree classified the Iris dataset at **100% training accuracy** with default settings and **97.33%** with `max_depth=3`, illustrating the effect of restricting model complexity.
- The backpropagation baseline converged after **343 iterations** with **97.5% training accuracy** and **93.33% test accuracy** on the shown Iris split. Early stopping reduced the documented averages to **110.9 iterations**, **89.5% training accuracy**, and **83.67% test accuracy**.
- Iris clustering achieved its highest documented silhouette score at **k=2** (**0.681**). On the Wine comparison, K-means produced a higher silhouette score than HAC at `k=3` (**0.189 vs. 0.158**).
- In Q-learning, the deterministic FrozenLake agent reached a documented mean reward of **1.00 ± 0.00**; the slippery-lake agent reached **0.57 ± 0.50**, showing the effect of stochastic transitions.

These values are tied to the splits and hyperparameters shown in the notebooks; they are included as examples rather than benchmark claims.

## Notebook quality

Code quality is confirmed by Ruff:

```bash
ruff format --check .
ruff check .
```

## Tools

**Languages and environments:** Python, Jupyter Notebook, Gymnasium

**Core libraries:** NumPy, pandas, SciPy, Matplotlib, scikit-learn, `ucimlrepo`, and `imageio`

**Algorithms:** Perceptron, K-nearest neighbors, decision trees, multilayer perceptrons, K-means, hierarchical agglomerative clustering, and tabular Q-learning

**Evaluation and analysis:** train/test splits, cross-validation, accuracy, probability estimates, MAE, R², inertia, silhouette scores, convergence curves, loss curves, and feature-weight interpretation

## Getting started

1. Clone the repository and move into it:

   ```bash
   git clone <repository-url>
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

   On Windows PowerShell, use `.venv\\Scripts\\Activate.ps1` instead.

3. Install the notebook dependencies:

   ```bash
   pip install numpy pandas scipy matplotlib scikit-learn jupyter ucimlrepo gymnasium imageio tqdm ruff
   ```

4. Launch Jupyter and open any notebook from the project map:

   ```bash
   jupyter notebook
   ```

Some notebooks fetch public datasets during execution. An internet connection may therefore be required for the UCI and course-hosted datasets referenced in the cells. The notebooks have been syntax-checked and linted, but full execution is not automated because several experiments depend on external datasets and runtime-specific state.

## Repository layout

```text
.
├── backpropagation/       # MLP classification, regularization, tuning, and regression
├── clustering/            # K-means and hierarchical clustering experiments
├── decision_tree/         # Decision-tree classification and regression
├── K-nearest-neighbors/   # KNN classification, regression, and custom distances
├── perceptron/            # Perceptron labs, examples, and supporting datasets
└── Q-learning/            # Tabular reinforcement learning in FrozenLake
```

## Data and attribution

The notebooks use public datasets from sources including the UCI Machine Learning Repository and course-hosted ARFF files. Dataset-specific source links and citations are preserved in the relevant notebook cells. Please follow each source's terms of use when redistributing or extending the experiments.
