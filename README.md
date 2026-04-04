# **Principled inference and simulation methods for scientific systems under partial observability.**

Hi, I'm Josh — postdoc at the Bloomberg School of Public Health, Johns Hopkins.

I build computational methods and software for scientific modeling problems where the full system state is never directly observed. My work spans **Bayesian inference**, **numerical solver design**, and **model evaluation**, with a focus on formal guarantees: convergence proofs, proper scoring, calibration diagnostics, and Pareto-optimal tradeoffs between fidelity and computational cost.

Applications include infectious disease forecasting, marine ecosystem dynamics, and pharmacometrics.

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/)

---

# Software — Primary Architect

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)
Variational Bayesian PCA for incomplete data. Native missingness handling (MCAR/MNAR/block), uncertainty-calibrated posterior outputs, automatic relevance determination for rank selection, C++ accelerated kernels. Currently preparing convergence characterization and JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine)
Operator-partitioned numerical solver for mechanistic scientific models. Supports ODE and IMEX/PDE operator splitting with pluggable linear solver backends. Born from benchmarking the original [FlepiMoP](https://www.flepimop.org) solver, which identified architectural bottlenecks that motivated a ground-up redesign.

## [op_system](https://github.com/ACCIDDA/op_system)
Declarative governing equation specification compiler for structured dynamical systems (e.g., age-structured epidemic models, size-structured plankton models). Transforms YAML model definitions into callable numerics consumed by op_engine or other solvers.

## [flepimop2](https://github.com/ACCIDDA/flepimop2)
Simulation campaign orchestrator for config-driven batch runs. Pluggable system + engine backends, parameter management, output collection. Domain-agnostic core supporting infectious disease forecasting and scenario modeling workflows.

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

**Modeling** · Mechanistic ODEs/PDEs, structured stochastic systems, stability and bifurcation analysis, simulation-based inference, global sensitivity analysis (Sobol, PRCC, Morris)

**Inference** · Hierarchical Bayesian models, variational inference, profile likelihood, posterior predictive checks, identifiability analysis, uncertainty quantification

**Computing** · Python, Julia, C++; ODE/PDE solver design and benchmarking, operator splitting (IMEX), vectorization, CI/CD, type-checked codebases

**Evaluation** · Proper scoring rules, calibration diagnostics, Pareto front analysis, reduced-order forecasting models with scientific constraints by construction

*Full details: [jcmacdonald.dev/cv](https://jcmacdonald.dev/cv/)*

---

<p align="center">
  <img src="https://github-readme-stats-sigma-five.vercel.app/api/top-langs/?username=jc-macdonald&layout=compact&theme=default&hide_border=true&langs_count=10" alt="Top Languages" />
</p>

<p align="center">
  <img src="https://github-readme-stats-sigma-five.vercel.app/api?username=jc-macdonald&show_icons=true&hide_border=true&count_private=true&include_all_commits=true&hide_title=true&hide_rank=true" alt="GitHub Stats" />
  <img src="https://github-readme-streak-stats.herokuapp.com?user=jc-macdonald&hide_border=true&date_format=j%20M%5B%20Y%5D" alt="GitHub Streak" />
</p>
