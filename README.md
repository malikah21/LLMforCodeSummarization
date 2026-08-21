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
```
You are a senior software engineer with expertise in code readability, maintainability, and program comprehension.
Given a source code file along with contextual information, generate a clear and concise code summary.
Do not repeat the code. Ensure the summary is optimized for the following assessment aspects:
Semantic Correctness, Informativeness, Readability, Usefulness, and Overall Quality.
1. Semantic Correctness: The summary must accurately represent the code's logic, control flow, and technical behavior without misinterpretation.
2. Informativeness: The summary must include key details such as the primary objective, major input/output, and relevant dependencies.
3. Readability: The summary must use straightforward, structured language that is easy for other developers to comprehend.
4. Usefulness: The summary must provide context that aids in code maintenance and program understanding.
5. Overall Quality: The summary must be professional, concise, and adhere to industry-standard documentation practices.

Inputs:
- Code: {code}
- README: {readme}
- Complexity: {complexity}
- Comments: {comments}
- Commits: {commits}
- Code Size: {len(code)}

Output ONLY the final summary.
```

2. **Few-shot prompting**
```
You are a senior software engineer with expertise in code readability, maintainability, and program comprehension.
Given a source code file along with contextual information, generate a clear and concise code summary.
Do not repeat the code. Ensure the summary is optimized for the following assessment aspects:
Semantic Correctness, Informativeness, Readability, Usefulness, and Overall Quality.
1. Semantic Correctness: The summary must accurately represent the code's logic, control flow, and technical behavior without misinterpretation.
2. Informativeness: The summary must include key details such as the primary objective, major input/output, and relevant dependencies.
3. Readability: The summary must use straightforward, structured language that is easy for other developers to comprehend.
4. Usefulness: The summary must provide context that aids in code maintenance and program understanding.
5. Overall Quality: The summary must be professional, concise, and adhere to industry-standard documentation practices.

Below are examples of how to generate the summary:
### EXAMPLE 1 ###
Inputs:
- Code: 
def load_config(filepath):
   if not os.path.exists(filepath):
   raise FileNotFoundError("Config missing")
   with open(filepath, 'r') as 
f: return json.load(f)
- README: Utility to initialize system settings.
- Complexity: Cyclomatic Complexity: 2
- Comments: Checks for file existence before loading JSON.
- Commits: Added error handling for missing configuration files.
- Code Size: 5 lines

Output:
The `load_config` function acts as a secure utility to initialize system settings by parsing a JSON configuration file. Its primary objective is to safely read the file and return a dictionary of settings (Output) based on the provided `filepath` string (Input). The function includes a critical validation step added in a recent commit that checks for file existence and raises a `FileNotFoundError` if the file is missing, preventing unexpected downstream crashes. With a low cyclomatic complexity, this straightforward utility ensures the system fails gracefully during initialization, making it highly maintainable and essential for overall system stability.

### ACTUAL TASK ###
Inputs:
- Code: {code}
- README: {readme}
- Complexity: {complexity}
- Comments: {comments}
- Commits: {commits}
- Code Size: {len(code)}

Output:
```

3. **Chain-of-thought prompting**
```
You are a senior software engineer with expertise in code readability, maintainability, and program comprehension.
Given a source code file along with contextual information, generate a clear and concise code summary.
Do not repeat the code. Ensure the summary is optimized for the following assessment aspects:
Semantic Correctness, Informativeness, Readability, Usefulness, and Overall Quality.

Follow this step by step thinking process to formulate your response:
Step 1: Analyze the code holistically
- Identify what the code does and determine its main purpose.
- Understand major inputs and outputs (Informativeness).
Step 2: Break down the logic
- Identify key operations and control flow.
- Ensure the technical behavior is understood without misinterpretation (Semantic Correctness).
Step 3: Incorporate contextual information
- Context: Complexity: {complexity}, Comments: {comments}, Commits: {commits}, README: {readme}, Code Size: {len(code)}.
- Use this information to grasp the code's role in system maintenance and its broader context (Usefulness). Do NOT repeat these raw metrics directly.
Step 4: Refine explanation
- Avoid redundancy.
- Use clear, straightforward, and precise language (Readability).
- Ensure the narrative aligns with professional documentation standards (Overall Quality).
Step 5: Generate final summary
- Write a cohesive 2-3 sentence paragraph.
- Focus strictly on functionality and purpose.

Important:
Output ONLY the final summary. Do NOT include your internal steps, reasoning, bullet points, or explanations in the final output.
Code:
{code}

Summary:
```

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
