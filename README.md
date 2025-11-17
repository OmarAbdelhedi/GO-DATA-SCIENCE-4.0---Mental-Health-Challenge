# GO! Data Science 4.0 – Mental Health Challenge 🧠📚

This repository contains my solution for the [GO! Data Science 4.0 – Mental Health Challenge](https://zindi.africa/competitions/go-data-science-40-mental-health-challenge) hosted on Zindi. The goal of the challenge was to classify mental health-related texts into predefined categories using natural language processing techniques.

---

## 🧠 Problem Statement

Given a set of short text entries (titles and contents), the task was to classify each entry into one of several mental health-related target categories. The dataset presented challenges such as:
- Noisy and short-form language,
- Imbalanced label distribution,
- Ambiguous language between classes.

---

## 🚀 Solution Overview

- **Model:**  
  Fine-tuned [`mental/mental-roberta-base`](https://huggingface.co/mental/mental-roberta-base), a RoBERTa model pre-trained on mental health-related text.

- **Preprocessing:**  
  - Combined title and content fields.
  - Encoded target labels using `LabelEncoder`.

- **Training Strategy:**  
  - Used Hugging Face `Trainer` API with `TrainingArguments`.
  - Split dataset 80/20 for train/validation.
  - Optimized using **weighted F1-score**.

- **Inference Pipeline:**  
  - Cleaned and tokenized test data.
  - Loaded the best saved model.
  - Used `Trainer.predict` for inference and label decoding.
  - Generated `submission.csv` in the required format.
