PSNet: Knowledge Graph–Based Phosphatase–Substrate Association Prediction

PSNet is a computational framework for predicting phosphatase–substrate associations at the phosphosite level using a heterogeneous biological knowledge graph and network embedding–based machine learning.

This repository contains the data preprocessing pipeline, knowledge graph construction, embedding generation, and prediction experiments described in the associated manuscript.

Overview

Protein phosphorylation and dephosphorylation are central regulatory mechanisms in cellular signaling. While kinase–substrate associations have been extensively studied, phosphatase–substrate relationships remain poorly characterized. PSNet addresses this gap by integrating heterogeneous biological data into a unified knowledge graph and leveraging network embeddings to predict candidate phosphatases for a given phosphosite.

Methodology

The PSNet framework consists of five main steps: data collection, data cleaning, knowledge graph construction, node embedding, and prediction modeling.

<p align="center"> <img src="Figure1.jpg" width="800"> </p>

Figure 1. (a) Workflow of the PSNet framework, illustrating data collection, preprocessing, heterogeneous knowledge graph construction, vector representation learning, and prediction modeling. (b) Schematic representation of the heterogeneous knowledge graph, showing node types (phosphatases, kinases, substrates, phosphosites, pathways, drugs, and diseases) and their relationships.

1. Data Collection

Data are collected from multiple curated biological databases, including:

DEPOD (2019): experimentally validated phosphatase–phosphosite associations

PhosphoSitePlus: kinase–substrate and phosphosite annotations

STRING: protein–protein interactions

MSigDB: pathway–gene associations

DrugMap (2023): gene–drug and gene–disease associations

UniProt: identifier mapping

2. Data Cleaning

All datasets are standardized and filtered to:

Remove missing or ambiguous identifiers

Harmonize gene and protein naming conventions

Remove isolated nodes with no interactions

3. Heterogeneous Knowledge Graph Construction

A heterogeneous knowledge graph is constructed where:

Nodes represent phosphatases, kinases, substrates (proteins), phosphosites, pathways, drugs, and diseases

Edges represent biological relationships among these entities

Phosphatase–substrate relationships are modeled at the phosphosite level, connecting phosphatases to specific dephosphorylation sites.

4. Vector Representation (Node Embedding)

Low-dimensional node embeddings are learned from the graph using multiple network embedding algorithms:

Node2Vec

Word2Vec

NetMF

DNGR

Before embedding computation, experimentally validated phosphatase–phosphosite edges from DEPOD are removed to prevent information leakage.

5. Prediction Modeling

The learned embeddings are used as features in supervised machine learning models:

Logistic Regression

Random Forest

Naïve Bayes

Support Vector Machine

K-Nearest Neighbors

.
├── Preprocessing.ipynb      # Data cleaning and integration
├── Knowledge_Graph.ipynb    # Knowledge graph construction
├── P_S.ipynb                # Phosphatase–phosphosite prediction experiments
├── LOOCV.ipynb              # Leave-one-out cross-validation analysis
├── Figure1.jpg              # Framework and knowledge graph illustration
└── README.md                # Project documentation

Notebooks Description

Preprocessing.ipynb
Data loading, cleaning, identifier mapping, and filtering steps.

Knowledge_Graph.ipynb
Construction of the heterogeneous knowledge graph from integrated data sources.

P_S.ipynb
Training and evaluation of prediction models for phosphatase–phosphosite associations.

LOOCV.ipynb
Leave-one-out cross-validation and phosphatase prioritization analysis.

Key Features

Predicts candidate phosphatases for a given phosphosite

Covers ~250 human phosphatases

Integrates multi-relational biological context

Robust to embedding method choice

Designed for experimental prioritization

Models are evaluated using stratified cross-validation and prioritization-based metrics (e.g., AUC, Top-k accuracy).

Repository Structure
