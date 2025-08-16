# YNWA_PZ at SemEval-2025 Task 11

paper link: [ACL Anthology](https://aclanthology.org/2025.semeval-1.71/)
models link: [HuggingFace](https://huggingface.co/ErfanSadegh)

## Multilingual Multi-Label Sentiment Analysis

This repository contains the LaTeX source files for our research paper and Jupyter notebooks used for experiments in the SemEval-2025 Task 11: **Multilingual Multi-Label Sentiment Analysis**. The study explores emotion classification across multiple languages using deep learning approaches, including transformer-based models and traditional classifiers.

## Table of Contents

- [YNWA\_PZ at SemEval-2025 Task 11](#ynwa_pz-at-semeval-2025-task-11)
  - [Multilingual Multi-Label Sentiment Analysis](#multilingual-multi-label-sentiment-analysis)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [System Overview](#system-overview)
  - [Installation](#installation)
  - [Dataset](#dataset)
  - [Preprocessing](#preprocessing)
  - [Models and Techniques](#models-and-techniques)
  - [Experiments](#experiments)
  - [Results](#results)
  - [Contributors](#contributors)
  - [License](#license)
  - [Citation](#citation)

## Introduction

Understanding emotions in multilingual text is crucial for various applications, including social media analysis and behavioral research. Our approach categorizes emotions into six key dimensions:

- **Sadness**
- **Anger**
- **Fear**
- **Disgust**
- **Joy**
- **Surprise**

We evaluate three distinct tracks:
1. **Track A** - Binary emotion classification.
2. **Track B** - Emotion intensity estimation (scale from 0 to 3).
3. **Track C** - Cross-lingual emotion detection.

## System Overview

Our system follows a pipeline consisting of:
1. **Text Preprocessing**
2. **Feature Extraction** using transformer-based embeddings (LLMs, MLMs, etc.)
3. **Classification** using SVM, XGBoost, and MLP

We experimented with multiple architectures to determine the best model per language, ensuring adaptability to both high- and low-resource languages.

## Installation

Clone the repository and install dependencies:
```bash
git clone https://github.com/YNWA-PZ/SemEval2025-task11.git
cd SemEval2025-task11
python -m notebook
```

## Dataset

The dataset comprises multilingual texts annotated for emotion labels. We split it into:
- **80% Training**
- **20% Validation**
- **Held-out Test Set** (for final evaluation)

## Preprocessing

Preprocessing steps include:
- Lowercasing text
- Removing special characters, URLs.
- Replacing emojis with their description.
- Tokenization using language-specific methods
- Stopword removal

## Models and Techniques

We experimented with:
- **Feature Extraction**: Transformer embeddings (XLM-R, mBERT, E5, etc.)
- **Classifiers**: SVM, XGBoost, and MLP
- **Optimization**: Fine-tuning using LoRA, AdamW optimizer, and learning rate schedulers

## Experiments

All experiments were conducted on **Kaggle Tesla P100 GPUs**. We used **Optuna** for hyperparameter tuning and **Scikit-learn** for evaluation metrics.

## Results

Our approach achieved competitive macro-average F1 scores across multiple languages. Notably, we ranked **2nd place** in cross-lingual detection for **Tigrinya and Kinyarwanda**.

## Contributors

- **Mohammad Sadegh Poulaei** (Iran University of Science and Technology)
- **Erfan Zare** (Iran University of Science and Technology)
- **Mohammad Reza Mohammadi** (Iran University of Science and Technology)
- **Sauleh Etemadi** (University of Birmingham)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
For more details, refer to our [paper](paper.pdf) and [notebooks](notebooks/). Feel free to raise issues or contribute!

## Citation

```bibtex
@inproceedings{poulaei-etal-2025-ynwa,
    title = "{YNWA}{\_}{PZ} at {S}em{E}val-2025 Task 11: Multilingual Multi-Label Emotion Classification",
    author = "Poulaei, Mohammad Sadegh  and
      Zare, Mohammad Erfan  and
      Mohammadi, Mohammad Reza  and
      Eetemadi, Sauleh",
    editor = "Rosenthal, Sara  and
      Ros{\'a}, Aiala  and
      Ghosh, Debanjan  and
      Zampieri, Marcos",
    booktitle = "Proceedings of the 19th International Workshop on Semantic Evaluation (SemEval-2025)",
    month = jul,
    year = "2025",
    address = "Vienna, Austria",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.semeval-1.71/",
    pages = "508--521",
    ISBN = "979-8-89176-273-2"
}
```
