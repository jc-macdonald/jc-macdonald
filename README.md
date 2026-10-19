# Joshua C. Macdonald

I'm Josh, an Assistant Scientist in the Department of International Health at the Johns Hopkins Bloomberg School of Public Health.

I develop mathematical models, statistical methods, and software for health, environmental, and earth sciences. I study how systems change over time, how well models describe their behavior, and how models can inform interventions and data collection. A recurring question is how measurements and scientific assumptions affect the conclusions we draw.

Applications include infectious disease forecasting and intervention timing, surveillance design, marine and terrestrial ecology, and cultural transmission dynamics. The infectious disease tools contribute to CDC-funded multi-model scenario evidence used for public-health planning; other applications include wildlife disease surveillance design in sub-Saharan Africa and cross-scale ecological modeling.

| Research area                   | Related tools                                                                                                                                                               |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Infectious disease              | [op_engine](https://github.com/ACCIDDA/op_engine), [flepimop2](https://github.com/ACCIDDA/flepimop2), [Flu Hub](https://github.com/midas-network/flu-scenario-modeling-hub) |
| Wildlife and zoonotic disease   | [op_engine](https://github.com/ACCIDDA/op_engine), [trade-study](https://github.com/jcm-sci/trade-study)                                                                    |
| Cultural evolution and genomics | [VBPCApy](https://github.com/yoavram-lab/VBPCApy), [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)                                                           |
| Marine ecology                  | [op_system](https://github.com/ACCIDDA/op_system), [trade-study](https://github.com/jcm-sci/trade-study)                                                                    |
| Statistical methods             | [trade-study](https://github.com/jcm-sci/trade-study), [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)                                                       |

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/) · [@jcm-sci](https://github.com/jcm-sci)

## Research in progress

- **[Structural scores](https://jcmacdonald.dev/projects/current_analyses/#structural-scores-and-scientific-prediction).** Assessing predictions against declared scientific constraints, including checks before outcomes are observed.
- **[Inference and calibration with op_infer](https://jcmacdonald.dev/projects/inference_calibration/).** Research software for Bayesian fitting, simulation-based calibration and replicated study-design checks. It remains private, pre-alpha and unreleased while application studies continue.
- **[Scientific applications](https://jcmacdonald.dev/projects/current_analyses/#application-studies).** Dengue within-host dynamics, COVID-19 observation noise, diphtheria vaccination and CCHF surveillance.

These summaries describe research questions and aims. Public papers and artifacts are linked as they become available.

---

# Software I develop

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![CI](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml/badge.svg)](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml) [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)

Released on PyPI. JOSS submission in preparation.

Variational Bayesian PCA for incomplete cultural, genetic, and survey data. The package models observed entries directly and estimates uncertainty through a variational posterior. It provides component pruning, model-selection tools, C++ kernels, and a scikit-learn-compatible API. It was used in [Macdonald et al. (2024, _Evolutionary Human Sciences_)](https://doi.org/10.1017/ehs.2024.45). Current work focuses on testing, packaging, and a JOSS submission.

## [op_engine](https://github.com/ACCIDDA/op_engine) · [![CI](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_engine/)

Released on [PyPI](https://pypi.org/project/op-engine/). In active development and used in CDC-funded scenario modeling.

Framework-independent numerical core for PDE/structured-field, nonlocal, compartmental and stochastic reaction models, used in CDC-funded influenza scenario modeling and wildlife disease research. It provides explicit, IMEX, implicit and stochastic methods, named observations, adaptive-schedule replay, and independent NumPy CPU SSA banks with optional reaction firing counts. The [backend qualification matrix](https://accidda.github.io/op_engine/latest/guides/backend-qualification/) identifies tested NumPy, JAX and CPU PyTorch methods and derivatives; GPU execution needs separate hardware qualification. Use the core directly or through the separately packaged FlepiMoP2 provider.

## [op_system](https://github.com/ACCIDDA/op_system) · [![CI](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_system/)

Released on [PyPI](https://pypi.org/project/op-system/). In active development.

Declarative specification language and compiler for PDE/structured-field, nonlocal, compartmental and stochastic reaction models. Restricted equations or transition models compile to vectorized right-hand sides for NumPy, JAX and PyTorch, with flat, structured and independent-block state layouts. The compiler publishes reaction metadata, named observables, forcing schedules and checked replicate-independence declarations for numerical consumers. Structural validation is complemented by independent-equation and conservation checks; [constraint metadata is not yet enforced](https://accidda.github.io/op_system/latest/guides/getting-started/#cross-axis-constraints-current-boundary).

## [trade-study](https://github.com/jcm-sci/trade-study) · [![CI](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml/badge.svg)](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19599838.svg)](https://doi.org/10.5281/zenodo.19599838) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://jcm-sci.github.io/trade-study/)

Released on PyPI.

Compares simulation configurations against competing objectives. It builds design grids, runs replicated studies in phases, compares designs with shared random numbers, and reports Pareto fronts, regret and practical equivalence under specified preferences. Optional integrations add scoring rules, sensitivity analysis, adaptive search, surrogate models and model weighting. Results retain replicate counts, uncertainty assumptions and provenance. Calibration, power and applicability to observed data need separate assessment.

[Documentation and executable examples](https://jcm-sci.github.io/trade-study/guide/capabilities/).

## [op_infer](https://jcmacdonald.dev/projects/inference_calibration/)

Private pre-alpha research software. Unreleased.

Connects Bayesian fitting through established inference libraries, simulation-based calibration and replicated study-design checks. The implementation uses the simulation and evaluation tools above. Broader interfaces and application studies remain in development.

## [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)

Ongoing methods research with private pre-release software. A methods paper is in preparation.

Investigates how many latent dimensions an incomplete dataset can support, using posterior predictive eigenvalue testing and Bayesian latent-variable models. Current work studies rank decisions, uncertainty and calibration, building on the earlier methodology described in the [2024 preprint](https://arxiv.org/abs/2409.12129). The ongoing study is distinct from the released VBPCApy package.

# Other software contributions

## [flepimop2](https://github.com/ACCIDDA/flepimop2) · [![CI](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml)

Configuration-driven orchestration engine for CDC-supported infectious disease forecasting and scenario analysis. Plugin architecture decouples model specification, numerical integration, and output persistence.

## [FlepiMoP](https://github.com/HopkinsIDD/flepiMoP)

Flexible Pipeline for Modeling Pathogens. Contributed profiling and [vectorized simulation-backend code](https://github.com/HopkinsIDD/flepiMoP/pull/592).

## [Flu Scenario Modeling Hub](https://github.com/midas-network/flu-scenario-modeling-hub)

MIDAS Network coordination hub for CDC-funded influenza scenario modeling. Contributing team lead submissions and model evaluation infrastructure.

---

# Operational Modeling

## Influenza Scenario Modeling (JHU/UNC Flu Hub, Current)

Lead model developer for ACCIDDA's CDC-funded seasonal influenza scenario modeling across the 2024/25, 2025/26, and 2026/27 seasons. Set up the ACCIDDA flu model and operational pipeline (2024/25). Work with external modeling packages informed my contributions to FlepiMoP2 (2025/26). Supervising an undergraduate student on revisions to the flu model (2026/27). These contributions form part of the multi-model evidence produced by the CDC Flu Scenario Modeling Hub for public-health planning.

## Hib Vaccination Modeling (Navajo Nation, Current)

Technical lead supervising implementation of an age- and immune-status-structured Hib model for the Navajo Nation to evaluate the impact of long-running vaccination programs.

---

# Research

## Operator-Partitioned Simulation Stack (Current)

Profiling the [FlepiMoP](https://www.flepimop.org) backend informed the design of [op_system](https://github.com/ACCIDDA/op_system), [op_engine](https://github.com/ACCIDDA/op_engine) and [flepimop2](https://github.com/ACCIDDA/flepimop2). These packages separate model specification, numerical simulation and campaign execution. Their interfaces include forcing schedules, named observables and independent-replicate reactions. [trade-study](https://github.com/jcm-sci/trade-study) supports replicated design and evaluation. Adaptive replay gradients are conditional on the recorded mesh, and changed parameters may require a fresh solve.

## Current application studies

- Dengue antibody-dependent-enhancement modeling and Bayesian analysis
- Outcome-independent structural scores for scientific predictions
- COVID-19 observation-noise sensitivity experiments
- Diphtheria outbreak-vaccination modeling
- CCHF surveillance and control design across wildlife and livestock systems
- VBPCApy package hardening and JOSS manuscript preparation

---

# Expertise

My work uses these methods to study interventions, compare surveillance strategies, and assess the value of additional observations.

**Modeling** · Differential-equation, stochastic and hybrid models; machine learning with scientific constraints; stability and bifurcation analysis; simulation-based inference; global sensitivity analysis (Sobol, PRCC, Morris)

**Inference** · Hierarchical Bayesian models, variational inference, profile likelihood, posterior predictive checks, identifiability analysis, uncertainty quantification

**Computing** · Python, Julia, C++; ODE/PDE solver design and benchmarking, operator splitting (IMEX), vectorization, CI/CD, type-checked codebases

**Evaluation** · Proper scoring rules, calibration diagnostics, Pareto front analysis, reduced-order forecasting models with specified scientific constraints

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
