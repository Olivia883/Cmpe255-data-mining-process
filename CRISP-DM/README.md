# CRISP-DM Project

## Project Title
Evaluating Document Retrieval for Question Answering Using MMLongBench-Doc

## Objective
Investigate document retrieval for question answering using the MMLongBench-Doc dataset, with an initial focus on a TF-IDF retrieval baseline and a proposed evaluation of RAG-Anything.

## Dataset
[MMLongBench-Doc — Hugging Face](https://huggingface.co/datasets/yubo2333/MMLongBench-Doc)

## Methodology
1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment

## Current Status
The TF-IDF baseline has been implemented and evaluated on five questions. Manual evidence review and documentation are in progress. The full RAG-Anything pipeline has not yet been evaluated.

## Planned Files
- `CRISP_DM_RAG_Anything.ipynb` — Google Colab notebook
- `report.md` — Project report
- `results/` — Experiment results and review files
- `critique-revisions/` — Documented AI critiques and revisions
- `README.md` — Project overview

## Limitations
The current experiment evaluates TF-IDF retrieval, not the full RAG-Anything pipeline. Results from the baseline should not be interpreted as results for RAG-Anything.
