# **Decision support and principled inference for scientific systems under partial observability.**

Hi, I'm Josh — Assistant Scientist in the Department of International Health within the Bloomberg School of Public Health at Johns Hopkins University.

I determine what actions to take, what experiments to run, and what measurements are worth collecting in systems where interventions are costly and uncertainty is unavoidable. To do this, I build open scientific computing infrastructure — **declarative modeling**, **simulation**, and **generative decision support** — for partially observed systems across health, environmental, and earth sciences, integrating **generative modeling** (mechanistic, statistical, and hybrid), **Bayesian inference**, **numerical solver design**, and **model evaluation**. Prediction alone is not enough; the structural assumptions in every model must be tested and defended before anyone acts on the output.

Applications include infectious disease forecasting and intervention timing, surveillance design, marine and terrestrial ecology, and cultural transmission dynamics. The infectious disease tools contribute to CDC-funded multi-model scenario evidence used for public-health planning; other applications include wildlife disease surveillance design in sub-Saharan Africa and cross-scale ecological modeling.

**Domains → Tools:** Infectious disease ([op_engine](https://github.com/ACCIDDA/op_engine), [flepimop2](https://github.com/ACCIDDA/flepimop2), [Flu Hub](https://github.com/midas-network/flu-scenario-modeling-hub)) · Wildlife & zoonotic disease ([op_engine](https://github.com/ACCIDDA/op_engine), [trade-study](https://github.com/jcm-sci/trade-study)) · Cultural evolution & genomics ([VBPCApy](https://github.com/yoavram-lab/VBPCApy), [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)) · Marine ecology ([op_system](https://github.com/ACCIDDA/op_system), [trade-study](https://github.com/jcm-sci/trade-study)) · Cross-domain methods ([trade-study](https://github.com/jcm-sci/trade-study), [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/))

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/) · [@jcm-sci](https://github.com/jcm-sci)

## Research in progress

- **[Structural scores](https://jcmacdonald.dev/projects/current_analyses/#structural-scores-and-scientific-prediction):** assessing scientific predictions against declared constraints, including checks before outcomes are observed, alongside predictive evaluation.
- **[Inference and calibration](https://jcmacdonald.dev/projects/inference_calibration/):** working research software connects Bayesian fitting, simulation-based calibration and replicated study-design checks. The software remains private and pre-release; application-specific validation is ongoing.
- **[Scientific applications](https://jcmacdonald.dev/projects/current_analyses/#application-studies):** ongoing work on dengue within-host dynamics, COVID-19 observation noise, diphtheria vaccination and CCHF surveillance.

These summaries describe research questions and aims. Public papers and artifacts are linked as they become available.

---

# Software — Primary Architect

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![CI](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml/badge.svg)](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml) [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)

**Status: Released on PyPI · JOSS submission in preparation**

Recovers hidden population structure from datasets with substantial missing entries — applied to cultural, genetic, and survey data where complete records are rare. Used in [Macdonald et al. (2024, _Evolutionary Human Sciences_)](https://doi.org/10.1017/ehs.2024.45). Variational Bayesian PCA for incomplete data with native per-entry missingness handling, full posterior uncertainty quantification, automatic component pruning, built-in model selection, C++-accelerated kernels, and a scikit-learn-compatible API. Current work focuses on package hardening and a JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine) · [![CI](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_engine/)

**Status: Released on [PyPI](https://pypi.org/project/op-engine/) · Active development · CDC-funded scenario modeling**

Framework-independent numerical core for compartmental and spatial models, used in CDC-funded influenza scenario modeling and wildlife disease research. It provides explicit, IMEX, implicit and stochastic methods, named observations, adaptive-schedule replay, and independent NumPy CPU SSA banks with optional reaction firing counts. The [backend qualification matrix](https://accidda.github.io/op_engine/latest/guides/backend-qualification/) identifies tested NumPy, JAX and CPU PyTorch methods and derivatives; GPU execution needs separate hardware qualification. Use the core directly or through the separately packaged FlepiMoP2 provider.

## [op_system](https://github.com/ACCIDDA/op_system) · [![CI](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_system/)

**Status: Released on [PyPI](https://pypi.org/project/op-system/) · Active development**

Declarative specification language and compiler for structured dynamical systems. Restricted equations or transition models compile to vectorized right-hand sides for NumPy, JAX and PyTorch, with flat, structured and independent-block state layouts. The compiler publishes reaction metadata, named observables, forcing schedules and checked replicate-independence declarations for numerical consumers. Structural validation is complemented by independent-equation and conservation checks; [constraint metadata is not yet enforced](https://accidda.github.io/op_system/latest/guides/getting-started/#cross-axis-constraints-current-boundary).

## [trade-study](https://github.com/jcm-sci/trade-study) — multi-objective trade-study orchestration · [![CI](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml/badge.svg)](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19599838.svg)](https://doi.org/10.5281/zenodo.19599838) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://jcm-sci.github.io/trade-study/)

**Status: Released on PyPI**

Design and evaluation framework for comparing simulation configurations against competing objectives. Build grids, run replicated studies and hierarchical phases, compare designs with shared random numbers, and report Pareto fronts, preferences, regret and practical equivalence. Optional integrations provide proper scoring rules, sensitivity analysis, adaptive search, surrogate models and model weighting. Fixed or adaptive replication and provenance-checked result bundles make the study contract explicit; calibration, power and transfer to observational data still need application-specific evidence.

[Documentation and executable examples](https://jcm-sci.github.io/trade-study/guide/capabilities/).

## [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)

**Status: Ongoing methods research · Private pre-release software · Methods paper in preparation**

Investigates how many latent dimensions an incomplete dataset can support, using posterior predictive eigenvalue testing and Bayesian latent-variable models. Current work studies rank decisions, uncertainty and calibration, building on the earlier methodology described in the [2024 preprint](https://arxiv.org/abs/2409.12129). The ongoing study is distinct from the released VBPCApy package.

# Software — Contributor

## [flepimop2](https://github.com/ACCIDDA/flepimop2) · [![CI](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml)

Configuration-driven orchestration engine for CDC-supported infectious disease forecasting and scenario analysis. Plugin architecture decouples model specification, numerical integration, and output persistence.

## [FlepiMoP](https://github.com/HopkinsIDD/flepiMoP)

Flexible Pipeline for Modeling Pathogens. Contributed [5×–20× runtime speedups](https://github.com/HopkinsIDD/flepiMoP/pull/592) to the simulation backend through profiling-driven optimization.

## [Flu Scenario Modeling Hub](https://github.com/midas-network/flu-scenario-modeling-hub)

MIDAS Network coordination hub for CDC-funded influenza scenario modeling. Contributing team lead submissions and model evaluation infrastructure.

---

# Operational Modeling

## Influenza Scenario Modeling (JHU/UNC Flu Hub, Current)

Lead model developer for ACCIDDA's CDC-funded seasonal influenza scenario modeling across the 2024/25, 2025/26, and 2026/27 seasons. Set up the ACCIDDA flu model and operational pipeline (2024/25). Extensive work with external modeling packages drove contributions that led to FlepiMoP2 (2025/26). Supervising an undergraduate student in a scientific overhaul of the flu model (2026/27). These contributions form part of the multi-model evidence produced by the CDC Flu Scenario Modeling Hub for public-health planning.

## Hib Vaccination Modeling (Navajo Nation, Current)

Technical lead supervising implementation of an age- and immune-status-structured Hib model for the Navajo Nation to evaluate the impact of long-running vaccination programs.

---

# Research

## Operator-Partitioned Simulation Stack (Current)

Benchmarking the [FlepiMoP](https://www.flepimop.org) backend revealed architectural limitations that motivated a clean-sheet redesign. The result is the [op_system](https://github.com/ACCIDDA/op_system) + [op_engine](https://github.com/ACCIDDA/op_engine) + [flepimop2](https://github.com/ACCIDDA/flepimop2) stack: a restricted specification compiler, an Array-API-polymorphic operator-partitioned solver with backend-native execution providers, and a configuration-driven campaign orchestrator. The public cores also expose forcing schedules, named observables and independent-replicate reaction contracts. [trade-study](https://github.com/jcm-sci/trade-study) adds replicated design and evaluation workflows. Adaptive replay gradients are conditional on the recorded mesh; accuracy checks determine when a fresh solve is needed.

## Current Analysis Portfolio

- Dengue antibody-dependent-enhancement modeling and Bayesian analysis
- Outcome-independent structural scores for scientific predictions
- COVID-19 observation-noise sensitivity experiments
- Diphtheria outbreak-vaccination modeling
- CCHF surveillance and control design across wildlife and livestock systems
- VBPCApy package hardening and JOSS manuscript preparation

---

# Expertise

These capabilities are deployed to design interventions, optimize surveillance strategies, and determine what experiments and measurements are worth their cost.

**Modeling** · Generative models (ODE/PDE/stochastic/hybrid), scientific AI/ML (physics-embedded surrogates), stability and bifurcation analysis, simulation-based inference, global sensitivity analysis (Sobol, PRCC, Morris)

**Inference** · Hierarchical Bayesian models, variational inference, profile likelihood, posterior predictive checks, identifiability analysis, uncertainty quantification

**Computing** · Python, Julia, C++; ODE/PDE solver design and benchmarking, operator splitting (IMEX), vectorization, CI/CD, type-checked codebases

**Evaluation** · Proper scoring rules, calibration diagnostics, Pareto front analysis, reduced-order forecasting models with scientific constraints by construction

_Full details: [jcmacdonald.dev/cv](https://jcmacdonald.dev/cv/)_

---

<table align="center">
<tr><th colspan="2">Languages & Tools</th></tr>
<tr><td><b>Primary</b></td><td>Python · C++ · Julia</td></tr>
<tr><td><b>Secondary</b></td><td>MATLAB/Octave · R · Bash</td></tr>
<tr><td><b>Scientific</b></td><td>NumPy · SciPy · Cython · pybind11 · Numba</td></tr>
<tr><td><b>Infrastructure</b></td><td>GitHub Actions · Docker · pytest · pre-commit</td></tr>
</table>

<p align="center">
  <a href="https://github.com/jc-macdonald">
    <img height="180" src="https://github-readme-stats.vercel.app/api?username=jc-macdonald&show_icons=true&theme=github_dark_dimmed&hide_border=true&include_all_commits=true&count_private=true" alt="GitHub Stats" />
  </a>
</p>
<p align="center">
  <a href="https://github.com/jc-macdonald">
    <img src="https://streak-stats.demolab.com/?user=jc-macdonald&theme=github_dark_dimmed&hide_border=true" alt="GitHub Streak" />
  </a>
</p>
