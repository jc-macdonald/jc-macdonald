# **Structure-aware data science and scientific inference for environmental and public health systems.**


Hi, I’m Josh.  

I design and implement computational inference systems that integrate mechanistic structure with sparse, heterogeneous data. My work focuses on building **diagnostic-first, reduced-order modeling pipelines**—from numerical solvers to forecasting and scenario evaluation—that remain interpretable, stable, and decision-relevant under real-world constraints.

Applications include infectious disease dynamics, environmental and ecological systems, and human–environment interactions, with an emphasis on reproducibility, numerical discipline, and operational reliability.

---

# Core Skills

## Structured Mathematical & Statistical Modeling  
Develop and analyze mechanistic and hybrid models using nonlinear ODEs, PDEs, and structured stochastic systems. Emphasis on identifying **diagnostically meaningful summaries**, stability properties, and regime behavior rather than full latent-state reconstruction. Apply simulation-based inference, identifiability diagnostics, and global sensitivity analysis (Sobol, PRCC, Morris).

## Bayesian Inference & Identifiability  
Design inference targets and likelihood structures aligned with partial observability. Use hierarchical Bayesian models, profile likelihood, posterior predictive checks, and simulation-based identifiability analysis to support robust parameter estimation and uncertainty quantification.

## Scientific Computing & Inference Pipelines  
Build high-performance, reproducible scientific computing systems in Python, integrating mechanistic simulators with inference and forecasting workflows. Experience includes solver benchmarking, vectorization, scalable scenario generation, and disciplined software engineering practices (testing, CI, modular design). Working knowledge of Julia for ODE/PDE simulation.

## Forecasting, Scenarios, and Evaluation  
Develop reduced-order forecasting and scenario models that enforce scientific constraints by construction. Design evaluation and grading tools that diagnose drift, instability, and structural incoherence beyond accuracy-based metrics, informed by operational public health forecasting experience.

## Collaboration & Communication  
Collaborate across public health, ecology, environmental science, and the social sciences. Communicate results through technical manuscripts, stakeholder-facing briefs, and interdisciplinary presentations, with a focus on interpretability and decision relevance.

---

# Selected Projects

## FlepiMoP Backend Upgrade (Current)  
Leading a major [refactor and vectorization](https://github.com/HopkinsIDD/flepiMoP/pull/592) of the [FlepiMoP](https://www.flepimop.org) solver, inference, and scenario-generation backend. Work includes redesigning internal representations to improve numerical stability and scalability. Current results deliver **5×–20× speedups** depending on model structure and enable integrated scenario workflows, with forecasting deployment underway.

## Influenza Scenario & Forecast Modeling (CDC Flu Hub, Current)  
Lead modeler for Johns Hopkins/ACCIDDA’s CDC-funded seasonal influenza scenario modeling efforts (2024–2025), and incoming lead for 2025–2026 forecasting. Ran nationwide simulations using FlepiMoP with hierarchical Bayesian calibration across U.S. states. This work informs real-time public health decision-making under deep uncertainty.

## Cultural Evolution and Human–Environment Systems  
Applied Bayesian PCA, structured distance representations, and network diagnostics to identify dominant transmission pathways in high-dimensional cultural datasets. Focused on inference under severe observational constraint without reconstructing latent histories.  
(See: Macdonald et al., [2024](https://doi.org/10.48550/arXiv.2409.12129))

## Within-Host Viral Dynamics and Spillover Risk (FMDV)  
Developed and fit mechanistic viral–immune models to experimental infection data in African buffalo to infer transmission-relevant diagnostics. Applied profile likelihood and simulation-based identifiability analysis to quantify uncertainty under partial observability.  
(See: Macdonald et al., [2024](https://doi.org/10.1086/730703))

## Trait-Structured NPZD Ecosystem Modeling  
Extended classical NPZD models to incorporate toxicity-mediated feedbacks and non-trophic interactions. Performed bifurcation and resilience analyses to identify regime shifts and persistence margins relevant to ecosystem monitoring and exposure pathways.  
(See: Macdonald & Gulbudak, [2023](https://doi.org/10.1007/s00285-023-01969-7))

## COVID-19 Outbreak Dynamics  
Modeled behaviorally mediated COVID-19 transmission under testing-dependent ascertainment and intervention fatigue, highlighting structural sources of forecast instability.  
(See: Macdonald et al., [2021](https://doi.org/10.1098/rsos.210227))

---

# Reproducible Software & Data Products

- **Influenza Scenario Modeling with FlepiMoP**  
  [ACCIDDA-JHU Seasonal Flu Model](https://github.com/midas-network/flu-scenario-modeling-hub)

- **FMDV Viral–Immune Dynamics Toolkit**  
  [Zenodo: FMDV Transmission Model Software](https://zenodo.org/records/10720079)

- **Cultural Network Analysis Tools**  
  [Zenodo: Austronesian Cultural Transmission Analysis](https://zenodo.org/records/13798914)
