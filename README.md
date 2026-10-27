# CMPE 255 — Data Mining Process Assignment

## Project Overview

This repository contains my CMPE 255 Data Mining Process assignment. The goal is to apply three established data mining methodologies to separate datasets, document each phase, evaluate the results, and present the findings.

The Three Methodologies Are:

1. **CRISP-DM** — Cross-Industry Standard Process for Data Mining
2. **SEMMA** — Sample, Explore, Modify, Model, Assess
3. **KDD** — Knowledge Discovery in Databases

Each project will include a Google Colab notebook, methodology-specific analysis, evaluation results, documentation, and AI-assisted critique and revision records.

## Project Structure

| Folder | Description |
|---|---|
| `CRISP-DM/` | Document retrieval and question-answering evaluation using MMLongBench-Doc |
| `SEMMA/` | A separate data mining project following the SEMMA methodology |
| `KDD/` | A separate data mining project following the KDD methodology |

## Project 1: CRISP-DM

**Topic:** Evaluating document retrieval for question answering using MMLongBench-Doc.

**Dataset:** [MMLongBench-Doc on Hugging Face](https://huggingface.co/datasets/yubo2333/MMLongBench-Doc)

**Original Objective:** Evaluate the RAG-Anything multimodal retrieval-augmented generation framework for document question answering.

**Current Experiment:** A TF-IDF document retrieval baseline has been implemented and evaluated on five questions. The full RAG-Anything pipeline has not yet been evaluated.

**Methodology Phases:**
- Business Understanding
- Data Understanding
- Data Preparation
- Modeling
- Evaluation
- Deployment

See the CRISP-DM folder for the notebook, report, PDF article, and supporting experiment files.

## Project 2: SEMMA

This project will use a dataset different from those used in the other two projects.

The analysis will follow the five SEMMA stages:
- Sample
- Explore
- Modify
- Model
- Assess

See the SEMMA folder for the notebook, report, PDF article, and supporting project files.

## Project 3: KDD

Topic: Mall customer segmentation using K-means clustering.

Dataset: Mall Customer Segmentation Data on Kaggle

Objective: Identify customer groups based on annual income and spending score.

Results: The final model used five clusters and achieved a silhouette score of 0.555 across 200 customer records. The cluster profiles and visualization show groups with different income and spending patterns.

Methodology stages:

- Selection

- Preprocessing

- Transformation

- Data Mining

- Interpretation and Evaluation

See the KDD folder for the notebook, report, PDF article, clustered CSV, and supporting project files.

AI-Assisted Critique and Revision

The assignment requires multiple rounds of AI critique and revision for each methodology. The project-specific critique records should document:

- The section or phase reviewed

- Critique feedback

- Changes made in response

- Manual code and result verification

- Remaining limitations after revision

The critique process should be documented using the actual reviews and revisions performed, rather than assumed or reconstructed as completed.

Reproducibility

The project notebooks document the data sources, preprocessing, analysis, model configuration, evaluation methods, results, and limitations. Supporting files are included where appropriate.

Results should be interpreted within each project's scope and limitations. In particular, the CRISP-DM project evaluates a TF-IDF retrieval baseline rather than the full RAG-Anything pipeline.

Final Deliverables

Project Artifacts

- Three methodology-specific notebooks

- Three project reports

- Three PDF article drafts

- Dataset source links and relevant supporting files

- Experiment outputs and evaluation results

Publication Deliverables

- CRISP-DM Medium article and YouTube walkthrough

- SEMMA Medium article and YouTube walkthrough

- KDD Medium article and YouTube walkthrough

Publication links should be added here and to the corresponding project README files once the articles and videos are published.

Review Documentation

- AI critique-and-revision records for CRISP-DM

- AI critique-and-revision records for SEMMA

- AI critique-and-revision records for KDD
