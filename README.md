# Research Artifact: 
# Source Code Summarization with LLMs: Evaluating the Impact of Software Artifacts

This repository provides the research artifact and experimental dataset for evaluating Large Language Model (LLM)-based source code summarization using **Qwen, DeepSeek, and CodeLlama**.

The study investigates the performance of the three LLMs under **zero-shot, few-shot, and chain-of-thought prompting strategies**. The generated code summaries are evaluated using automatic evaluation metrics and human assessment to examine differences in summarization quality across models and prompting approaches.

The purpose of this repository is to provide the datasets, experimental outputs, evaluation results, and supporting materials required to reproduce the study and enable further research on LLM-based source code summarization.

## Contents

* `automatic_evaluation/`
  Contains the results of automatic evaluation of generated code summaries using metrics such as **BLEU, ROUGE, and METEOR**. The data are organized to support comparison across LLM models and prompting strategies.

* `human_evaluation/`
  Contains the human evaluation data used to assess the quality of generated code summaries from a human perspective. This evaluation complements automatic metrics by examining aspects of summary quality that may not be fully captured by lexical similarity measures.

* `sourcecode/`
  Contains the source code samples used as input for the code summarization experiments. These samples form the experimental dataset evaluated across Qwen, DeepSeek, and CodeLlama.

* `README.md`
  Provides an overview of the repository, research objectives, dataset organization, and experimental evaluation.

* `LICENSE`
  Specifies the terms under which the research artifact and repository materials may be used and redistributed.

## Experimental Design

The experiment evaluates three Large Language Models:

1. **Qwen**
2. **DeepSeek**
3. **CodeLlama**

Each model is evaluated using three prompting strategies:

1. **Zero-shot prompting**
2. **Few-shot prompting**
3. **Chain-of-thought prompting**

This results in nine model-prompt configurations used to generate source code summaries.

## Evaluation

The generated summaries are evaluated using two complementary approaches.

### Automatic Evaluation

Automatic evaluation measures similarity between generated summaries and reference summaries using:

* BLEU
* ROUGE
* METEOR

These metrics are used to compare the performance of different LLM and prompting configurations.

### Human Evaluation

Human evaluation is conducted to assess qualitative aspects of the generated summaries that cannot be fully represented by automatic metrics.

The combination of automatic and human evaluation provides a more comprehensive assessment of LLM-based source code summarization performance.

## Research Purpose

This artifact is intended to:

1. Support reproducibility of the experimental results.
2. Facilitate comparison between Qwen, DeepSeek, and CodeLlama.
3. Examine the effectiveness of different prompting strategies for source code summarization.
4. Compare automatic evaluation results with human judgments.
5. Provide reusable experimental data for future research on LLM-based software engineering tasks.

## Repository

`https://github.com/malikah21/LLMforCodeSummarization`

## Authors:
1. Malika Harsanto
2. [Yusuf Sulistyo Nugroho](https://www.ums.ac.id/profile/yusuf-sulistyo-nugroho)
3. [Syful Islam](https://syful-is.github.io/)
