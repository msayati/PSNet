# PSNet: Knowledge Graph–Based Phosphatase–Substrate Association Prediction

PSNet is a computational framework for predicting phosphatase–substrate associations at the phosphosite level using a heterogeneous biological knowledge graph and network embedding–based machine learning.

---

## Overview

Protein phosphorylation and dephosphorylation are essential regulatory mechanisms in cellular signaling. While kinase–substrate associations have been widely studied, phosphatase–substrate relationships remain poorly characterized. PSNet addresses this gap by integrating heterogeneous biological data into a unified knowledge graph and leveraging network embeddings for prediction.

---

## Methodology

The PSNet framework consists of five main steps: data collection, data cleaning, knowledge graph construction, node embedding, and prediction modeling.

![PSNet Workflow](Figure1.jpg)

**Figure 1.**  
(a) Workflow of the PSNet framework, illustrating data collection, preprocessing, heterogeneous knowledge graph construction, vector representation learning, and prediction modeling.  
(b) Schematic representation of the heterogeneous knowledge graph, showing node types (phosphatases, kinases, substrates, phosphosites, pathways, drugs, and diseases) and their relationships.

---

### 1. Data Collection

Data are collected from multiple curated biological databases:
- DEPOD (2019): phosphatase–ph
