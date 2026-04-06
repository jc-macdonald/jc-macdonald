# **Decision support and principled inference for scientific systems under partial observability.**

Hi, I'm Josh — postdoc at the Bloomberg School of Public Health, Johns Hopkins.

I determine what actions to take, what experiments to run, and what measurements are worth collecting in systems where interventions are costly and uncertainty is unavoidable. To do this, I build methods, scientific AI/ML, and research software for partially observed systems across earth, environmental, and health sciences — integrating **generative modeling** (mechanistic, statistical, and hybrid), **Bayesian inference**, **numerical solver design**, and **model evaluation**. Prediction alone is not enough; the structural assumptions in every model must be tested and defended before anyone acts on the output.

Applications include infectious disease forecasting and intervention timing, surveillance design, marine and terrestrial ecology, and cultural transmission dynamics. This work has directly informed CDC influenza vaccination policy, wildlife disease surveillance in sub-Saharan Africa, and public health resource allocation during respiratory virus seasons.

**Domains → Tools:**  Infectious disease ([op_engine](https://github.com/ACCIDDA/op_engine), [flepimop2](https://github.com/ACCIDDA/flepimop2), [Flu Hub](https://github.com/midas-network/flu-scenario-modeling-hub)) · Wildlife & zoonotic disease ([op_engine](https://github.com/ACCIDDA/op_engine), [model-criticism](https://github.com/jcm-sci/model-criticism)) · Cultural evolution & genomics ([VBPCApy](https://github.com/yoavram-lab/VBPCApy), [pp-eigentest](https://github.com/yoavram-lab/pp-eigentest)) · Marine ecology ([op_system](https://github.com/ACCIDDA/op_system), [model-criticism](https://github.com/jcm-sci/model-criticism)) · Cross-domain methods ([model-criticism](https://github.com/jcm-sci/model-criticism), [pp-eigentest](https://github.com/yoavram-lab/pp-eigentest))

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/) · [@jcm-sci](https://github.com/jcm-sci)

---

# Software — Primary Architect

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![CI](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml/badge.svg)](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml) [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)
**Status: Released on PyPI · JOSS submission in preparation**

Recovers hidden population structure from datasets with substantial missing entries — applied to cultural, genetic, and survey data where complete records are rare. Used in [Macdonald et al. (2024, *Evolutionary Human Sciences*)](https://doi.org/10.1017/ehs.2024.45). Variational Bayesian PCA with native missingness handling (MCAR/MNAR/block), uncertainty-calibrated posterior outputs, automatic relevance determination for rank selection, and C++ accelerated kernels. Currently preparing convergence characterization and JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine) · [![CI](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yml/badge.svg)](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_engine/)
**Status: Active development · In production for CDC flu forecasting**

Simulation engine powering CDC-funded influenza forecasting and wildlife disease modeling. Lightweight multiphysics solver core for time-dependent systems with explicit ODE solvers, IMEX/operator-splitting schemes, and pluggable linear solver backends. Framework-agnostic; separates state management from stepping logic.

## [op_system](https://github.com/ACCIDDA/op_system) · [![CI](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yml/badge.svg)](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_system/)
**Status: Active development**

Lets modelers define disease or ecological models in plain configuration files rather than writing solver code. Declarative equation compiler for structured dynamical systems (age-structured epidemic models, size-structured ecological models) that transforms YAML definitions into callable numerics consumed by op_engine or other solvers.

## Model Criticism — observable-based model evaluation · [![CI](https://github.com/jcm-sci/model-criticism/actions/workflows/ci.yml/badge.svg)](https://github.com/jcm-sci/model-criticism/actions/workflows/ci.yml)
**Status: Active development**

Answers the question: *should you trust this model's predictions before acting on them?* Structured evaluation framework using model worlds with known ground truth, observable-based scoring, multi-objective Pareto optimization, and Bayesian model stacking. Organizes evaluation into hierarchical phases (discovery → refinement → benchmark).

- **[model-criticism](https://github.com/jcm-sci/model-criticism)** (Python) — wraps scoringrules, pymoo, arviz, SALib, optuna.
- **[ModelCriticism.jl](https://github.com/jcm-sci/ModelCriticism.jl)** (Julia) — wraps Metaheuristics.jl, ParetoSmooth.jl, QuasiMonteCarlo.jl, GlobalSensitivity.jl. Native scoring rules.

## [pp-eigentest](https://github.com/yoavram-lab/pp-eigentest)
**Status: Pre-release · Companion to [arXiv:2409.12129](https://arxiv.org/abs/2409.12129) · Public release planned with paper**

Determines how many meaningful patterns exist in a dataset, separating signal from noise. Posterior predictive eigenvalue testing for covariance and Gram matrices with ordered hypothesis testing, FWER and FDR control. Applied in [Macdonald et al. (2024, *Evolutionary Human Sciences*)](https://doi.org/10.1017/ehs.2024.45); method paper: [arXiv:2409.12129](https://arxiv.org/abs/2409.12129).

# Software — Contributor

## [flepimop2](https://github.com/ACCIDDA/flepimop2) · [![CI](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yml/badge.svg)](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yml)
Manages the large-scale simulation campaigns that produce CDC scenario projections and forecasts. Config-driven batch orchestrator with pluggable system + engine backends, parameter management, and output collection.

## [FlepiMoP](https://github.com/HopkinsIDD/flepiMoP)
Flexible Pipeline for Modeling Pathogens. Contributed [5×–20× runtime speedups](https://github.com/HopkinsIDD/flepiMoP/pull/592) to the simulation backend through profiling-driven optimization.

## [Flu Scenario Modeling Hub](https://github.com/midas-network/flu-scenario-modeling-hub)
MIDAS Network coordination hub for CDC-funded influenza scenario modeling. Contributing team lead submissions and model evaluation infrastructure.

---

# Operational Modeling

## Influenza Scenario Modeling (JHU/UNC Flu Hub, Current)
Lead model developer for ACCIDDA's CDC-funded seasonal influenza scenario modeling across the 2024/25, 2025/26, and 2026/27 seasons. Set up the ACCIDDA flu model and operational pipeline (2024/25). Extensive work with external modeling packages drove contributions that led to FlepiMoP2 (2025/26). Supervising an undergraduate student in a scientific overhaul of the flu model (2026/27). These scenarios inform real-time public health decision-making and are used in part to help set influenza vaccination policy.

## Hib Vaccination Modeling (Navajo Nation, Current)
Technical lead supervising implementation of an age- and immune-status-structured Hib model for the Navajo Nation to evaluate the impact of long-running vaccination programs.

---

# Research

## Operator-Partitioned Solver Ecosystem (Current)
Benchmarking the [FlepiMoP](https://www.flepimop.org) backend revealed architectural limitations that motivated a clean-sheet redesign. The result is the [op_engine](https://github.com/ACCIDDA/op_engine) + [op_system](https://github.com/ACCIDDA/op_system) + [flepimop2](https://github.com/ACCIDDA/flepimop2) stack: a modular, operator-partitioned simulation platform now supporting CDC-funded influenza forecasting.

## VBPCApy Convergence Characterization (Current)
Developing formal convergence guarantees for variational Bayesian PCA ([VBPCApy](https://github.com/yoavram-lab/VBPCApy)): closed-form ELBO monotonicity proofs, CAVI contraction rate bounds, and a systematic grid experiment (15 factors, ~80k configurations) characterizing posterior quality vs. wall time across missingness patterns, priors, and stopping criteria.

---

# Expertise

These capabilities are deployed to design interventions, optimize surveillance strategies, and determine what experiments and measurements are worth their cost.

**Modeling** · Generative models (ODE/PDE/stochastic/hybrid), scientific AI/ML (physics-embedded surrogates), stability and bifurcation analysis, simulation-based inference, global sensitivity analysis (Sobol, PRCC, Morris)

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
