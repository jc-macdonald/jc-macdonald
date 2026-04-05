# **Principled inference and decision support for scientific systems under partial observability.**

Hi, I'm Josh — postdoc at the Bloomberg School of Public Health, Johns Hopkins.

I build methods, scientific AI/ML, and research software for partially observed systems across earth, environmental, and health sciences. My work integrates **generative modeling** (mechanistic, statistical, and hybrid), **Bayesian inference**, **numerical solver design**, and **model evaluation** — because prediction alone is not enough; the structural assumptions in every model must be tested and defended before anyone acts on the output.

Applications include infectious disease forecasting and decision support, surveillance design, marine and terrestrial ecology, and cultural transmission dynamics.

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/) · [@jcm-sci](https://github.com/jcm-sci)

---

# Software — Primary Architect

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)
Variational Bayesian PCA for incomplete data. Native missingness handling (MCAR/MNAR/block), uncertainty-calibrated posterior outputs, automatic relevance determination for rank selection, C++ accelerated kernels. Currently preparing convergence characterization and JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine)
Operator-partitioned numerical solver for generative scientific models. Supports ODE and IMEX/PDE operator splitting with pluggable linear solver backends. Born from benchmarking the original [FlepiMoP](https://www.flepimop.org) solver, which identified architectural bottlenecks that motivated a ground-up redesign.

## [op_system](https://github.com/ACCIDDA/op_system)
Declarative governing equation specification compiler for structured dynamical systems (e.g., age-structured epidemic models, size-structured plankton models). Transforms YAML model definitions into callable numerics consumed by op_engine or other solvers.

## [flepimop2](https://github.com/ACCIDDA/flepimop2)
Simulation campaign orchestrator for config-driven batch runs. Pluggable system + engine backends, parameter management, output collection. Domain-agnostic core supporting infectious disease forecasting and scenario modeling workflows.

## [model-criticism](https://github.com/jcm-sci/model-criticism)
Observable-based model evaluation framework with proper scoring rules, Pareto optimization, and Bayesian stacking for simulation studies. Determines whether a model deserves the decisions built on it.

## [pp-eigentest](https://github.com/jcm-sci/pp-eigentest)
Posterior predictive eigenvalue testing for signal rank determination in covariance and Gram matrices. Supports ordered hypothesis testing with FWER and FDR control.

# Software — Contributor

## [FlepiMoP](https://github.com/HopkinsIDD/flepiMoP)
Flexible Pipeline for Modeling Pathogens. Contributed [5×–20× runtime speedups](https://github.com/HopkinsIDD/flepiMoP/pull/592) to the simulation backend through profiling-driven optimization.

## [Flu Scenario Modeling Hub](https://github.com/midas-network/flu-scenario-modeling-hub)
MIDAS Network coordination hub for CDC-funded influenza scenario modeling. Contributing team lead submissions and model evaluation infrastructure.

---

# Operational Modeling

## Influenza Scenario Modeling (JHU/UNC Flu Hub, Current)
Lead model developer for ACCIDDA's CDC-funded seasonal influenza scenario modeling across the 2024/25 and 2025/26 seasons. Nationwide simulations using FlepiMoP with hierarchical Bayesian calibration across U.S. states, informing real-time public health decision-making. Leading scientific overhaul in advance of the 2026/27 season. These scenarios are used in part to help set influenza vaccination policy.

## Hib Vaccination Modeling (Navajo Nation, Current)
Technical lead supervising implementation of an age- and immune-status-structured Hib model for the Navajo Nation to evaluate the impact of long-running vaccination programs.

---

# Research

## Operator-Partitioned Solver Ecosystem (Current)
Benchmarking the [FlepiMoP](https://www.flepimop.org) backend revealed architectural limitations that motivated a clean-sheet redesign. The result is the [op_engine](https://github.com/ACCIDDA/op_engine) + [op_system](https://github.com/ACCIDDA/op_system) + [flepimop2](https://github.com/ACCIDDA/flepimop2) stack: a modular, operator-partitioned simulation platform now supporting CDC-funded influenza forecasting.

## VBPCApy Convergence Characterization (Current)
Developing formal convergence guarantees for variational Bayesian PCA: closed-form ELBO monotonicity proofs, CAVI contraction rate bounds, and a systematic grid experiment (15 factors, ~80k configurations) characterizing posterior quality vs. wall time across missingness patterns, priors, and stopping criteria.

---

# Expertise

**Modeling** · Generative models (ODE/PDE/stochastic/hybrid), scientific AI/ML (physics-embedded surrogates, lawful learning), stability and bifurcation analysis, simulation-based inference, global sensitivity analysis (Sobol, PRCC, Morris)

**Inference** · Hierarchical Bayesian models, variational inference, profile likelihood, posterior predictive checks, identifiability analysis, uncertainty quantification

**Computing** · Python, Julia, C++; ODE/PDE solver design and benchmarking, operator splitting (IMEX), vectorization, CI/CD, type-checked codebases

**Evaluation** · Proper scoring rules, calibration diagnostics, Pareto front analysis, reduced-order forecasting models with scientific constraints by construction

*Full details: [jcmacdonald.dev/cv](https://jcmacdonald.dev/cv/)*

---

<table align="center">
<tr><th colspan="2">Languages & Tools</th></tr>
<tr><td><b>Primary</b></td><td>Python · C++ · Julia</td></tr>
<tr><td><b>Secondary</b></td><td>MATLAB/Octave · R · Bash</td></tr>
<tr><td><b>Scientific</b></td><td>NumPy · SciPy · Cython · pybind11 · Numba</td></tr>
<tr><td><b>Infrastructure</b></td><td>GitHub Actions · Docker · pytest · pre-commit</td></tr>
</table>

<p align="center">
  <img src="https://github-contribution-stats.vercel.app/api/?username=jc-macdonald" alt="Contribution Stats" />
</p>
