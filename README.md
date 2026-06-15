# 🧠 Mental Health Text Classification

An end-to-end Natural Language Processing (NLP) project comparing a Bidirectional LSTM baseline with a fine-tuned DistilBERT transformer for multi-class mental health text classification.

Developed as part of the **Applied Artificial Intelligence Postgraduate Program** at **George Brown College**, this project demonstrates the complete machine learning workflow, including data preprocessing, exploratory data analysis, deep learning model development, evaluation, model comparison, and deployment with Streamlit.
> *(Project workflow image will be added here.)*

## 📌 Project Overview

Mental health professionals and researchers often work with large volumes of unstructured text collected from online forums, surveys, and social platforms. Manual analysis is time-consuming and difficult to scale.

This project investigates how deep learning can automatically classify mental health-related text into seven categories by comparing two modern Natural Language Processing approaches:

- Bidirectional Long Short-Term Memory (BiLSTM)
- DistilBERT Transformer

The project follows an end-to-end machine learning pipeline from exploratory data analysis and preprocessing through model training, evaluation, comparison, and deployment using Streamlit.

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

## 🎯 Objectives

- Perform exploratory data analysis on mental health text data.
- Build a Bidirectional LSTM baseline model.
- Fine-tune a DistilBERT transformer model.
- Compare deep learning architectures for multi-class text classification.
- Evaluate models using standard classification metrics.
- Deploy the final solution through a Streamlit web application.

## 🔄 Project Workflow

```

Kaggle Dataset

↓

Exploratory Data Analysis

↓

Text Cleaning

↓

Tokenization

↓

Model Development

├── Bidirectional LSTM

└── DistilBERT

↓

Model Evaluation

↓

Performance Comparison

↓

Streamlit Deployment

```
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

These observations guided the preprocessing strategy and motivated the use of class balancing techniques during model training.

## 🧹 Data Preprocessing

To prepare the dataset for model training, a complete preprocessing pipeline was implemented.

### Text Processing

- Removed missing records
- Converted text to lowercase
- Removed English stopwords using NLTK
- Removed unnecessary punctuation and special characters
- Standardized text formatting

### Label Processing

The target labels were encoded into numerical classes using Scikit-learn's `LabelEncoder`.

### BiLSTM Pipeline

For the Bidirectional LSTM model:

- Keras Tokenizer generated the vocabulary
- Vocabulary limited to 10,000 most frequent words
- Text converted into integer sequences
- Sequences padded to a maximum length of 100 tokens

### DistilBERT Pipeline

For the transformer model:

- Hugging Face `AutoTokenizer` was used
- Dynamic tokenization performed during training
- Maximum sequence length of 512 tokens
- Attention masks automatically generated

### Dataset Split

The dataset was divided into:

- Training Set
- Validation Set
- Test Set

using stratified sampling to preserve the class distribution across all subsets.

## 🤖 Model 1 — Bidirectional LSTM

The first model serves as a deep learning baseline for sequence classification.

### Architecture

- Embedding Layer
- Bidirectional LSTM (64 units)
- Dropout
- Batch Normalization
- Bidirectional LSTM (32 units)
- Dense Layer
- Softmax Output Layer (7 Classes)

### Training Configuration

- Optimizer: Adam
- Loss Function: Sparse Categorical Crossentropy
- Epochs: 6
- Batch Size: 32
- Class Weights applied to address dataset imbalance

### Performance

- Test Accuracy: **70%**
- Macro F1 Score: **0.68**
- Weighted F1 Score: **0.69**

The BiLSTM model demonstrated strong sequence learning capability but struggled with minority classes such as **Personality Disorder** and **Stress**, highlighting limitations when trained from scratch on imbalanced text datasets.

## 🚀 Model 2 — DistilBERT

To improve contextual understanding and classification performance, a pretrained DistilBERT transformer was fine-tuned using the Hugging Face Transformers library.

Unlike the BiLSTM model, DistilBERT leverages transfer learning from large-scale language pretraining, enabling stronger semantic representation of text.

### Training Configuration

- Pretrained Model: `distilbert-base-uncased`
- Epochs: 4
- Batch Size: 16 (training)
- Learning Rate: 1e-5
- Weight Decay: 0.01
- Learning Rate Scheduler: Cosine
- Early Stopping enabled

### Performance

- Test Accuracy: **82%**
- Macro F1 Score: **0.79**
- Weighted F1 Score: **0.82**

DistilBERT consistently outperformed the BiLSTM baseline across nearly every evaluation metric and demonstrated significantly stronger performance on challenging sentiment categories due to its contextual language understanding.


## 💻 Streamlit Application

To demonstrate the models in a real-world setting, a lightweight web application was developed using **Streamlit**.

The application allows users to:

- Select either the **BiLSTM** or **DistilBERT** model.
- Enter free-text mental health statements.
- View the predicted sentiment category.
- Display confidence scores for each prediction.
- Switch between **Technical** and **Layman** explanation modes.

This deployment demonstrates how trained NLP models can be integrated into an interactive application for inference and user-friendly visualization.

## 📂 Repository Structure

```
mental-health-text-classification/
│
├── app/
│   └── app.py
│
├── data/
│   ├── dataset_description.md
│   └── data_preprocessing.md
│
├── images/
│
├── models/
│
├── notebooks/
│   ├── 01_eda_preprocessing.ipynb
│   ├── 02_bilstm_training.ipynb
│   ├── 03_distilbert_training.ipynb
│   └── 04_evaluation.ipynb
│
├── src/
│
├── README.md
├── LICENSE
└── requirements.txt
```

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/cpL712/mental-health-text-classification.git

cd mental-health-text-classification
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Download Dataset

Download the dataset from Kaggle:

https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health

Place the dataset in:

```
data/raw/raw_data.csv
```

### Run the Streamlit Application

```bash
streamlit run app/app.py
```

## 📚 Future Improvements

Potential enhancements include:

- Evaluate additional transformer models such as BERT, RoBERTa, and DeBERTa.
- Apply data augmentation techniques to improve minority class performance.
- Perform systematic hyperparameter optimization using Optuna or Ray Tune.
- Deploy the application using Docker and cloud platforms such as Azure or AWS.
- Build a REST API using FastAPI for production inference.
- Integrate Explainable AI (XAI) techniques such as SHAP or LIME to improve prediction interpretability.

## 📚 Future Improvements

Potential enhancements include:

- Evaluate additional transformer models such as BERT, RoBERTa, and DeBERTa.
- Apply data augmentation techniques to improve minority class performance.
- Perform systematic hyperparameter optimization using Optuna or Ray Tune.
- Deploy the application using Docker and cloud platforms such as Azure or AWS.
- Build a REST API using FastAPI for production inference.
- Integrate Explainable AI (XAI) techniques such as SHAP or LIME to improve prediction interpretability.

## 👨‍💻 Author

**Cheung Pang Li**

- 🎓 Postgraduate Certificate in Applied Artificial Intelligence, George Brown College
- 🎓 B.Sc. Mathematics (Probability & Statistics), University of California San Diego

**GitHub**

https://github.com/cpL712

**LinkedIn**

https://www.linkedin.com/in/cheung-pang-li-b14b70387/

## 👤 My Contributions

This project was completed as part of a team. My primary contributions included:

- Fine-tuned the DistilBERT transformer model for multi-class mental health text classification.
- Assisted with exploratory data analysis and text preprocessing.
- Implemented data preparation and tokenization pipelines for transformer training.
- Evaluated model performance using accuracy, precision, recall, F1-score, and confusion matrices.
- Contributed to project documentation and comparative analysis between BiLSTM and DistilBERT.
