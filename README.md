# Student Performance — Exploratory Data Analysis

This repository contains a reproducible, **EDA-only** investigation of the supplied UCI Student Performance data archive. It covers Mathematics and Portuguese course records. **No machine-learning models are built or trained.**

## Contents

- `student_performance_eda.ipynb` — executed Jupyter notebook with tables, diagnostics, and 12 visualizations.
- `student-mat.csv` — supplied Mathematics data.
- `student-por.csv` — supplied Portuguese data.
- `student.txt` — supplied data dictionary.
- `student_performance_eda.pdf` — PDF printout of the executed notebook.
The notebook includes 12 visualizations, with charts embedded directly in the notebook outputs. The HTML report also includes the visualizations.
- `student_performance_eda.html` — standalone HTML report with interactive notebook outputs.

## Run locally

Python 3.10+ is recommended.

```bash
python -m venv .venv
# Windows: .venv\\Scripts\\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook student_performance_eda.ipynb
```

The notebook expects the two CSV files in the same directory and reads them with `sep=';'`.

## Scope

The notebook includes:
1. Dataset structure, dimensions, dtypes, cardinality, and memory footprint.
2. Missing-value, duplicate-row, categorical-domain, and documented-range audits.
3. Descriptive statistics and grade summaries.
4. Univariate, bivariate, and multivariate visual analysis (12 charts).
5. IQR-based outlier flags for review (no automatic deletion).
6. Explicit nominal/ordinal typed copies for downstream preparation.
7. A careful subject-level comparison and evidence-led findings.

## Important data caveat discovered in the supplied files

The two CSVs each have 33 columns, but their schemas differ: Mathematics has a `paid` column, while Portuguese has a `fatherd` column. The supplied `student.txt` dictionary documents `paid` but does not define `fatherd`. The Portuguese `fatherd` field is retained without renaming or guessing its meaning. Clarify this with the data provider before interpreting it.

The two files are separate course samples, not a documented paired panel. Do not match rows across subjects or interpret aggregate differences as within-student changes.

## Data source

UCI Machine Learning Repository, Student Performance dataset (Cortez & Silva). The original archive and accompanying description were supplied by the project user. See the [UCI dataset page](https://archive.ics.uci.edu/dataset/320/student+performance) for provenance and citation guidance.

## Reproducibility and interpretation

- Raw CSVs are preserved unchanged.
- Missing-value imputation is not performed unless supported by the audit.
- IQR flags are diagnostic only; valid extremes are not removed.
- `studytime`, `traveltime`, `famrel`, `freetime`, `goout`, `Dalc`, `Walc`, and `health` are ordinal-coded variables.
- Associations are descriptive, not causal.
- The notebook intentionally does not train, tune, or evaluate any model.
