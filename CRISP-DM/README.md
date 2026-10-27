# CRISP-DM Project

## Project Title
**Evaluating Document Retrieval for Question Answering Using MMLongBench-Doc**

## Project Overview
This project applies the Cross-Industry Standard Process for Data Mining (CRISP-DM) to investigate document retrieval for question answering. The project uses MMLongBench-Doc and evaluates a lightweight TF-IDF retrieval baseline as an initial experiment.

The work follows all six CRISP-DM phases: Business Understanding, Data Understanding, Data Preparation, Modeling, Evaluation, and Deployment.

## Research Question
Can we group customers into useful clusters using their income and spending score?

## Dataset
[MMLongBench-Doc — Hugging Face](https://huggingface.co/datasets/yubo2333/MMLongBench-Doc)

Additional resources:
- [MMLongBench-Doc research paper](https://arxiv.org/abs/2407.01523)
- [MMLongBench-Doc project website](https://mayubo2333.github.io/MMLongBench-Doc/)
- [RAG-Anything GitHub repository](https://github.com/HKUDS/RAG-Anything)

The loaded dataset contained 1,091 question records across seven fields. The associated document collection contained 135 PDFs.

## Methodology

1. **Business Understanding:** Define the document retrieval problem and research question.
2. **Data Understanding:** Inspect dataset structure, document types, answer formats, missing values, and potential annotation inconsistencies.
3. **Data Preparation:** Select pilot questions, obtain relevant PDFs, extract page-level text, and prepare text for retrieval.
4. **Modeling:** Implement TF-IDF vectorization and cosine-similarity ranking to retrieve the three highest-ranked pages for each question.
5. **Evaluation:** Manually inspect retrieved pages and compare retrieval results with annotated evidence pages.
6. **Deployment:** Organize the notebook, report, result files, and review documentation for reproducibility and project delivery.

## Experiment and Results

The TF-IDF baseline was evaluated on a five-question pilot sample.

Among the four questions with annotated evidence pages:
- **Exact Evidence-page Hits:** 2 out of 4 (50%).
- **Adjacent-page Hits:** 3 out of 4 (75%) under the project's current evaluation procedure.

Manual review found that the monitor-manual question retrieved a passage directly supporting the reference answer. Other cases showed that retrieving the correct PDF doesn't entirely mean the displayed excerpt contains enough evidence to answer the question.

These results are only early findings. The page‑numbering rules must me fixed and confirmed before treating the hit rates as final.

**Important:** The complete RAG-Anything pipeline was not evaluated. These results describe the TF-IDF baseline only and must not be interpreted as performance results for RAG-Anything.

## Project Files

- [Google Colab Notebook — CRISP_DM_RAG_Anything.ipynb](https://colab.research.google.com/drive/1OxZDkhAXqWdKvOs6o34aEoFOU8Zze4r0)
- [`report.md`](./report.md) — Detailed report covering the CRISP-DM phases.
- `CRISP-DM Medium Article.pdf` — Written article draft.
- `crisp_dm_pilot_sample.csv` — Selected pilot sample.
- `crisp_dm_tfidf_retrieval_results.csv` — TF-IDF retrieval results.
- `crisp_dm_phase5_manual_review.csv` — Manual-review records; ensure this is the completed version, not the original blank template.

## AI Critique and Revision

The assignment requires multiple rounds of AI critique and revision. The project should document the actual feedback, revisions, and manual verification performed.

- Critique log: add a link to `ai_critique_log.md` once the file contains the completed review records.
- Review documentation should identify the section reviewed, feedback received, changes made, and remaining limitations.

## Limitations

- The evaluation covers only five questions and is too small to establish general retrieval performance.
- TF-IDF relies on lexical similarity and may miss semantically relevant evidence.
- Text extraction may lose visual or structural information from charts and tables.
- Some dataset annotations may be ambiguous or inconsistent.
- Evidence-page numbering needs further verification.
- The full RAG-Anything pipeline was not evaluated or deployed.

## Publication Deliverables

- **Medium Article:** https://medium.com/@olhunter03/crisp-dm-medium-article-38409762ee81
- **YouTube Walkthrough:** Pending

## Conclusion

The project demonstrates a structured application of CRISP-DM to a document retrieval problem. The TF-IDF baseline provides a reproducible starting point, while manual review identifies areas for further improvement. Future work should expand the evaluation set, standardize page numbering, and compare the baseline with a properly configured RAG-Anything pipeline.
