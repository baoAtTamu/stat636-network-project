Social Networks: Community Detection & Modularity

This project explores **community structure** and **modularity** in real-world social networks using methods from **STAT 636 – Multivariate Analysis and Statistical Learning for Network Data**.

## Project Proposal

[Project Proposal Document](https://docs.google.com/document/d/1YJMrrdy3Ut8AaVXE0JwHxjFi-LMXUui_/edit)

---

# Facebook Ego Network Project – Team Task Checklist (R Implementation)

This checklist organizes the full workflow for your STAT 636 project on **Community Detection and Modularity in Facebook Ego Networks (with SBM extension)**.

---

## Project Setup
- [ ] **Create GitHub repo and folder structure**
  - `/data`, `/scripts`, `/outputs/plots`, `/outputs/tables`, `/report`, `/notebooks`
- [ ] **Set up R environment**
  - Use `renv` or `pak` to manage dependencies (`igraph`, `sbm`, `blockmodels`, `ggplot2`, `ggraph`, `Matrix`, `RSpectra`)
- [ ] **Define coding conventions and random seeds** for reproducibility
- [ ] **Add dataset**
  - Download `facebook_combined.txt` to `/data/raw`
  - Include README with source and schema

---

## Data Preparation
- [ ] **Load and clean graph** (A)
  - Import edge list → `igraph` object
  - Simplify graph: remove self-loops and duplicates
- [ ] **Check components and graph info**
  - Keep the largest connected component
  - Confirm node/edge counts (n≈4039, m≈88234)

---

## Exploratory Analysis
- [ ] **Descriptive statistics** (B)
  - Compute: density, degree distribution, clustering coefficients, path length, diameter
  - Export results to `/outputs/tables`
- [ ] **Centrality measures** (B)
  - Degree, betweenness, closeness, eigenvector
  - Save top-10 nodes for each metric

---

## Community Detection
- [ ] **Louvain clustering** (B)
  - Compute modularity Q and community sizes
  - Export table of results
- [ ] **Spectral clustering** (B)
  - Build Laplacian L, compute eigenvectors, run k-means
  - Compare modularity and community count

---

## Random Graph Baselines
- [ ] **Generate synthetic models** (A)
  - Erdős–Rényi (ER), Barabási–Albert (BA), Chung–Lu (CL)
- [ ] **Compute metrics for baselines** (B)
  - Clustering, modularity, path length, diameter
  - Save comparison table `/outputs/tables/baseline_metrics.csv`

---

## SBM Analysis
- [ ] **Hard-label SBM estimation** (B)
  - Use Louvain or Spectral labels (`ẑ`)
  - Estimate block matrix `B̂` and plot heatmap
- [ ] **Model-based SBM estimation** (B)
  - Fit `sbm` or `blockmodels` (Bernoulli) model
  - Record log-likelihood, ICL/BIC, estimated K
- [ ] **SBM simulation** (A)
  - Simulate networks using estimated `B̂` or package fit
  - Compute clustering, modularity, and compare with real graph

---

## Visualization (C)
- [ ] Force-directed plot (clusters colored)
- [ ] Degree histograms (linear + log–log)
- [ ] Spectral 2D embedding scatterplot (color = cluster)
- [ ] Heatmap of `B̂`
- [ ] Bar chart: modularity & clustering comparison across Real / ER / BA / CL / SBM

---

## Results Consolidation (C)
- [ ] Merge metrics and plots into `/report/assets`
- [ ] Build summary tables for modularity, clustering, degree, and model fit

---

## Reporting (C)
- [ ] Write and knit R Markdown report:
  - **Sections:** Introduction → Methods → Results → Discussion → Limitations
  - Knit to PDF in `/report`
- [ ] Prepare final presentation deck (slides with visuals and key findings)

---

## Quality Control (All)
- [ ] Run full pipeline (A → B → C)
- [ ] Reproduce results with fixed seed
- [ ] Update README with step-by-step run guide
- [ ] Ensure outputs regenerate cleanly

---

---

**Legend:**  
A – Data Engineer & Simulation Lead  
B – Statistician & Model Analyst  
C – Visualization & Report Lead
