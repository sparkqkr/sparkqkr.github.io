---
title: "Tensor Landmark Analysis"
authors: "Sung Hee Park, Ruiwen Zhou, Xin Zhang, Liang Li, Lei Liu"
venue: "Stat (Wiley) — Original Article"
year: 2024
links:
  pdf: /assets/papers/tlm/TLM_STAT.pdf
  doi: https://onlinelibrary.wiley.com/doi/10.1002/sta4.70014
  code: https://github.com/sparkqkr/TensorCoxReg
abstract: >
  We introduce a Tensor Landmark Model (TLM) for dynamic survival prediction using
  longitudinal biomarkers arranged as tensor covariates. The model uses low‑rank
  CP decomposition to reduce dimensionality, with parameters estimated via an
  iteratively reweighted least squares (IRLS) block‑relaxation algorithm. Simulations
  and ADNI data show accurate recovery of survival coefficients and improved
  prediction versus vectorized landmark models.
layout: paper
toc: true
---

## Overview

This page accompanies the paper **Tensor Landmark Analysis** and provides a
short, accessible summary, figures, and links to the full PDF and code.

**What problem is addressed?**  
Dynamic risk prediction after a landmark time \(s\) when the predictors are
longitudinal and structured (e.g., stacked visits × biomarkers) is hard for
vectorized models. We keep the structure by modeling a tensor covariate
\(X_i(s)\) with a low‑rank CP factorization for the coefficient tensor \(B(s)\).

**Model (matrix case for clarity).**
For landmark time \(s\), the hazard is
\[
\lambda_i(t \mid s) = \lambda_0(t \mid s)\,
\exp \{ \eta^\top z_i + \langle B(s),\, X_i(s) \rangle \},
\]
with \(B(s) = \sum_{r=1}^R \sigma_r(s)\, b_{1r}(s) \circ b_{2r}(s)\).
Low rank \(R\) yields strong parsimony and preserves temporal structure.

**Estimation.**
We use an IRLS block‑relaxation procedure that alternates updates of
\(\{b_{1r}, b_{2r}, \sigma_r, \eta\}\) and Breslow baseline increments; rank is
chosen via right‑censored AIC/BIC.

---

## Figures

> Replace the file names if yours differ. Images can be PNG/JPG/PDF.

**Figure 1 — Workflow of TLM.**  
![Workflow](/assets/papers/tlm/fig1_workflow.png)

**Figure 2 — Estimated coefficients across ranks/patterns.**  
![Results](/assets/papers/tlm/fig2_results.png)

**Table 1 — Simulation settings (example as image or HTML table).**  
![Table 1](/assets/papers/tlm/table1_settings.png)

<!-- Optionally, make a live table in Markdown:
| n | p1 | p2 | Rank R | Censoring |
|--:|---:|---:|:------:|:---------:|
| 300 | 8 | 9 | 2 | ~50% |
-->

---

## PDF

- 📄 **Full paper (PDF):** [Download](/assets/papers/tlm/TLM_STAT.pdf)  
- 🔗 **Publisher page / DOI:** <https://onlinelibrary.wiley.com/doi/10.1002/sta4.70014>

To embed the PDF inline instead of a download link:

```html
<iframe src="/assets/papers/tlm/TLM_STAT.pdf" width="100%" height="900" style="border:0;"></iframe>
