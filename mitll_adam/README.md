# TextFooler (Jin et al.) TDA Visualization and Analysis Archive

## Overview

This archive contains notebooks, adversarial sentence-pair datasets, and visualization outputs for analyzing adversarial attacks on transformer language models using Topological Data Analysis (TDA).

The workflow evaluates transformer sentiment classifiers on IMDb data, generates adversarial examples with TextFooler, and compares clean vs adversarial attention representations through visualization and statistical analysis.

---

# Repository Structure

```text
mitll_adam/
│
├── train.ipynb
├── analyze_pairs.ipynb
├── statistical_tests.ipynb
│
├── attack_pairs_bert.csv
├── attack_pairs_roberta.csv
├── attack_pairs_distilbert.csv
│
├── attack_pairs_bert_updated.csv
├── attack_pairs_roberta_updated.csv
├── attack_pairs_distilbert_updated.csv
│
└── visualizations/
    ├── bert/
    ├── roberta/
    └── distilbert/
```

---

# Notebook Overview

## `train.ipynb`

Main notebook for:

- loading and fine-tuning transformer models,
- evaluating IMDb sentiment classification,
- generating adversarial examples using TextFooler,
- exporting clean/adversarial text pairs as CSV files.

### Outputs

Generates CSV files containing adversarial attack pairs:

- `attack_pairs_*.csv`
- `attack_pairs_*_updated.csv`

---

## `analyze_pairs.ipynb`

Main analysis and visualization notebook.

Performs:

- attention extraction,
- persistence diagram generation,
- Wasserstein distance computation,
- KDE/survival curve visualization,
- contour overlays and heatmaps.

### Outputs

Produces visualization artifacts stored in:

```text
visualizations/
```

with separate directories for each model.

---

## `statistical_tests.ipynb`

Performs statistical analysis on generated Wasserstein metrics.

Includes:

- layer-wise statistical testing,
- distribution comparisons,
- violin plots,
- summary visualizations.

---

# CSV Files

The CSV files contain clean/adversarial text pairs and associated metadata for each transformer model.

Typical fields include:

- original text,
- adversarial text,
- predictions,
- attack success indicators,
- confidence scores.

---

# Visualization Outputs

The `visualizations/` directory contains generated figures such as:

- attention maps,
- persistence diagrams,
- persistence KDE plots,
- survival curves,
- Wasserstein heatmaps,
- contour overlays.

Outputs are grouped by model:

```text
visualizations/
    bert/
    roberta/
    distilbert/
```

---

# Recommended Execution Order

## 1. Generate Adversarial Examples

Run:

```text
train.ipynb
```

---

## 2. Generate TDA Visualizations

Run:

```text
analyze_pairs.ipynb
```

---

## 3. Run Statistical Analysis

Run:

```text
statistical_tests.ipynb
```

---

# Environment Notes

Recommended:

```text
Python 3.10+
```

```text
textattack
transformers
torch
datasets
numpy
pandas
scipy
matplotlib
seaborn
ripser
persim
```

Using a venv and enabling GPU acceleration are strongly recommended for attack generation and large-scale analysis.

---

# Notes

- Notebook outputs consist of many graphs and may be large.
- Future teams should verify package compatibility before rerunning experiments.

