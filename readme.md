# **Principled inference and simulation methods for scientific systems under partial observability.**

Hi, I'm Josh — postdoc at the Bloomberg School of Public Health, Johns Hopkins.

I build computational methods and software for scientific modeling problems where the full system state is never directly observed. My work spans **Bayesian inference**, **numerical solver design**, and **model evaluation**, with a focus on formal guarantees: convergence proofs, proper scoring, calibration diagnostics, and Pareto-optimal tradeoffs between fidelity and computational cost.

Applications include infectious disease forecasting, marine ecosystem dynamics, cultural transmission, and pharmacometrics.

---

# Active Software

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)
Variational Bayesian PCA for incomplete data. Native missingness handling (MCAR/MNAR/block), uncertainty-calibrated posterior outputs, automatic relevance determination for rank selection, C++ accelerated kernels. Currently preparing convergence characterization and JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine)
Operator-partitioned numerical solver for mechanistic scientific models. Supports ODE and IMEX/PDE operator splitting with pluggable linear solver backends. Born from benchmarking the original [FlepiMoP](https://www.flepimop.org) solver, which identified architectural bottlenecks that motivated a ground-up redesign.

## [op_system](https://github.com/ACCIDDA/op_system)
Declarative governing equation specification compiler. Designed particualrly for structured dynaimcal systems eg. age structured edpicdemic models or size structured plankton models.  Transforms structured YAML model definitions into callable numerics consumed by op_engine or other differential equations solvers.  Designed to remove mistakes in bookeeping and reduce the barrier to simulation of complex models.

## [flepimop2](https://github.com/ACCIDDA/flepimop2)
Simulation campaign orchestrator for config-driven batch runs. Pluggable system + engine backends, parameter management, output collection. Domain-agnostic core supporting infectious disease forecasting and scenario modeling workflows.

---

# Core Skills

## Structured Mathematical & Statistical Modeling
Develop and analyze mechanistic and hybrid models using nonlinear ODEs, PDEs, and structured stochastic systems. Emphasis on identifying **diagnostically meaningful summaries**, stability properties, and regime behavior rather than full latent-state reconstruction. Apply simulation-based inference, identifiability diagnostics, and global sensitivity analysis (Sobol, PRCC, Morris).

## Bayesian Inference & Identifiability
Design inference targets and likelihood structures aligned with partial observability. Use hierarchical Bayesian models, variational inference, profile likelihood, posterior predictive checks, and simulation-based identifiability analysis to support robust parameter estimation and uncertainty quantification.

## Scientific Computing & Numerical Methods
Build high-performance, reproducible scientific computing systems in Python and Julia. Experience includes ODE/PDE solver design and benchmarking, operator splitting (IMEX), vectorization, scalable scenario generation, and disciplined software engineering practices (testing, CI/CD, modular design, type-checked codebases).

## Forecasting, Evaluation, and Model Criticism
Develop reduced-order forecasting and scenario models that enforce scientific constraints by construction. Design evaluation tools using proper scoring rules, calibration diagnostics, and Pareto front analysis to assess fidelity-vs-cost tradeoffs beyond point-accuracy metrics.

## Collaboration & Communication
Collaborate across public health, ecology, environmental science, and the social sciences. Communicate results through technical manuscripts, stakeholder-facing briefs, and interdisciplinary presentations, with a focus on interpretability and decision relevance.

---

# Selected Projects

## Operator-Partitioned Solver Ecosystem (Current)
Benchmarking the [FlepiMoP](https://www.flepimop.org) backend ([5×–20× speedups](https://github.com/HopkinsIDD/flepiMoP/pull/592)) revealed architectural limitations that motivated a clean-sheet redesign. The result is the [op_engine](https://github.com/ACCIDDA/op_engine) + [op_system](https://github.com/ACCIDDA/op_system) + [flepimop2](https://github.com/ACCIDDA/flepimop2) stack: a modular, operator-partitioned simulation platform now supporting CDC-funded influenza forecasting.

## VBPCApy Convergence Characterization (Current)
Developing formal convergence guarantees for variational Bayesian PCA: closed-form ELBO monotonicity proofs, CAVI contraction rate bounds, and a systematic grid experiment (15 factors, ~80k configurations) characterizing posterior quality vs. wall time across missingness patterns, priors, and stopping criteria.

## Influenza Scenario Modeling (JHU/UNC Flu Hub)
Led Johns Hopkins/ACCIDDA's JHU/UNC-led seasonal influenza scenario modeling in 2024/25 and 2025/26 seasons. Nationwide simulations using FlepiMoP with hierarchical Bayesian calibration across U.S. states, informing real-time public health decision-making.  Leading scientific overhaul of ACCIDDA's flu model in advance of the 2026/27 season sceanrio round. These scenarios are used in part to help set influenza vaccination policy. 

## Cultural Evolution and Human–Environment Systems
Applied Bayesian PCA, structured distance representations, and network diagnostics to identify dominant transmission pathways in high-dimensional cultural datasets under severe observational constraint.
(See: Macdonald et al., [2024](https://doi.org/10.48550/arXiv.2409.12129))

## Within-Host Viral Dynamics and Spillover Risk (FMDV)
Developed mechanistic viral–immune models for experimental infection data in African buffalo. Applied profile likelihood and simulation-based identifiability analysis to quantify uncertainty under partial observability.
(See: Macdonald et al., [2024](https://doi.org/10.1086/730703))

## Trait-Structured NPZD Ecosystem Modeling
Extended classical NPZD models with toxicity-mediated feedbacks and non-trophic interactions. Bifurcation and resilience analyses to identify regime shifts and persistence margins.
(See: Macdonald & Gulbudak, [2023](https://doi.org/10.1007/s00285-023-01969-7))

## COVID-19 Outbreak Dynamics
Modeled behaviorally mediated COVID-19 transmission under testing-dependent ascertainment and intervention fatigue.
(See: Macdonald et al., [2021](https://doi.org/10.1098/rsos.210227))
