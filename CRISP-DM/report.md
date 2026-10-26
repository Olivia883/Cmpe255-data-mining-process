# CRISP-DM Project Report

## Project Title
**Evaluating Document Retrieval for Question Answering Using MMLongBench-Doc**

## 1. Business Understanding

### 1.1 Problem Statement
Long documents such as research papers, financial reports, and technical manuals can contain information needed to answer detailed questions. Finding the correct information can be time-consuming, especially when the answer depends on a particular page, chart, or table.

This project investigates document retrieval for question answering using MMLongBench-Doc. The original objective was to evaluate the RAG-Anything multimodal retrieval-augmented generation framework. A TF-IDF retrieval baseline was implemented first to establish an initial comparison point.

### 1.2 Project Objectives
- Examine the MMLongBench-Doc dataset.
- Prepare a small, reproducible set of questions for an initial experiment.
- Build a TF-IDF document-page retrieval baseline.
- Evaluate retrieval using annotated evidence pages and manual inspection.
- Document limitations and identify next steps for a full RAG-Anything evaluation.

### 1.3 Success Criteria
The baseline is evaluated using whether the retrieved pages match the dataset's annotated evidence pages, whether adjacent pages are retrieved, and whether the displayed text excerpts contain evidence relevant to answering the question.

These criteria evaluate document retrieval. They do not establish the answer quality of a complete RAG system.

## 2. Data Understanding

### 2.1 Dataset Source
The project uses MMLongBench-Doc.

Dataset: https://huggingface.co/datasets/yubo2333/MMLongBench-Doc

Project website: https://mayubo2333.github.io/MMLongBench-Doc/

Research paper: https://arxiv.org/abs/2407.01523

### 2.2 Dataset Overview
The dataset contains 1,091 question records and references 135 PDF documents. The loaded dataset contains seven fields: `doc_id`, `doc_type`, `question`, `answer`, `evidence_pages`, `evidence_sources`, and `answer_format`.

### 2.3 Data Quality
The initial inspection found no missing values in the seven columns. No blank values were found in the question, answer, or document ID fields.

One duplicate document-and-question combination was identified. The two records had different answers and evidence annotations, so they were retained and documented as a potential dataset quality issue.

The dataset includes multiple document types and answer formats. Question lengths also vary, which reflects the different information needs represented in the dataset.

### 2.4 Data Limitations and Licensing
The project uses a small sample rather than the complete dataset for the retrieval experiment. The source materials may have different licensing and redistribution restrictions. Dataset and document licensing should be verified before redistributing source PDFs.

## 3. Data Preparation

### 3.1 Pilot Sample
A reproducible pilot sample of 30 questions was created using random seed 42. The selected records were checked against the available PDF documents.

Five questions were selected for the initial retrieval test. They cover an ITC logo question, a Best Buy tax question, a MIMIC-IT question about line plots, a Pew survey question, and a monitor safety instruction question.

### 3.2 PDF Text Extraction
The five corresponding PDFs were downloaded for the experiment. Text was extracted from PDF pages using PyMuPDF, and nonempty pages were indexed.

The experiment uses extracted text. It does not perform full multimodal interpretation of charts, figures, and other visual content.

### 3.3 Reproducibility
The notebook, pilot sample CSV, retrieval-results CSV, and manual-review CSV are maintained as project artifacts. The experiment's package versions and preprocessing steps are documented in the notebook.

## 4. Modeling

### 4.1 Baseline Approach
A TF-IDF retrieval baseline was implemented using scikit-learn. Text was lowercased, English stop words were removed, and unigram and bigram features were used. The vocabulary was limited to 50,000 features.

Cosine similarity was used to rank the PDF pages for each question. The three highest-ranked pages were displayed for manual inspection.

### 4.2 Experiment Scope
The experiment tested five questions against the extracted text from their associated PDFs. This small experiment is useful for checking the implementation and identifying retrieval errors, but it is too small to establish broad performance across the full dataset.

### 4.3 RAG-Anything Status
The `raganything` package was installed and imported, but the full RAG-Anything pipeline was not evaluated. Therefore, the experiment's quantitative results apply only to the TF-IDF baseline and must not be presented as RAG-Anything results.

## 5. Evaluation

### 5.1 Quantitative Results
Four of the five test questions have annotated evidence pages. For those four questions:

- Exact evidence-page hits: 2 out of 4 (50%).
- Exact or adjacent-page hits: 3 out of 4 (75%).

The MIMIC-IT question has an empty evidence-page annotation and is excluded from these evidence-page hit-rate calculations.

### 5.2 Manual Evidence Review
The retrieved excerpts were reviewed to determine whether the top-ranked results contained information that supported the reference answer.

| Question | Manual-review finding |
|---|---|
| ITC logo color | The correct PDF and annotated page were retrieved, but the displayed text excerpt does not state the logo color. The answer was separately verified visually. |
| Best Buy tax ratio | The correct PDF was retrieved, but the displayed top-three excerpts do not show the 20.7% figure or the exact calculation evidence. |
| MIMIC-IT line plots | The retrieved excerpt does not establish the number of line plots in the referenced slides. The dataset provides no annotated evidence pages for this question. |
| Pew survey percentage | Relevant survey pages were retrieved, but the displayed text alone does not conclusively establish the intended party interpretation and the 21% answer. |
| Monitor safety instruction | The top-ranked excerpt explicitly contains the reference answer: “Operate the unit on 100-240V AC only.” |

These findings show that retrieving a page from the correct document does not always mean the retrieved text contains sufficient evidence to answer the question.

### 5.3 Error Analysis
The Best Buy example suggests that relevant information may not be ranked among the top three displayed excerpts. The ITC example shows that text extraction may not capture visual information such as logo color. The MIMIC-IT example cannot be fully assessed using the annotated evidence-page metric. The Pew example requires careful interpretation of the original chart or table. The monitor example demonstrates successful retrieval of directly relevant text.

The manual review is based on the displayed excerpts. Additional inspection of the original PDF pages is needed to resolve the uncertain cases.

### 5.4 Evaluation Limitations
The test set contains only five questions. Results may change with a larger sample. The evidence-page metric measures page retrieval rather than end-to-end answer correctness. The text-only baseline is not designed to fully interpret charts or figures.

## 6. Deployment

### 6.1 Deployment Approach
The current notebook and CSV outputs provide a reproducible starting point for document retrieval experiments. The project artifacts are being organized in GitHub so that the experiment, results, and limitations can be reviewed.

### 6.2 Reproducibility and Documentation
The notebook documents the dataset source, preprocessing, retrieval method, package versions, evaluation metrics, results, and limitations. CSV files preserve the pilot sample, retrieval results, and manual-review findings.

Google Colab runtime storage can be temporary, so important artifacts should be downloaded and stored in the project repository.

### 6.3 Future Work
Future work should include:
- Completing and documenting the manual verification of uncertain results.
- Testing a larger and more representative set of questions.
- Improving retrieval for numerical, visual, and table-based questions.
- Evaluating the full RAG-Anything pipeline if the required model, API, and processing resources are available.
- Comparing baseline retrieval and RAG-Anything using the same evaluation questions and clearly defined metrics.

### 6.4 Conclusion
This project established an initial TF-IDF document retrieval baseline on five MMLongBench-Doc questions. The baseline achieved a 50% exact evidence-page hit rate and a 75% exact-or-adjacent-page hit rate across the four questions with evidence-page annotations.

The results highlight both successful retrieval and cases where the displayed evidence was insufficient. The full RAG-Anything pipeline remains unevaluated, so its effectiveness cannot yet be concluded from this experiment.
