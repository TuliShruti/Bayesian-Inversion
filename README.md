# Bayesian Inversion
# Self Potential Modeling and Bayesian Inference

This project focuses on modeling Self Potential (SP) using Bayesian inference. The code implements a probabilistic approach to analyze and predict SP values, incorporating uncertainty quantification and posterior predictive checks. It leverages libraries like PyMC, NumPy, and Matplotlib to construct priors, likelihoods, and posterior distributions.

---

## Features

- **Bayesian Modeling**: Implements Bayesian inference for SP modeling using probabilistic priors (`m`, `b`, and `σ`) and a likelihood function.
- **Posterior Analysis**: Analyzes posterior distributions of model parameters and visualizes credible intervals.
- **Predictive Checks**: Generates posterior predictive distributions to evaluate model performance.
- **Interactive Visualizations**: Creates insightful plots to understand parameter distributions and their confidence intervals.
- **Noise Simulation**: Includes random noise in the observed data to simulate real-world uncertainty and validate the model's robustness.

---

## Prerequisites

To run the project, you need the following Python libraries:

- [PyMC](https://docs.pymc.io/) (for Bayesian inference)
- [NumPy](https://numpy.org/) (for mathematical operations)
- [Matplotlib](https://matplotlib.org/) (for plotting)
- [Seaborn](https://seaborn.pydata.org/) (for enhanced data visualizations)

Install the dependencies using pip:

```bash
pip install pymc numpy matplotlib seaborn
