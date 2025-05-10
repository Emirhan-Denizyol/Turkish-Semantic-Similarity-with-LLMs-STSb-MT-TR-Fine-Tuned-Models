# 🇹🇷 Turkish Semantic Similarity with LLMs (STSb-MT-TR)

This repository presents a Large Language Model (LLM)-based architecture fine-tuned on the **STSb-MT-Turkish** dataset to estimate **semantic similarity scores** between two Turkish sentences.

## 🚀 Project Summary

Semantic Textual Similarity (STS) models are designed to score the degree of semantic equivalence between pairs of sentences. While English and multilingual models are widespread, Turkish-specific semantic similarity research is still limited. This project aims to fill that gap by:

- Fine-tuning transformer-based LLMs (e.g., RoBERTa, BERT, DeBERTa, etc.) on the **STSb-MT-Turkish** dataset.
- Producing continuous similarity scores in the [0, 5] range.
- Supporting real-time inference for downstream NLP tasks (e.g., paraphrase detection, duplicate question detection, semantic search, etc.).

---

## 📂 Dataset

- **Name:** STSb-MT-Turkish  
- **Source:** Translated version of the Semantic Textual Similarity Benchmark (STSb) dataset for Turkish.  
- **License:** [Refer to original dataset terms](https://huggingface.co/datasets/emrecan/stsb-mt-turkish).

---

## 🧠 Model Details

| Feature               | Description                                        |
|-----------------------|----------------------------------------------------|
| Base Model            | `bert-base-turkish-uncased` / `xlm-roberta-base` (configurable) |
| Objective             | Regression (Mean Squared Error)                   |
| Input Format          | Pair of sentences                                 |
| Output                | Float score between 0 and 5                        |
| Evaluation Metric     | Pearson / Spearman Correlation                     |

---


