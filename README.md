# FinQA LLM Evaluation

## Project Setup

### Dependencies

Python dependencies can be installed by running the first python cell in the `eval.ipynb`.

- `python` - 3.11: Python version used for running the project.
- `jupyter` - 7.2.1: For running Jupyter notebooks.
- `openai` - 1.35.10: For interacting with OpenAI's API.
- `python-dotenv` - 1.0.1: For loading environment variables from a `.env` file.

### How to Use Notebook

1. **Setup**
   - Open the `eval.ipynb` file in Jupyter Notebook or Jupyter Lab.
   - Run the first python cell to install the dependencies

2. **Run the Code**
   - Run the cells sequentially to reproduce the evaluation results.

## Project Overview

- **Estimated time taken:** 4 hours
- **Accuracy:** 83.57%
- **Approach:** OpenAI assistant and function calling
- **LLMS:**
    - **Agent LLM:** GPT-4o
    - **Validator LLM:** GPT-3

## Underlying Assumptions

- Leveraging a Large Language Model (LLM) instead of a traditional Machine Learning (ML) model as per the task requirements.
- The application is designed for real-world deployment, implying that the use of `qa.steps` from the test set would not be feasible in a practical scenario as this data would not be available. I am aware that utilizing `qa.steps` within the prompt would [significantly increase accuracy (Few-shot CoT)](https://arxiv.org/pdf/2406.06608), leading to near 100% accuracy.

## Justification for Approach

- Time constraints prevented the fine-tuning of a custom model for the downstream task.
- Focus was placed on technology commonly used in Tomoro's environments rather than open-source models.
- A Jupyter notebook was employed for brevity.
- A comprehensive Exploratory Data Analysis (EDA) process was not conducted due to time constraints, leading to a lack of understanding of the data and missing key discrepancies such as mismatched keys in the data named ‘table_ori’, ‘qa_1’, ‘qa_0’, ‘text_23’, etc.
- The `.env` file and data folder were committed for brevity, which would *never* be done under normal circumstances.

## Proposed Improvements

- Develop a cost-effective pipeline that can scale efficiently.
- Implement robust type checking, monitoring, logging and error handling mechanisms.
- Enhance separation of concerns to improve scalability.
- Introduce evaluation metrics across various dimensions (e.g. hallucinations, precision, recall, relevancy, correctness, etc..).
- Introduce both unit tests and end-to-end (E2E) tests.
- Refactor the codebase into a well-structured Python project instead of relying on a single Jupyter notebook.

## Alternative Approach

- Utilize existing open-source models (e.g., GLM-4 and X-Win) that are leading in the market and perform exceptionally well in mathematical benchmarks.
- [Fine-tune the LLM through supervised learning on procedural math](https://arxiv.org/pdf/2305.14201) to enhance chain-of-thought (CoT) reasoning.
- Further fine-tune the LLM [on the provided training set (data.zip)](https://github.com/czyssrs/ConvFinQA) to deepen its mathematical understanding, and then evaluate on the test set.
- Implement checkpointing and evaluation at each stage to ensure continuous learning and prevent regression.
