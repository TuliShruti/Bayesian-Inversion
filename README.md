# Self‑Potential (SP) Modeling & Bayesian Inversion

*A reproducible, uncertainty‑aware workflow for interpreting self‑potential logs and de‑risking natural‑hydrogen plays.*

---

## ✨ Overview

This repository combines physics‑based **SP forward modeling** with state‑of‑the‑art **Bayesian inversion** so you can

* recover subsurface parameters ($K$, $\theta$, $h$, $q$) from noisy field data,
* attach **credible** and **prediction** intervals to every estimate, and
* run synthetic what‑if scenarios that improve survey design and lower exploration risk.

> 🔬  Most code lives in Jupyter notebooks to keep the workflow fully transparent and easy to tweak.

---

## 🚀 Key Features

| Theme                           | Highlights                                                                |
| ------------------------------- | ------------------------------------------------------------------------- |
| **Probabilistic core**          | Uniform / Normal priors, Gaussian likelihood, adaptive MCMC (PyMC + DRAM) |
| **Deterministic baseline**      | One–click least‑squares inversion in SciPy for quick sanity checks        |
| **Forward model suite**         | Simulate SP curves for arbitrary parameter sets & noise levels            |
| **Rich diagnostics**            | Corner plots, trace plots, credible/prediction bands via ArviZ & Seaborn  |
| **Full uncertainty accounting** | Posterior summarised as `InferenceData` — no black‑box magic              |

---

## 🗂 Repository Layout

```
├── data/                 # Raw + processed SP logs
├── notebooks/
│   ├── 01_deterministic_ls.ipynb   # Least‑squares benchmark
│   ├── 02_bayesian_inversion.ipynb # PyMC workflow
│   └── 03_forward_modeling.ipynb   # Synthetic tests / survey design
├── src/
│   ├── forward.py        # Physics model
│   ├── priors.py         # Prior helpers
│   ├── likelihood.py     # Likelihood & objective functions
│   └── plot_utils.py     # Re‑usable plotting snippets
├── environment.yml       # Conda spec (alternative to requirements.txt)
└── README.md             # ← you are here
```

---

## ⚡ Quick Start

```bash
# 1. Clone & install
$ git clone https://github.com/<your‑handle>/sp-bayesian-inversion.git
$ cd sp-bayesian-inversion
$ pip install -r requirements.txt      # or: conda env create -f environment.yml

# 2. Run deterministic benchmark
$ jupyter notebook notebooks/01_deterministic_ls.ipynb

# 3. Explore full Bayesian inversion
$ jupyter notebook notebooks/02_bayesian_inversion.ipynb

# 4. Create synthetic SP scenarios
$ jupyter notebook notebooks/03_forward_modeling.ipynb
```

---

## 🔧 Core Dependencies

| Package                  | Purpose                                          |
| ------------------------ | ------------------------------------------------ |
| **PyMC v5**              | MCMC sampling & posterior inference              |
| **ArviZ**                | Diagnostics & visualisation of Bayes output      |
| **NumPy / SciPy**        | Numerical routines & deterministic least‑squares |
| **Matplotlib + Seaborn** | Publication‑quality plotting                     |

> Install via `pip install pymc arviz numpy scipy matplotlib seaborn` or use the provided Conda environment.

---

## 📊 Results Snapshot

| Parameter    | Posterior Mean | 95 % Credible Interval |
| ------------ | -------------- | ---------------------- |
| $K$          | 49.9           | 44.9 – 55.0            |
| $\theta$ (°) | 25.3           | 18.5 – 32.1            |
| $h$          | 29.8           | 23.7 – 36.2            |
| $q$          | 2.05           | 1.53 – 2.57            |

A banded plot of mean prediction (red) plus 95 % credible (blue) & prediction (orange) intervals shows nearly all field points captured — confirming both fit **and** calibrated uncertainty.

---

## 🤔 Why It Matters

Deterministic inversions give one “best” model but no idea how wrong it might be.  Bayesian inversion adds the *range* of plausible models, directly informing drill‑or‑no‑drill decisions in high‑cost natural‑hydrogen exploration.

---

## 📄 License

MIT — free to use, modify & share with attribution.

---

## 🙌 Acknowledgements

Created under the supervision of **Prof. \[Partha P. mandal]**. Field data courtesy of **\[IIT(ISM) Dhanbad]**.

*Feel free to open issues / pull requests — feedback is welcome!*
