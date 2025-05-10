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


## 📊 Model Training & Evaluation

The model was trained on the `STSb-MT-Turkish` dataset using a hybrid regression architecture that combines:

- **Bi-directional Cross-Attention**
- **Multi-Head Self-Attention**
- **Sentence-level Mean Pooling**
- **Attention Pooling with Fusion**
- Output scaled to the **[0, 5]** range for semantic similarity.

Training was performed using:
- **Mixed-Precision Training (AMP)**
- **AdamW Optimizer**
- **Early Stopping based on Validation MAE**

### 🏋️ Training Progress

```txt
Epoch 1  | Train Loss: 1.6597 | Val MAE: 1.1838
Epoch 2  | Train Loss: 0.9385 | Val MAE: 0.6353
Epoch 3  | Train Loss: 0.5916 | Val MAE: 0.5385
Epoch 4  | Train Loss: 0.4554 | Val MAE: 0.4846
Epoch 5  | Train Loss: 0.3340 | Val MAE: 0.4428
Epoch 6  | Train Loss: 0.2790 | Val MAE: 0.4380
Epoch 7  | Train Loss: 0.2321 | Val MAE: 0.4291
Epoch 8  | Train Loss: 0.2104 | Val MAE: 0.3891
Epoch 9  | Train Loss: 0.1952 | Val MAE: 0.3604
Epoch 10 | Train Loss: 0.1735 | Val MAE: 0.3567
Epoch 11 | Train Loss: 0.1698 | Val MAE: 0.3410
Epoch 12 | Train Loss: 0.1698 | Val MAE: 0.3687
Epoch 13 | Train Loss: 0.1698 | Val MAE: 0.3978
→ Early stopping triggered
