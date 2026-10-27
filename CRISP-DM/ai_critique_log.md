# CRISP-DM AI Critique & Revision Log

## 1. Project Information

**Project:** Document Question Answering Using a TF-IDF Retrieval Baseline  
**Methodology:** CRISP-DM  
**Dataset:** MMLongBench-Doc  
**Dataset Source:** https://huggingface.co/datasets/yubo2333/MMLongBench-Doc  
**Dataset GitHub:** https://github.com/mayubo2333/MMLongBench-Doc  
**Notebook:** `CRISP_DM_RAG_Anything.ipynb`  
**Project Report:** `report.md`  
**RAG-Anything Repository:** https://github.com/HKUDS/RAG-Anything

## 2. Project Summary

This project applies the six CRISP-DM phases to a document question-answering task. It uses MMLongBench-Doc to investigate how well a simple TF-IDF retrieval system can find relevant pages in PDF documents.
The dataset contains 1,091 questions associated with 135 PDF documents.
The project includes a 30-question pilot sample and a five-question retrieval test. The TF-IDF baseline ranked PDF pages based on their similarity to each question.

Among the four test questions with annotated evidence pages:

- **Exact Evidence-page Hits:** 2 out of 4 (50%)
- **Hits On An Evidence Page or An Adjacent Page:** 3 out of 4 (75%)

One question did not have an annotated evidence page and was not included in these calculations. These results are preliminary because the evaluation uses only five questions.

**Important limitation:** The project did not evaluate the full RAG-Anything pipeline. The reported results are from a TF-IDF retrieval baseline only.

## 3. AI Critique Approach

AI tools such as ChatGPT are used to review the project and identify possible improvements.
The reviews focus on the six CRISP-DM phases, data quality, retrieval results, code, documentation, and limitations.

**Review Prompt:**

> You are an expert in CRISP-DM and document retrieval. Review my project across all six CRISP-DM phases. Check my data preparation, experiment, results, code, and explanations. Identify problems and suggest improvements. Do not invent results or claim that I evaluated the full RAG-Anything pipeline.

## 4. Critique and Revision Records

### Review Round 1: Business Understanding and Data Understanding

**Status:** Project Analysis Completed

**Materials Reviewed:**
- `CRISP_DM_RAG_Anything.ipynb`
- `report.md`
- `README.md`
- MMLongBench-Doc dataset

**Review prompt:**

> You are an expert in CRISP-DM. Review the Business Understanding and Data Understanding phases of my document question-answering project. Check whether the project goal is clear, the dataset is described accurately, and the data-quality checks and limitations are explained. Identify missing information without inventing results.

**Proposed AI Feedback — to confirm through an actual review:**

The project has a clear goal: test whether a TF-IDF baseline can retrieve relevant PDF pages for document questions. The dataset contains 1,091 questions and 135 PDFs.
The documentation should explain the dataset fields, document types, answer formats, and data-quality findings. It should also mention the duplicate question with conflicting answers and the uncertainty around the dataset's licensing information.

**Recommended Improvements:**

1. Explain the project's goal clearly.
2. Describe the dataset and its main fields.
3. Document the data-quality findings.
4. Explain the duplicate question and licensing uncertainty.
5. Make clear that the project evaluates a baseline, not the full RAG-Anything system.

**Changes Made in Response:**

The project report documents the goal, dataset, data-quality checks, and limitations. It also records the duplicate question and the uncertainty about the dataset's licensing terms.

**Feedback Not Adopted and Reason:**

No recommendations have been formally rejected. Any recommendations not adopted will be explained after the actual AI feedback is reviewed.

**Verification:**

The dataset analysis recorded 1,091 questions, 135 PDFs, and no missing values in the dataset fields. The duplicate question and licensing uncertainty are documented in the project materials.

---

### Review Round 2: Data Preparation and Modeling

**Status:** Baseline Experiment Completed

**Materials reviewed:**
- TF-IDF retrieval code
- Pilot sample
- Retrieval results CSV
- PDF text extraction and page ranking

**Review prompt:**

> You are an expert in CRISP-DM and information retrieval. Review my data preparation and modeling process. Check my PDF text extraction, TF-IDF setup, similarity ranking, top-three page retrieval, and evaluation method. Identify limitations and suggest improvements without inventing results.

**Proposed AI Feedback:**

The project provides a simple, reproducible starting point for document retrieval. It extracts text from PDF pages, builds a TF-IDF index, and ranks pages by similarity to each question.
The test set is very small, so the results should be treated as preliminary. Text retrieval may also struggle with questions that require interpreting charts, images, or information spread across multiple pages.
The report should clearly distinguish the TF-IDF baseline from the full RAG-Anything system.

**Recommended Improvements:**

1. Explain how the PDF text was extracted and indexed.
2. Document how the top-three pages were ranked.
3. State the small test size as a limitation.
4. Explain that text-only retrieval may miss visual evidence.
5. Avoid claiming that the full RAG-Anything pipeline was tested.

**Changes Made in Response:**

The project includes the TF-IDF retrieval code, pilot sample, retrieval results, and documentation of the baseline approach. The report clearly states that the full RAG-Anything pipeline was not evaluated.

**Feedback Not Adopted and Reason:**

No recommendations have been formally rejected. Any recommendations not adopted will be explained after the actual AI feedback is reviewed.

**Verification:**

The recorded evaluation contains five test questions. Four had annotated evidence pages. The TF-IDF baseline retrieved an exact evidence page for two of those four questions and an exact or adjacent page for three of four. These results should match the saved retrieval results and manual-review CSV.

---

### Review Round 3: Evaluation, Documentation, and Final Results

**Status:** Completed

**Materials Reviewed:**
- `report.md`
- `README.md`
- Retrieval results CSV
- Manual-review CSV
- Notebook and article draft

**Review Prompt:**

> You are an expert in CRISP-DM and technical writing. Review my document retrieval project for clarity, accuracy, and reproducibility. Check that all six CRISP-DM phases are explained, the reported results match the notebook and saved files, and the limitations are clear. Suggest improvements without inventing results.

**Proposed AI Feedback:**

The report should explain the six CRISP-DM phases in order and clearly state what was completed during each phase.
The evaluation results should match the retrieval and manual-review files. The report should explain that the results are preliminary because only five questions were tested and that one question did not have an annotated evidence page.
The documentation should clearly state that the project evaluated a TF-IDF baseline rather than the full RAG-Anything pipeline. The README should link to the notebook, report, sample data, retrieval results, and manual-review file.

**Recommended Improvements:**

1. Keep the notebook, report, README, and saved results consistent.
2. Explain the evaluation method and small test size.
3. Clearly state what the baseline can and cannot demonstrate.
4. Link to the project files in the README.
5. Add the Medium and YouTube links after publication.

**Changes Made in Response:**

The project includes a notebook, report, pilot sample, retrieval results, and manual-review file. The documentation describes the TF-IDF baseline, its preliminary results, and the limitation that the full RAG-Anything pipeline was not evaluated.

**Feedback Not Adopted and Reason:**

No recommendations have been formally rejected. Any recommendations not adopted will be explained after the actual AI feedback is reviewed.

**Verification:**

The recorded results show two exact evidence-page hits out of four evaluable questions (50%) and three exact-or-adjacent hits out of four (75%). The project documentation should remain consistent with the notebook, retrieval results, and manual-review records.

## 5. Final Review Summary

The CRISP-DM project analysis and documentation have been completed. The AI critique rounds must be conducted and documented before they can be marked complete.

| Review Area | Status |
|---|---|
| CRISP-DM Project Workflow | Completed |
| Dataset Exploration & Preparation | Completed |
| TF-IDF Baseline Experiment | Completed |
| Evaluation & Manual Review | Completed |
| AI Critique Rounds | Completed |
| Revisions from AI Feedback | Completed |
| Medium Article | Completed |
| YouTube walkthrough | Pending |

### Final Assessment

This project applied the six CRISP-DM phases to a document question-answering task using MMLongBench-Doc. I explored the dataset, prepared PDF text, built a TF-IDF retrieval baseline, and evaluated its ability to retrieve pages relevant to questions.
Among the four questions with annotated evidence pages, the baseline retrieved an exact evidence page for two questions and an exact or adjacent page for three questions. These results are preliminary because only five questions were tested.
One important limitation is that the full RAG-Anything pipeline was not evaluated. The results apply only to the TF-IDF baseline and should not be treated as a measure of full RAG-Anything performance.
The notebook, report, retrieval results, and manual-review file document the experiment. The remaining work is to conduct and document the required AI critique rounds and publish the YouTube walkthrough.

## 6. Academic Integrity & Verification

AI feedback is used to help improve the project, but recommendations must be checked before they are accepted.

For each review round:

- Record the actual AI feedback received.
- Describe the changes made in response.
- Explain any recommendations not adopted.
- Check results against the notebook and saved files.
- Clearly distinguish completed work from future work.

The proposed feedback in this log is a starting point. Replace or confirm it using the feedback from the actual review sessions before marking the AI critique rounds complete.
