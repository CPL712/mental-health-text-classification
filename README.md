# 🧠 Mental Health Text Classification

An end-to-end Natural Language Processing (NLP) project comparing a Bidirectional LSTM baseline with a fine-tuned DistilBERT transformer for multi-class mental health text classification.

Developed as part of the **Applied Artificial Intelligence Postgraduate Program** at **George Brown College**, this project demonstrates the complete machine learning workflow, including data preprocessing, exploratory data analysis, deep learning model development, evaluation, and model comparison.

---

## 📌 Project Overview

Mental health professionals and researchers often work with large volumes of unstructured text collected from online forums, surveys, and social platforms. Manual analysis is time-consuming and difficult to scale.

This project investigates how deep learning can automatically classify mental health-related text into seven categories by comparing two modern Natural Language Processing approaches:

- Bidirectional Long Short-Term Memory (BiLSTM)
- DistilBERT Transformer

The project follows an end-to-end machine learning pipeline from exploratory data analysis and preprocessing through model training, evaluation, and comparison.

---

## 📂 Dataset

**Source**

Kaggle – Sentiment Analysis for Mental Health

https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health

### Dataset Summary

- Over 53,000 labelled text statements
- Seven mental health categories
- English language
- Multi-class classification problem

### Categories

- Anxiety
- Bipolar
- Depression
- Normal
- Personality Disorder
- Stress
- Suicidal

> **Note:** The dataset is not included in this repository. Please download it directly from Kaggle and place `raw_data.csv` under `data/raw/`.

---

## 🎯 Objectives

- Perform exploratory data analysis on mental health text data.
- Build a Bidirectional LSTM baseline model.
- Fine-tune a DistilBERT transformer model.
- Compare deep learning architectures for multi-class text classification.
- Evaluate models using standard classification metrics.

---

## 🔄 Project Workflow

```
Kaggle Dataset
      │
Exploratory Data Analysis
      │
Text Cleaning
      │
Tokenization
      │
Model Development
├── Bidirectional LSTM
└── DistilBERT
      │
Model Evaluation
      │
Performance Comparison
```

---

## 🛠 Technologies Used

| Category | Technologies |
|----------|--------------|
| Programming Language | Python |
| Deep Learning | TensorFlow, Keras, PyTorch |
| Natural Language Processing | Hugging Face Transformers, DistilBERT, Bidirectional LSTM, NLTK |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Visualization | Matplotlib, Seaborn |
| Development Environment | Google Colab, Jupyter Notebook |
| Deployment | Streamlit |
| Version Control | Git, GitHub |

---

## 📊 Exploratory Data Analysis

Before model development, exploratory data analysis was performed to understand the characteristics of the dataset.

The analysis included:

- Examining the distribution of the seven sentiment classes
- Identifying missing values
- Measuring text length distribution
- Inspecting vocabulary size
- Exploring class imbalance

### Key Findings

- The dataset contains over **53,000** labeled statements.
- Class distribution is imbalanced, with **Normal** and **Depression** containing significantly more samples than **Personality Disorder** and **Stress**.
- Text lengths vary considerably, making sequence padding necessary for deep learning models.
- No significant data quality issues remained after preprocessing.

> *(EDA figures will be added soon.)*

---

## 🧹 Data Preprocessing

The preprocessing pipeline included:

### Text Processing

- Removed missing records
- Converted text to lowercase
- Removed English stopwords
- Removed unnecessary punctuation
- Standardized text formatting

### Label Processing

- Encoded labels using Scikit-learn's `LabelEncoder`

### BiLSTM Pipeline

- Keras Tokenizer
- Vocabulary size of 10,000 words
- Sequence padding

### DistilBERT Pipeline

- Hugging Face AutoTokenizer
- Dynamic tokenization
- Attention masks
- Maximum sequence length of 512 tokens

---

## 🤖 Model 1 — Bidirectional LSTM

The first model serves as a deep learning baseline.

### Architecture

- Embedding Layer
- Bidirectional LSTM
- Dropout
- Batch Normalization
- Bidirectional LSTM
- Dense Layer
- Softmax Output

### Performance

- Test Accuracy: **70%**
- Weighted F1-score: **0.69**

---

## 🚀 Model 2 — DistilBERT

A pretrained DistilBERT transformer was fine-tuned using the Hugging Face Transformers library.

### Performance

- Test Accuracy: **82%**
- Weighted F1-score: **0.82**

DistilBERT consistently outperformed the BiLSTM baseline, demonstrating superior contextual understanding of mental health-related language.

---

## 📈 Model Comparison

| Metric | Bidirectional LSTM | DistilBERT |
|---------|-------------------:|-----------:|
| Test Accuracy | **70%** | **82%** |
| Weighted F1-score | **0.69** | **0.82** |
| Training Strategy | Train from Scratch | Transfer Learning |

### Key Findings

- DistilBERT outperformed the BiLSTM baseline across all evaluation metrics.
- Transfer learning significantly improved contextual understanding.
- BiLSTM provided a lightweight and effective baseline.
- Transformer-based models demonstrated stronger generalization.

---


## 📂 Repository Structure

```text
mental-health-text-classification/
│
│
├── data/
│   ├── raw/
│   ├── dataset_description.md
│   └── data_preprocessing.md
│
├── docs/
│   └── Mental_Health_Text_Classification_Report.pdf
│
├── images/
│
├── models/
│   └── README.md
│
├── notebooks/
│   ├── 01_eda_preprocessing.ipynb
│   ├── 02_bilstm_training.ipynb
│   ├── 03_distilbert_training.ipynb
│   └── 04_model_evaluation.ipynb
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/cpL712/mental-health-text-classification.git

cd mental-health-text-classification
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the dataset from Kaggle and place:

```text
data/raw/raw_data.csv
```

Run the Streamlit application:

```bash
streamlit run app/app.py
```

---

## 📄 Project Report

The complete report is available in:

```text
docs/Mental_Health_Text_Classification_Report.pdf
```

---

## 📚 Future Improvements

- Evaluate larger transformer models (BERT, RoBERTa, DeBERTa)
- Improve minority-class performance through data augmentation
- Hyperparameter optimization
- Docker deployment
- FastAPI inference API
- Explainable AI (SHAP / LIME)

---

## 👤 My Contributions

This project was completed as part of a postgraduate team project.

My primary contributions included:

- Fine-tuning the DistilBERT model using Hugging Face Transformers.
- Assisting with exploratory data analysis and text preprocessing.
- Preparing datasets for transformer-based training.
- Evaluating model performance using accuracy, precision, recall, F1-score, and confusion matrices.
- Contributing to comparative analysis between BiLSTM and DistilBERT.

---

## 👨‍💻 Author

**Cheung Pang Li**

- Postgraduate Certificate in Applied Artificial Intelligence — George Brown College
- B.Sc. Mathematics (Probability & Statistics) — University of California, San Diego

**GitHub**

https://github.com/cpL712

**LinkedIn**

https://www.linkedin.com/in/cheung-pang-li-b14b70387/
