# Joshua C. Macdonald

I'm Josh, an Assistant Scientist in the Department of International Health at the Johns Hopkins Bloomberg School of Public Health.

My research asks how processes within hosts shape immune response and protection, how they link to transmission between hosts, and how movement, contact, and ecological change shape spread and persistence across populations. I develop mechanistic models, inference methods, and open research software for these questions and for decisions under uncertainty.

Established work spans human infectious disease, livestock and wildlife health, ecology, and cultural transmission. Developing work extends the same multiscale approach to longitudinal clinical data and to the design of experiments, studies, monitoring programs, and surveillance. The infectious disease tools contribute to CDC-funded multi-model scenario evidence used for public-health planning.

🌐 [jcmacdonald.dev](https://jcmacdonald.dev) · [Publications](https://jcmacdonald.dev/publications/) · [CV](https://jcmacdonald.dev/cv/) · [@jcm-sci](https://github.com/jcm-sci)

## Research in progress

- **[Proposed clinical direction](https://jcmacdonald.dev/projects/#proposed-clinical-direction).** My influenza scenario-modeling work requires assumptions about individual immune responses that population hospital admissions do not directly measure. I am developing a mentored clinical-research proposal on antibody responses after influenza vaccination in adults over 75: how they rise and decline, and whether the previous season's antibody trajectory improves prediction of the current season's response beyond the current pre-vaccination titer. Clinical and laboratory training would support this work; relating antibody trajectories to protection is a later question.
- **[Scenario-model evaluation](https://jcmacdonald.dev/projects/current_analyses/#constraint-checks-for-predictions).** Studying whether declared checks of scenario-model submissions reveal consequential inconsistencies. Their predictive usefulness remains an empirical question.
- **[Inference and calibration with op_infer](https://jcmacdonald.dev/projects/inference_calibration/).** Public pre-alpha research software for Bayesian fitting, simulation-based calibration and replicated study-design checks. It is unreleased on PyPI while broader interfaces and application-specific validation develop.
- **[Scientific applications](https://jcmacdonald.dev/projects/current_analyses/#application-studies).** Dengue within-host dynamics, COVID-19 observation noise, diphtheria vaccination and CCHF surveillance.

In 2027 I will participate in the unpaid, virtual Scholar program of Duke University's [Center of Excellence for Multiscale Immune Systems Modeling](https://immunescale.org/). The program provides mentorship and training but no salary or stipend.

Public papers and artifacts are linked as they become available.

---

# Operational Modeling

## Influenza Scenario Modeling (JHU/UNC Flu Hub, Current)

Lead model developer for ACCIDDA's CDC-funded seasonal influenza scenario modeling across the 2024/25, 2025/26, and 2026/27 seasons. I established the model and operational pipeline in 2024/25; work with external modeling packages informed my contributions to FlepiMoP2 in 2025/26. For 2026/27, I led model fitting across states and seasons, inference checks using simulated data, and predictive evaluation, while supervising an undergraduate on model revisions. These contributions form part of the multi-model evidence produced by the Influenza Scenario Modeling Hub for public-health planning.

## COVID-19 Scenario Modeling (2026/27)

Led ACCIDDA's 2026/27 COVID-19 Scenario Modeling Hub submission.

## Hib Vaccination Modeling (Current)

Technical supervisor for PhD students implementing an age- and immune-status-structured Hib model to evaluate long-running vaccination programs in a partner-defined population. Public descriptions remain general pending approval from participating organizations.

---

# Software I develop

The packages separate model specification, numerical simulation, inference and replicated evaluation. Their interfaces support applications across scientific disciplines.

| Capability | Related tools |
| --- | --- |
| Model specification | [op_system](https://github.com/ACCIDDA/op_system) |
| Numerical simulation | [op_engine](https://github.com/ACCIDDA/op_engine) |
| Inference and calibration | [op_infer](https://github.com/ACCIDDA/op_infer) |
| Experiment and observation design | [trade-study](https://github.com/jcm-sci/trade-study) |
| Incomplete-data structure | [VBPCApy](https://github.com/yoavram-lab/VBPCApy), [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/) |
| Infectious-disease campaign execution | [flepimop2](https://github.com/ACCIDDA/flepimop2), [Flu Hub](https://github.com/midas-network/flu-scenario-modeling-hub) |

## [VBPCApy](https://github.com/yoavram-lab/VBPCApy) · [![CI](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml/badge.svg)](https://github.com/yoavram-lab/VBPCApy/actions/workflows/ci.yml) [![PyPI](https://img.shields.io/pypi/v/vbpca-py)](https://pypi.org/project/vbpca-py/) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19389250.svg)](https://doi.org/10.5281/zenodo.19389250)

<!-- software-release:vbpca_py:start -->

Public beta release: [v0.4.12 on PyPI](https://pypi.org/project/vbpca-py/0.4.12/). Cite the [v0.4.12 archive](https://doi.org/10.5281/zenodo.23566480); the [concept DOI](https://doi.org/10.5281/zenodo.19389250) covers all archived versions.

<!-- software-release:vbpca_py:end -->

Variational Bayesian PCA for incomplete cultural, genetic, and survey data. The package fits observed entries under an explicit mask and exposes approximate variational-posterior covariance summaries; it does not model the missingness mechanism or by itself establish uncertainty calibration. It provides component pruning, model-selection tools, C++ kernels, and a scikit-learn-style estimator for fitting and training-data transforms. It was used in [Macdonald et al. (2024, _Evolutionary Human Sciences_)](https://doi.org/10.1017/ehs.2024.45). Current work focuses on testing, qualification, packaging, and maintenance.

## [op_engine](https://github.com/ACCIDDA/op_engine) · [![CI](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_engine/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_engine/)

<!-- software-release:op_engine:start -->

Public alpha release: [v0.8.0 on PyPI](https://pypi.org/project/op-engine/0.8.0/). [Citation metadata](https://github.com/ACCIDDA/op_engine/blob/v0.8.0/CITATION.cff).

<!-- software-release:op_engine:end -->

Framework-independent numerical core for structured-field, nonlocal, compartmental and stochastic reaction models across scientific domains. It provides explicit, implicit and stochastic methods, named observations and adaptive-schedule replay. Current applications include influenza scenario modeling and wildlife disease research. The [backend qualification matrix](https://accidda.github.io/op_engine/latest/guides/backend-qualification/) records which methods and derivatives have been tested; GPU execution needs separate hardware qualification. Use the core directly or through the separately packaged FlepiMoP2 provider.

## [op_system](https://github.com/ACCIDDA/op_system) · [![CI](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/op_system/actions/workflows/ci.yaml) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://accidda.github.io/op_system/)

<!-- software-release:op_system:start -->

Public alpha release: [v0.9.0 on PyPI](https://pypi.org/project/op-system/0.9.0/). [Citation metadata](https://github.com/ACCIDDA/op_system/blob/v0.9.0/CITATION.cff).

<!-- software-release:op_system:end -->

Domain-independent specification language and compiler for structured-field, nonlocal, compartmental and stochastic reaction models. Equations or transition models compile to numerical evaluators for NumPy, JAX and PyTorch, with reaction metadata, named observables and forcing schedules. Structural validation is complemented by independent-equation and conservation checks; [constraint metadata is not yet enforced](https://accidda.github.io/op_system/latest/guides/getting-started/#cross-axis-constraints-current-boundary).

## [trade-study](https://github.com/jcm-sci/trade-study) · [![CI](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml/badge.svg)](https://github.com/jcm-sci/trade-study/actions/workflows/ci.yml) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19599838.svg)](https://doi.org/10.5281/zenodo.19599838) [![Docs](https://img.shields.io/badge/docs-online-blue)](https://jcm-sci.github.io/trade-study/)

<!-- software-release:trade_study:start -->

Public alpha release: [v0.6.0 on PyPI](https://pypi.org/project/trade-study/0.6.0/). Cite the [v0.6.0 archive](https://doi.org/10.5281/zenodo.23497881); the [concept DOI](https://doi.org/10.5281/zenodo.19599838) covers all archived versions.

<!-- software-release:trade_study:end -->

Compares model settings, experiments, studies, and surveillance plans against competing objectives. It builds design grids, runs replicated studies in phases, compares designs with shared random numbers, and reports Pareto fronts, regret and practical equivalence under specified preferences. Optional integrations add scoring rules, sensitivity analysis, adaptive search, surrogate models and model weighting. Results retain replicate counts, uncertainty assumptions and provenance. Calibration, power and applicability to observed data need separate assessment.

[Documentation and executable examples](https://jcm-sci.github.io/trade-study/guide/capabilities/).

## [op_infer](https://github.com/ACCIDDA/op_infer)

<!-- software-release:inference_calibration:start -->

Public-source pre-alpha research software (development version 0.0.1); unreleased on PyPI. Cite a commit until a release exists.

<!-- software-release:inference_calibration:end -->

Connects Bayesian fitting through established inference libraries, simulation-based calibration and replicated study-design checks. The implementation uses the simulation and evaluation tools above. Broader interfaces and application studies remain in development; operational data, partner discussions, and application materials remain private. See the [project summary](https://jcmacdonald.dev/projects/inference_calibration/).

## [pp-eigentest](https://jcmacdonald.dev/projects/pp_eigentest/)

<!-- software-release:pp_eigentest:start -->

Private alpha research software; unreleased. A methods paper is in preparation.

<!-- software-release:pp_eigentest:end -->

Investigates how many latent dimensions an incomplete dataset can support, using posterior predictive eigenvalue testing and Bayesian latent-variable models. Current work studies rank decisions, uncertainty and calibration, building on the earlier methodology described in the [2024 preprint](https://arxiv.org/abs/2409.12129). The ongoing study is distinct from the released VBPCApy package.

# Other software contributions

## [flepimop2](https://github.com/ACCIDDA/flepimop2) · [![CI](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml/badge.svg)](https://github.com/ACCIDDA/flepimop2/actions/workflows/ci.yaml)

<!-- software-release:flepimop2:start -->

Public alpha release: [v0.3.0 on PyPI](https://pypi.org/project/flepimop2/0.3.0/). The [Zenodo concept record](https://doi.org/10.5281/zenodo.19672076) exists; a release-specific v0.3.0 archive has not yet been verified.

<!-- software-release:flepimop2:end -->

Configuration-driven orchestration engine for CDC-supported infectious disease forecasting and scenario analysis. Plugin architecture decouples model specification, numerical integration, and output persistence.

## [FlepiMoP](https://github.com/HopkinsIDD/flepiMoP)

Flexible Pipeline for Modeling Pathogens. Contributed profiling and [vectorized simulation-backend code](https://github.com/HopkinsIDD/flepiMoP/pull/592).

## [Flu Scenario Modeling Hub](https://github.com/midas-network/flu-scenario-modeling-hub)

MIDAS Network coordination hub for CDC-funded influenza scenario modeling. Lead model developer for ACCIDDA submissions, with contributions to model-evaluation infrastructure.

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
