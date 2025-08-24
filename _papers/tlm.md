---
title: "Tensor Landmark Analysis"
authors: "Sung Hee Park, Ruiwen Zhou, Xin Zhang, Liang Li, Lei Liu"
venue: "Stat (Wiley) — Original Article"
year: 2024
links:
  pdf: /assets/papers/tlm/TLM_STAT.pdf
  doi: https://onlinelibrary.wiley.com/doi/10.1002/sta4.70014
  code:
abstract: >
  We introduce a Tensor Landmark Model (TLM) for dynamic survival prediction
  using longitudinal biomarkers arranged as tensor covariates. The model uses a
  low-rank CP decomposition for the coefficient tensor and estimation via an
  IRLS block-relaxation algorithm. Simulations and ADNI data show improved
  prediction over vectorized landmark models while preserving structure.
---

## Overview

This page summarizes the paper and hosts figures and the PDF.

- **Goal.** Dynamic risk prediction at a landmark time \(s\) using structured longitudinal covariates.
- **Model.** Hazard \(\lambda_i(t\mid s)=\lambda_0(t\mid s)\exp\{\eta^\top z_i + \langle B(s), X_i(s)\rangle\}\), with a low-rank CP factorization for \(B(s)\).
- **Estimation.** IRLS block-relaxation alternating updates of factor matrices and baseline increments; rank selected via AIC/BIC.

## Figures

**Figure 1 — Workflow of TLM.**  
![Workflow](/assets/papers/tlm/fig1_workflow.png)

**Figure 2 — Estimated coefficients / results.**  
![Results](/assets/papers/tlm/fig2_results.png)

## PDF

- 📄 **Full paper (PDF):** [Download](/assets/papers/tlm/TLM_STAT.pdf)  
- 🔗 **Publisher page (DOI):** <https://onlinelibrary.wiley.com/doi/10.1002/sta4.70014>

<!-- Or embed the PDF inline:
<iframe src="/assets/papers/tlm/TLM_STAT.pdf" width="100%" height="900" style="border:0;"></iframe>
-->

## Why it matters

- Preserves visit × biomarker structure (no lossy vectorization).
- Parsimonious low-rank CP representation reduces parameters dramatically.
- Improves prediction accuracy (e.g., C-index) on ADNI compared with baselines.
