# RAG Evaluation Data

## Overview

Question sets used to evaluate RAG answers for engineering and marketing teams.

UC Berkeley DATASCI 267 specified the business scenario for implementing RAG for engineering and marketing teams and provided the gold Q&A set.

## Files

- [Gold Q&A set](gold_answers.json): 75 questions with separate engineering and marketing reference answers
- [Additional questions](additional_questions.json): 30 questions without gold answers, including the out-of-domain example

The files retain the question IDs and text from the original notebook. Engineering references use `gold_answer_research`; marketing references use `gold_answer_marketing`.

## Evaluation

15 questions were randomly selected using seed 1234 to compare configurations. The selected configuration was then evaluated on all 75 questions for both audiences. The 15-question sample is part of the full validation set, not a separate test set.
