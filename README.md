# RAG Pipeline Implementation and Evaluation

## Overview

Implement and evaluate a retrieval-augmented generation (RAG) pipeline to answer GenAI questions for engineering and marketing teams. Both teams use the same document collection, with different prompts for technical explanations and high-level answers.

UC Berkeley Master of Information and Data Science project (DATASCI 267). The course specified the business scenario for implementing RAG for engineering and marketing teams and provided the gold Q&A set.

## Methodology

- Research papers, Wikipedia pages, technical blogs, and business sources as the document collection
- LangChain pipeline with MPNet embeddings and Qdrant vector search
- Baseline comparison of Cohere and Mistral
- Experiments with chunk size, number of retrieved chunks, and audience prompts
- Cosine similarity and ROUGE-L F1 against engineering and marketing gold answers, supplemented by review of generated answers and retrieved context

## Results

Cohere with 1,000-character chunks, no overlap, four retrieved chunks, and the original prompts had the highest average cosine similarity for both teams in the 15-question comparison. Retrieving eight chunks lowered both metrics. Revised prompts improved engineering ROUGE-L but lowered cosine similarity for both teams.

Results for the selected configuration on all 75 validation questions:

| Audience | Average cosine similarity | Average ROUGE-L F1 |
| --- | ---: | ---: |
| Engineering | 0.818888 | 0.136126 |
| Marketing | 0.813214 | 0.199620 |

75 questions per audience, producing 150 answers. The 15 questions used to compare configurations are included in the full validation set. These are similarity scores, not accuracy percentages. Answer review showed that high similarity could still miss key facts or include claims unsupported by the retrieved context.

## Files

- [Notebook](rag_evaluation.ipynb)
- [Report](rag_evaluation_report.pdf)
- [Evaluation data](data/README.md)
- [Saved results](results/README.md)
- [Dependencies](requirements.txt)

## How to Run

1. Download or clone the project, keeping the notebook, `requirements.txt`, and `data/` together.
2. Open the notebook from the project folder in a GPU runtime suitable for the original 4-bit Mistral setup.
3. Set `COHERE_API_KEY` and, if needed for model access, `HF_TOKEN` through environment variables or Colab secrets.
4. Run the setup cell to install dependencies, then run the remaining cells in order.
